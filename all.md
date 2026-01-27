---
title: All Posts
---

{% assign chronologicalPosts = site.posts | reversed %}
{% assign postsByMonth = chronologicalPosts | group_by_exp: "post", "post.date | date: '%B'" %}

{% for month in postsByMonth %}
  <section class="archive-month">
    <h2>{{ month.name }}</h2>
    <ul class="post-list">
      {% for post in month.items %}
        <li>
          <strong>Day {{ forloop.index }}</strong>: 
          <a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a> 
          <small>({{ post.date | date: "%b %d" }})</small>
        </li>
      {% endfor %}
    </ul>
  </section>
{% endfor %}