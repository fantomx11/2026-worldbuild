---
title: All Posts
permalink: /posts/
---

{% assign sortedPosts = site.posts | sort: "date" %}
{% assign postsByMonth = sortedPosts | group_by_exp: "post", "post.date | date: '%B'" %}

{% for month in postsByMonth %}
  <section class="archive-month">
    <h2>{{ month.name }}</h2>
    <ol class="post-list">
      {% for post in month.items %}
        <li>
          <strong>Day {{ post.date | date: "%d" }}</strong>: 
          <a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a> 
        </li>
      {% endfor %}
    </ol>
  </section>
{% endfor %}