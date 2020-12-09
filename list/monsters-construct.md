---
layout: post
permalink: /list/monsters-construct
title: Constructs
---

Machines and animated objects.

<ins>Common Traits</ins>: Immunity to poison, diseases or sleep. Weakness to anti-magic. Considered an object.

<ins>Encounter Table</ins>. Roll every 30 minute in a dungeon or in every hex during hexcrawl.

<ins>Contruction Table</ins>. Provide instruction for the [Build One](https://saltygoo.github.io/2020/11/10/extra-rules/#between-adventures) carousing activity. Roll for malfunctions.

{% capture posts %}
  {% for post in site.tags.construct %}
    |{{ post.title }}#{{ post.url }}
  {% endfor %}
{% endcapture %}
{% assign sortedposts = posts | split: '|' | sort %}
<ol>
{% for post in sortedposts %}
{% assign postitems = post | split: '#' %}
{% unless forloop.first %}
  <li> <a href="{{ postitems[1] }}"> {{ postitems[0] }}</a></li>
{% endunless %}
{% endfor %}
</ol>
 
