---
layout: post
title: Testing
---

{% capture posts %}
  {% for post in site.posts %}
    |{{ post.title }}#{{ post.url }}
  {% endfor %}
{% endcapture %}
{% assign sortedposts = posts | split: '|' | sort %}
{% for post in sortedposts %}
    {% assign postitems = post | split: '#' %}
    <a href={{ postitems[1] }}">{{ postitems[0] }}</a><br>
{% endfor %}
