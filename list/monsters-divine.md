---
layout: post
permalink: /list/monsters-celestial
title: Divine Creatures
---

Entities of order that enforce the laws of the gods. Angels and the lawful devils of DnD are celestials.

<ins>Common Traits</ins>: They resist everything.

<ins>Encounter Table</ins>. Roll every 30 minute in a dungeon or in every hex during hexcrawl.

<ins>Quest & Reward Tables</ins>. Roll as the consequence of the [Negotiate a Pact](https://saltygoo.github.io/2020/11/10/extra-rules/#between-adventures) carousing activity and whenever appropriate. The quest table can be used to determine the celestial's current goal, the reward table can be rolled for loot.

{% capture posts %}
  {% for post in site.tags.celestial %}
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
 
