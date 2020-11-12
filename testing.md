---
layout: post
title: Testing v8
---

{% capture posts %}
  {% for post in site.tags.animorphosis %}
    |{{ post.title }}#{{ post.url }}
  {% endfor %}
{% endcapture %}
{% assign sortedposts = posts | split: '|' | sort %}
<ol>
{% for post in sortedposts %}
<a class="post-title" href="{{ site.baseurl }}{{ post.url }}">
<li> {{ post.title }} </li>
</a>
{% endfor %}
</ol>
