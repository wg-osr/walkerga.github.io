---
layout: page
title: The Cleric
permalink: /class/magic-user/cleric
---

###### Adapted from A Blasted, Cratered Land's [version](https://crateredland.blogspot.com/2019/01/the-cleric.html)

The Cleric is a type of [Magic User](/class/magic-user). The religion you follow is represented by 3 [Domains](#domains) over which it claims dominion.

<ins>Starting Equipment</ins><br>
A holy book. Ink & quill. Censer.

<ins>Spell List</ins><br>
The spells listed in each of your religion's Domains.

<ins>Perk</ins><br>
Each Domain has 2 Commandments. For each Commandment you follow while casting a spell, you can add or substract 1 to your dice roll.

<ins>Drawback</ins><br>
Each Domain has a Sin. If you commit it, gain 1 Doom Point and you cant cast spells for as many hours as you have Doom Points.

<ins>Cantrips</ins>
Each Domain gives you a cantrip.

---

## Domains

{% capture posts %}
  {% for post in site.tags.domain %}
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
