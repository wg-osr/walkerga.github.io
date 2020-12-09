---
layout: post
permalink: /list/monsters-humanoid
title: Humanoids
---

Like beasts, but capable of speech and communal living.

<ins>Common Traits</ins>: No or few immunities and resistances. Giants have extra HP.

<ins>Encounter Table</ins>. Roll every 30 minute in a dungeon or in every hex during hexcrawl.

<ins>Loot Table</ins>. Roll for equipment.

<ins>Culture Table</ins>. Roll to generate a variety of unique cultures with immediate tension in your world.

Each humanoid has a [class version](https://saltygoo.github.io/classes/) for players to play as them.

{% capture posts %}
  {% for post in site.tags.humanoid %}
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
 
