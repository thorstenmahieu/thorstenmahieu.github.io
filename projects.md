---

layout: page
title: "All Projects"
permalink: projects/
---

<!-- Dropdown Filter -->
<label for="tag-filter">Filter by Tag:</label>
<select id="tag-filter">
  <option value="all" selected>All Tags</option>
</select>

<!-- Projects List -->
<ul id="projects-list">
  {% for project in site.pages %}
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
  uniqueTags.forEach(tag => {
    const option = document.createElement('option');
    option.value = tag;
    option.textContent = tag.charAt(0).toUpperCase() + tag.slice(1); // Capitalize first letter
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
