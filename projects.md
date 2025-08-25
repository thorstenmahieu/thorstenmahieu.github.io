---

layout: page
title: "All Projects"
permalink: projects/
---

<!-- Dropdown Filter -->
<label for="tag-filter">Filter by tag:</label>
<select id="tag-filter">
  <option value="all" selected>All</option>
</select>


<!-- Projects List -->
<ul id="projects-list">
  {% assign sorted_projects = site.pages | sort: "title" %}
  {% for project in sorted_projects %}
    {% if project.tags %}
      <li class="project-item" data-tags="{{ project.tags | join: ',' }}">
        <a href="{{ project.url }}">{{ project.title }}</a>
      </li>
    {% endif %}
  {% endfor %}
</ul>

<script>
// Dynamically populate the dropdown with unique tags from projects
document.addEventListener('DOMContentLoaded', function () {
  const tagDropdown = document.getElementById('tag-filter');
  const projectItems = document.querySelectorAll('.project-item');
  const uniqueTags = new Set();

  // Collect all tags from the project items
  projectItems.forEach(item => {
    const tags = item.getAttribute('data-tags').split(',');
    tags.forEach(tag => uniqueTags.add(tag.trim()));
  });

  // Add tags to the dropdown as options
  const sortedTags = Array.from(uniqueTags).sort((a, b) => a.localeCompare(b, undefined, { sensitivity: 'base' }));

  sortedTags.forEach(tag => {
    const option = document.createElement('option');
    option.value = tag;
    option.textContent = tag.replace(/-/g, ' ');
    tagDropdown.appendChild(option);
  });

  // Filter projects based on the selected tag
  tagDropdown.addEventListener('change', function () {
    const selectedTag = this.value;

    projectItems.forEach(item => {
      const tags = item.getAttribute('data-tags').split(',');
      if (selectedTag === 'all' || tags.includes(selectedTag)) {
        item.style.display = 'list-item';
      } else {
        item.style.display = 'none';
      }
    });
  });
});
</script>
