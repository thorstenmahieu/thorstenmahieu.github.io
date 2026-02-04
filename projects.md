---
layout: page
title: Projects
permalink: /projects/
---

<div class="filters">
  <div class="filter-group">
    <label>Project Type:</label>
    <button class="filter-btn" data-filter-type="project-type" data-filter-value="">All</button>
    <button class="filter-btn" data-filter-type="project-type" data-filter-value="personal">Personal</button>
    <button class="filter-btn" data-filter-type="project-type" data-filter-value="school">School</button>
    <button class="filter-btn" data-filter-type="project-type" data-filter-value="work">Work</button>
  </div>

  <div class="filter-group">
    <label>Programming Language:</label>
    <button class="filter-btn" data-filter-type="language" data-filter-value="">All</button>
    <button class="filter-btn" data-filter-type="language" data-filter-value="python">Python</button>
    <button class="filter-btn" data-filter-type="language" data-filter-value="javascript">JavaScript</button>
    <button class="filter-btn" data-filter-type="language" data-filter-value="c">C</button>
    <button class="filter-btn" data-filter-type="language" data-filter-value="c#">C#</button>
    <button class="filter-btn" data-filter-type="language" data-filter-value="dart">Dart</button>
    <button class="filter-btn" data-filter-type="language" data-filter-value="matlab">MATLAB</button>
    <button class="filter-btn" data-filter-type="language" data-filter-value="labview">LabVIEW</button>
  </div>

  <div class="filter-group">
    <label>Tags:</label>
    <button class="filter-btn" data-filter-type="tag" data-filter-value="">All</button>
    <div id="tag-filters"></div>
  </div>

  <div class="filter-group">
    <label>Project Size:</label>
    <button class="filter-btn" data-filter-type="size" data-filter-value="">All</button>
    <button class="filter-btn" data-filter-type="size" data-filter-value="small">Small</button>
    <button class="filter-btn" data-filter-type="size" data-filter-value="medium">Medium</button>
    <button class="filter-btn" data-filter-type="size" data-filter-value="large">Large</button>
  </div>

  <div class="filter-group">
    <label>Collaboration Type:</label>
    <button class="filter-btn" data-filter-type="collaboration" data-filter-value="">All</button>
    <button class="filter-btn" data-filter-type="collaboration" data-filter-value="solo">Solo</button>
    <button class="filter-btn" data-filter-type="collaboration" data-filter-value="group">Group</button>
  </div>
</div>

<div class="timeline">

{% assign sorted = site.projects | sort: "start-date" | reverse %}
{% for project in sorted %}

  <div class="timeline-item project-card"
       data-tags="{{ project.tags | join: ',' }}"
       data-language="{{ project.programming-language | downcase }}"
       data-size="{{ project.size | downcase }}"
       data-project-type="{{ project.project-type }}"
       data-collaboration="{{ project.collaboration-type | downcase }}"
       data-important="{{ project.important }}">

    <span class="timeline-year">{{ project.start-date }}</span>

    <div class="card-content">
      <h3>
        <a href="{{ project.url }}">
          {{ project.title }}
        </a>
      </h3>

      <p>{{ project.excerpt }}</p>

      {% if project.rating %}
        <div class="rating-stars">
          {% assign rating_value = project.rating | split: "/" | first | plus: 0 %}
          {% for i in (1..5) %}
            {% if i <= rating_value %}
              <span class="star filled">★</span>
            {% else %}
              <span class="star empty">☆</span>
            {% endif %}
          {% endfor %}
        </div>
      {% endif %}

      <div class="project-tags">
        {% for tag in project.tags %}
          <span class="tag-badge" data-tag="{{ tag }}">
            {{ tag | replace: '-', ' ' }}
          </span>
        {% endfor %}
      </div>
    </div>

  </div>

{% endfor %}
</div>
<script>
// Collect all unique tags from project cards
const allTags = new Set();
document.querySelectorAll('.project-card').forEach(card => {
  const tags = card.dataset.tags.split(',').filter(t => t.trim());
  tags.forEach(tag => allTags.add(tag.trim()));
});

// Populate tag filter buttons
const tagFilterContainer = document.getElementById('tag-filters');
Array.from(allTags).sort().forEach(tag => {
  const btn = document.createElement('button');
  btn.className = 'filter-btn';
  btn.textContent = tag.replace('-', ' ');
  btn.dataset.filterType = 'tag';
  btn.dataset.filterValue = tag;
  tagFilterContainer.appendChild(btn);
});

// Filtering state
const activeFilters = {
  'project-type': '',
  'language': '',
  'size': '',
  'collaboration': '',
  'tag': []
};

// Add event listeners to filter buttons
document.querySelectorAll('.filter-btn').forEach(btn => {
  btn.addEventListener('click', (e) => {
    const filterType = e.target.dataset.filterType;
    const filterValue = e.target.dataset.filterValue;
    
    if (filterType === 'tag') {
      // For tags, toggle selection
      if (filterValue === '') {
        // Clear all tags
        activeFilters['tag'] = [];
      } else {
        const index = activeFilters['tag'].indexOf(filterValue);
        if (index > -1) {
          activeFilters['tag'].splice(index, 1);
        } else {
          activeFilters['tag'].push(filterValue);
        }
      }
    } else {
      // For other filters, single selection
      activeFilters[filterType] = filterValue;
    }
    
    updateActiveButtonStyles();
    filterProjects();
  });
});

function updateActiveButtonStyles() {
  document.querySelectorAll('.filter-btn').forEach(btn => {
    const filterType = btn.dataset.filterType;
    const filterValue = btn.dataset.filterValue;
    
    let isActive = false;
    if (filterType === 'tag') {
      isActive = filterValue === '' ? activeFilters['tag'].length === 0 : activeFilters['tag'].includes(filterValue);
    } else {
      isActive = activeFilters[filterType] === filterValue;
    }
    
    if (isActive) {
      btn.classList.add('active');
    } else {
      btn.classList.remove('active');
    }
  });
}

function filterProjects() {
  document.querySelectorAll('.project-card').forEach(card => {
    let show = true;
    
    // Check project type filter
    if (activeFilters['project-type']) {
      const cardProjectType = card.dataset.projectType;
      show = show && cardProjectType === activeFilters['project-type'];
    }
    
    // Check language filter
    if (activeFilters['language'] && show) {
      const cardLanguages = card.dataset.language.split(',').map(l => l.trim().toLowerCase());
      show = show && cardLanguages.some(lang => lang === activeFilters['language'].toLowerCase());
    }
    
    // Check size filter
    if (activeFilters['size'] && show) {
      const cardSize = (card.dataset.size || '').toLowerCase();
      show = show && cardSize === activeFilters['size'].toLowerCase();
    }
    
    // Check collaboration filter
    if (activeFilters['collaboration'] && show) {
      const cardCollaboration = (card.dataset.collaboration || '').toLowerCase();
      const collaborationTypes = cardCollaboration.split(',').map(c => c.trim());
      show = show && collaborationTypes.includes(activeFilters['collaboration'].toLowerCase());
    }
    
    // Check tag filter (multiple tags with OR logic)
    if (activeFilters['tag'].length > 0 && show) {
      const cardTags = card.dataset.tags.split(',').map(t => t.trim());
      show = show && activeFilters['tag'].some(selectedTag => cardTags.includes(selectedTag));
    }
    
    card.style.display = show ? 'block' : 'none';
  });
}

// Initialize active button styles
updateActiveButtonStyles();
</script>
