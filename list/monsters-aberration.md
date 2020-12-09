---
layout: post
permalink: /list/monsters-aberration
title: Aberrations
---

Eldritch horrors and mutants. The chaotic demons of DnD are aberrations.

<ins>Common Traits</ins>: Resistance to mind effects. Save vs fear to kill.

<ins>Encounter Table</ins>. Roll every 30 minute in a dungeon or in every hex during hexcrawl.

<ins>Mutation Table</ins>. Roll as the consequence of the [Researching Eldritch Knowledge](https://saltygoo.github.io/2020/11/10/extra-rules/#between-adventures) carousing activity and whenever appropriate.

{% capture posts %}
  {% for post in site.tags.aberration %}
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
 
