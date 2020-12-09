---
layout: post
permalink: /list/monsters-elemental
title: Elementals
---

Sentient raw matter.

<ins>Common Traits</ins>: Resistance to all damage. Decay outside of its element.

<ins>Encounter Table</ins>. Roll every 30 minute in a dungeon or in every hex during hexcrawl.

<ins>What the Monster Wants Table</ins>. Roll to give it a goal.

<ins>Binding Table</ins>. Provide instruction for the [Binding](https://saltygoo.github.io/2020/11/10/extra-rules/#between-adventures) carousing activity. Roll for the consequences.

A variation of the [Conjure](https://saltygoo.github.io/2020/11/12/conjure/) spell unique to the elemental type is included in each monster sheet.

{% capture posts %}
  {% for post in site.tags.elemental %}
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
 
