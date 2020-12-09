---
layout: post
permalink: /list/monsters-undead
title: All Undeads
---

Other monster types brought back to life.

<ins>Common Traits</ins>: Cannot die of natural causes. Ethereal undeads are immune to nearly everything, mindless undeads are immunte to mind effects.

<ins>Encounter Table</ins>. Roll every 30 minute in a dungeon or in every hex during hexcrawl.

<ins>What the Monster Wants Table</ins>. Roll to give the creature a goal.

All undead pages include a variation of the [Occult Consultation](https://saltygoo.github.io/2020/11/13/occult-consultation/) or [Lichcraft](https://saltygoo.github.io/2020/11/13/lichcraft/) spells unique to the undead type you want to create or summon, or instructions on how to become one.

{% capture posts %}
  {% for post in site.tags.undead %}
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
 
