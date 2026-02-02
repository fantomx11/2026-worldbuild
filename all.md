---
title: All Posts
permalink: /posts/
---

{% assign sortedPosts = site.posts | sort: "date" %}
{% assign postsByMonth = sortedPosts | group_by_exp: "post", "post.date | date: '%B'" %}

{% for month in postsByMonth %}

  {% case month.name %}
    {% when "January" %}{% assign subtitle = " - Hawjio" %}
    {% when "February" %}{% assign subtitle = " - Sa'ngirr" %}
    {% when "March" %}{% assign subtitle = "" %}
    {% when "April" %}{% assign subtitle = "" %}
    {% when "May" %}{% assign subtitle = "" %}
    {% when "June" %}{% assign subtitle = "" %}
    {% when "July" %}{% assign subtitle = "" %}
    {% when "August" %}{% assign subtitle = "" %}
    {% when "September" %}{% assign subtitle = "" %}
    {% when "October" %}{% assign subtitle = "" %}
    {% when "November" %}{% assign subtitle = "" %}
    {% when "December" %}{% assign subtitle = "" %}
    {% else %}{% assign subtitle = "" %}
  {% endcase %}
  
  <section class="archive-month">
    <h2>{{ month.name }}{{ subtitle }}</h2>
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

