---
layout: post
title: Testing v7
---

{% capture posts %}
  {% for post in site.tags.animorphosis %}
    |{{ post.title }}#{{ post.url }}
  {% endfor %}
{% endcapture %}
<ol>
{% for post in posts %}
<a class="post-title" href="{{ site.baseurl }}{{ post.url }}">
<li> {{ post.title }} </li>
</a>
{% endfor %}
</ol>
