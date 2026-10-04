---
title: News
permalink: /news/
---

# News

{% assign sorted_news = site.news | sort: 'date' | reverse %}

{% if sorted_news.size > 0 %}
{% for item in sorted_news %}
<div class="news-item">
<h3><a href="{{ item.url }}">{{ item.title }}</a></h3>
<p class="news-date">{{ item.date | date: "%B %d, %Y" }}</p>
<p>{{ item.excerpt }}</p>
</div>
{% endfor %}
{% else %}
<p>No news yet.</p>
{% endif %}

<style>
  .news-item {
    margin-bottom: 2rem;
    padding-bottom: 2rem;
    border-bottom: 1px solid #eee;
  }

  .news-item:last-child {
    border-bottom: none;
  }

  .news-item h3 {
    margin: 0 0 0.5rem 0;
  }

  .news-item h3 a {
    text-decoration: none;
    color: #222;
  }

  .news-item h3 a:hover {
    text-decoration: underline;
  }

  .news-date {
    color: #666;
    font-size: 0.9em;
    margin: 0;
  }

  .news-item p {
    margin: 0.5rem 0 0 0;
  }
</style>
