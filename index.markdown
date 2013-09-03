---
layout: main
title: Oculata Certitudine
---

{% for post in site.posts %}
  <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
  <p class="byline">By Nathan | {{ post.date | date_to_long_string }}</p>

  {{ post.content | split:'<!--more-->' | first }}

  <div class="postfoot postflow">
    <a href="{{ post.url }}">...read the whole post</a>
  </div>
{% endfor %}
