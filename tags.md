---
layout: page
title: "Tags"
permalink: /tags/
---

<h1>Tags</h1>
<ul>
  {% assign tags = site.posts | map: "tags" | join: "," | split: "," | uniq | sort %}
  {% for tag in tags %}
    <li><a href="/tags/{{ tag | downcase | slugify }}/">{{ tag }}</a></li>
  {% endfor %}
</ul>
