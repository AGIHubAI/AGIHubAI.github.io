---
title: Rooms
permalink: /rooms/
---

# Topic Rooms

{% if site.rooms.size > 0 %}
  {% for item in site.rooms %}
    <div class="room-item">
      <h3><a href="{{ item.url }}">{{ item.title }}</a></h3>
      <p>{{ item.excerpt }}</p>
    </div>
  {% endfor %}
{% else %}
  <p>No topic rooms yet.</p>
{% endif %}

<style>
  .room-item {
    margin-bottom: 2rem;
    padding-bottom: 2rem;
    border-bottom: 1px solid #eee;
  }

  .room-item:last-child {
    border-bottom: none;
  }

  .room-item h3 {
    margin: 0 0 0.5rem 0;
  }

  .room-item h3 a {
    text-decoration: none;
    color: #222;
  }

  .room-item h3 a:hover {
    text-decoration: underline;
  }

  .room-item p {
    margin: 0.5rem 0 0 0;
  }
</style>
