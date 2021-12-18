---
layout: post
permalink: /list/monsters-beast
title: Beasts
---


Plants and animals. To view them sorted by climate, see the lists [here](/pages/fantasylandgenerator/).

<ins>Common Traits</ins>: Few immunities and resistances. Swarms resist single target attacks. Crawling insects detect movement. Plants resist mind and detect movement.

<ins>Encounter Table</ins>. Roll every 30 minute in a dungeon or in every hex during hexcrawl.

<ins>Salvaging the Body</ins>. Tells if the beast is edible and what can be crafted from its body.

<ins>Totem Table</ins>. Use to flesh local culture, and flavor magic items and druid magic.

<ins>Beasts</ins>

{% capture posts %}
  {% for post in site.tags.beast %}
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
 
<ins>Plants</ins>

 {% capture posts %}
  {% for post in site.tags.plant %}
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
