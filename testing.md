---
layout: post
title: Testing v3
---

{% capture posts %}
  {% for post in site.tags.animorphosis %}
  |{{ post.title }}#{{ post.url }}
  {% endfor %}
{% endcapture %}
{% assign sortedposts = posts | split: '|' | sort %}
<ol>
  {% for post in sortedPosts %}
  <li><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></li>
{% endfor %}
</ol>
