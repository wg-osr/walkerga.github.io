---
layout: post
title: Testing v4
---

{% assign sortedposts = posts | split: '|' | sort %}
<ol>
  {% for post in sortedPosts %}
  <li><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></li>
{% endfor %}
</ol>
