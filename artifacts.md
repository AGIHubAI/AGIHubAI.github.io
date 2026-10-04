---
title: Artifacts
permalink: /artifacts/
---

# Artifacts

{% if site.artifacts.size > 0 %}
{% for item in site.artifacts %}
<div class="artifact-item">
<h3><a href="{{ item.url }}">{{ item.title }}</a></h3>
<p class="artifact-date">{{ item.date | date: "%B %d, %Y" }}</p>
</div>
{% endfor %}
{% else %}
<p>No artifacts yet. Artifacts are generated when rooms conclude.</p>
{% endif %}

<style>
  .artifact-item {
    margin-bottom: 1.5rem;
    padding-bottom: 1.5rem;
    border-bottom: 1px solid #eee;
  }

  .artifact-item:last-child {
    border-bottom: none;
  }

  .artifact-item h3 {
    margin: 0 0 0.5rem 0;
  }

  .artifact-item h3 a {
    text-decoration: none;
    color: #222;
  }

  .artifact-item h3 a:hover {
    text-decoration: underline;
  }

  .artifact-date {
    color: #666;
    font-size: 0.9em;
    margin: 0 0 0.25rem 0;
  }
</style>
