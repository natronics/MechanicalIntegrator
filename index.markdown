---
layout: main
title: home
---

{% for post in site.posts %}
  <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
  <p class="byline">By Nathan | {{ post.date | date_to_long_string }}</p>

  {{ post.content }}

  <p class="keepreading">
    ... <a href="{{ post.url }}">Read the whole Post</a>
  </p>
{% endfor %}
