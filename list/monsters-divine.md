---
layout: post
permalink: /list/monsters-celestial
title: Divine Creatures
---

Entities of order that enforce the laws of the gods. Angels and Devils, depending on your point of view.

<ins>Common Traits</ins>: They resist everything.

<ins>Encounter Table</ins>. Roll every 30 minute in a dungeon or in every hex during hexcrawl.

<ins>Quest & Reward Tables</ins>. Roll as the consequence of the [Negotiate a Pact](https://saltygoo.github.io/2020/11/10/extra-rules/#between-adventures) carousing activity and whenever appropriate. The quest table can be used to determine the celestial's current goal, the reward table can be rolled for loot.

<details markdown="1">
<summary>Greater Divine Servants</summary>
{% capture posts %}
{% for post in site.posts %}
    {% if post.tags contains "celestial" and post.tags contains "greater" %}
    |{{ post.title }}#{{ post.url }}
    {% endif %}
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
</details>

<details markdown="1">
<summary>Lesser Divine Servants</summary>
{% capture posts %}
{% for post in site.posts %}
    {% if post.tags contains "celestial" and post.tags contains "lesser" %}
    |{{ post.title }}#{{ post.url }}
    {% endif %}
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
</details>

---

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
 
