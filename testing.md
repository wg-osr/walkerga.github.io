---
layout: post
title: Testing v8
---

{% capture posts %}
  {% for post in site.tags.animorphosis %}
    |{{ post.title }}#{{ post.url }}
  {% endfor %}
{% endcapture %}
{% assign sortedposts = posts | split: '|' | sort %}
<ol>
{% for post in sortedposts %}
{% assign postitems = post | split: '#' %}
    <a href={{ postitems[1] }}"><li> {{ postitems[0] }} </li>
</a>
{% endfor %}
</ol>
