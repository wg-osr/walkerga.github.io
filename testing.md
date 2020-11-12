---
layout: post
title: Testing
---

{% capture posts %}
  {% for post in site.tags.animorphosis %}
  ø{{ post.title }}#{{ post.url }}
  {% endfor %}
{% endcapture %}
{% assign sortedposts = posts | split: 'ø' | sort %}
{% for post in sortedposts %}
    {% assign postitems = post | split: '#' %}
    <a href={{ postitems[1] }}">{{ postitems[0] }}</a><br>
{% endfor %}
