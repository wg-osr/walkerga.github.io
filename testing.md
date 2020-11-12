---
layout: post
title: Testing v5
---

{% capture posts %}
  {% for post in site.tags.animorphosis %}
    |{{ post.title }}#{{ post.url }}
  {% endfor %}
{% endcapture %}
{% assign sortedposts = posts | split: '|' | sort %}
{% for post in sortedposts %}
    {% assign postitems = post | split: '#' %}
    <a href={{ postitems[1] }}">{{ postitems[0] }}</a><br>
{% endfor %}
