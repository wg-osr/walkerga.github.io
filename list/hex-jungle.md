---
layout: page
permalink: /list/jungle
title: Jungle Monsters
---

<details markdown="1">
<summary>Click here for fauna only</summary>
{% capture posts %}
{% for post in site.posts %}
    {% if post.tags contains "beast" and post.tags contains "jungle" %}
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
  {% for post in site.tags.jungle %}
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
