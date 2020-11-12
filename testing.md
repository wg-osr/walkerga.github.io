---
layout: post
title: Testing v12
---

{% capture posts %}
  {% for post in site.tags.animorphosis %}
    |{{ post.title }}#{{ post.url }}
  {% endfor %}
{% endcapture %}
{% assign sortedposts = posts | split: '|' | sort %}
<ol>
{% for post in sortedposts %}
{% assign postitems = post | split: '#' %}
   <li> <a class="post-title" href="{{ site.baseurl }}{{ post.url }}"></li>
{% endfor %}
</ol>
