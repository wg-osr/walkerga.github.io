---
layout: post
permalink: /list/monsters-fey
title: Fairies
---

Sentient raw emotions.

<ins>Common Traits</ins>: Resistance to weapons and spells.

<ins>Encounter Table</ins>. Roll every 30 minute in a dungeon or in every hex during hexcrawl.

<ins>What the Monster Wants Table</ins>. Roll to give it a goal.

<ins>Salvaging the body</ins>. Roll for loot. Instructions on how to learn new unique spell words are always included.

{% capture posts %}
  {% for post in site.tags.fey %}
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
 
