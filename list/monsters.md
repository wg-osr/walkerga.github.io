---
layout: post
permalink: /list/monsters
title: All Monsters
---

{% capture pages %}
  {% for page in site.tags.monster %}
    |{{ page.title }}#{{ page.url }}
  {% endfor %}
{% endcapture %}
{% assign sortedpages = pages | split: '|' | sort %}
<ol>
{% for page in sortedpages %}
{% assign pageitems = page | split: '#' %}
{% unless forloop.first %}
  <li> <a href="{{ pageitems[1] }}"> {{ pageitems[0] }}</a></li>
{% endunless %}
{% endfor %}
</ol>
 
