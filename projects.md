---
layout: page
title: Projects
permalink: /projects/
---
<>
<div class="timeline">

{% assign sorted = site.projects | sort: "start-date" | reverse %}
{% for project in sorted %}

  <div class="timeline-item project-card"
       data-tags="{{ project.tags | join: ',' }}"
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
          <span class="tag" data-tag="{{ tag }}">
            {{ tag | replace: '-', ' ' }}
          </span>
        {% endfor %}
      </div>
    </div>

  </div>

{% endfor %}
</div>
<script>
document.querySelectorAll('.tag').forEach(tag => {
  tag.addEventListener('click', () => {
    const selected = tag.dataset.tag;

    document.querySelectorAll('.project-card').forEach(card => {
      const tags = card.dataset.tags.split(',');

      card.style.display =
        tags.includes(selected) ? 'block' : 'none';
    });
  });
});
</script>
