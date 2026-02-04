---
layout: page
title: Projects
permalink: /projects/
---

<div class="filters">
  <div class="filter-group">
    <label>Project Type:</label>
    <button class="filter-btn" data-filter-type="project-type" data-filter-value="">All</button>
    <button class="filter-btn" data-filter-type="project-type" data-filter-value="personal-project">Personal</button>
    <button class="filter-btn" data-filter-type="project-type" data-filter-value="school-project">School</button>
    <button class="filter-btn" data-filter-type="project-type" data-filter-value="work-project">Work</button>
    <button class="filter-btn" data-filter-type="project-type" data-filter-value="solo-project">Solo</button>
    <button class="filter-btn" data-filter-type="project-type" data-filter-value="group-work">Group</button>
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
</div>

<div class="timeline">

{% assign sorted = site.projects | sort: "start-date" | reverse %}
{% for project in sorted %}

  <div class="timeline-item project-card"
       data-tags="{{ project.tags | join: ',' }}"
       data-language="{{ project.programming-language | downcase }}"
       data-important="{{ project.important }}">

    <span class="timeline-year">{{ project.start-date }}</span>

    <div class="card-content">
      <h3>
        <a href="{{ project.url }}">
          {{ project.title }}
        </a>
      </h3>

      <p>{{ project.excerpt }}</p>

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
  'tag': ''
};

// Add event listeners to filter buttons
document.querySelectorAll('.filter-btn').forEach(btn => {
  btn.addEventListener('click', (e) => {
    const filterType = e.target.dataset.filterType;
    const filterValue = e.target.dataset.filterValue;
    
    activeFilters[filterType] = filterValue;
    updateActiveButtonStyles();
    filterProjects();
  });
});

function updateActiveButtonStyles() {
  document.querySelectorAll('.filter-btn').forEach(btn => {
    const filterType = btn.dataset.filterType;
    const filterValue = btn.dataset.filterValue;
    
    if (activeFilters[filterType] === filterValue) {
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
      const cardTags = card.dataset.tags.split(',').map(t => t.trim());
      show = show && cardTags.includes(activeFilters['project-type']);
    }
    
    // Check language filter
    if (activeFilters['language'] && show) {
      const cardLanguages = card.dataset.language.split(',').map(l => l.trim().toLowerCase());
      show = show && cardLanguages.some(lang => lang.includes(activeFilters['language'].toLowerCase()));
    }
    
    // Check tag filter
    if (activeFilters['tag'] && show) {
      const cardTags = card.dataset.tags.split(',').map(t => t.trim());
      show = show && cardTags.includes(activeFilters['tag']);
    }
    
    card.style.display = show ? 'block' : 'none';
  });
}

// Initialize active button styles
updateActiveButtonStyles();
</script>
