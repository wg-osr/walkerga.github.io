---
layout: post
title: Testing v11
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
   <li> <a href={{ postitems[1] }}> {{ postitems[0] }} 
</a></li>
{% endfor %}
</ol>
