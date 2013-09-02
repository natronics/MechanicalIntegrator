---
layout: main
title: home
---

{% for post in site.posts %}
  <h2>{{ post.title }}</h2>
  <p class="byline">By Nathan | {{ post.date }}</p>
  {{ post.content }}
{% endfor %}
