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

<details markdown="1">
<summary>Minor Elementals</summary>
{% capture posts %}
{% for post in site.posts %}
    {% if post.tags contains "elemental" and post.tags contains "lesser" %}
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
<summary>Major Elementals</summary>
{% capture posts %}
{% for post in site.posts %}
    {% if post.tags contains "elemental" and post.tags contains "greater" %}
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

### All Elementals

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
 
