---
layout: page
permalink: /list/arctic
title: Arctic Monsters
---

### All Monsters

{% capture posts %}
  {% for post in site.tags.arctic %}
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

### Just Beasts

{% capture posts %}
{% for post in site.posts %}
    {% if post.tags contains "beast" and post.tags contains "arctic" %}
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
