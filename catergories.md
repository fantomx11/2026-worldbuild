---
title: Posts by Category
permalink: /categories/
---

{% assign categories = site.categories | sort %}

<div class="category-list">
  {% for category in categories %}
    <a href="#{{ category[0] | slugify }}">{{ category[0] | capitalize }}</a>
  {% endfor %}
</div>

<hr>

{% for category in categories %}
  <h2 id="{{ category[0] | slugify }}">{{ category[0] | capitalize }}</h2>
  <ul>
    {% for post in category[1] %}
      <li><a href="{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
  </ul>
{% endfor %}