---
layout: post
title: Testing v3
---

{% capture posts %}
  {% for post in site.tags.animorphosis %}
  |{{ post.title }}#{{ post.url }}
  {% endfor %}
{% endcapture %}
{% assign sortedposts = posts | split: '|' | sort %}
{% for post in sortedposts %}
    {% assign postitems = post | split: '#' %}
    <a class="post-title" href="{{ site.baseurl }}{{ post.url }}">
{% endfor %}
