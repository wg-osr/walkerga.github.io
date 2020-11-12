---
layout: page
title: Classes
permalink: /classes/
---

- The [Fighter](/class/fighter)
- The [Magic User](/class/magic-user)
   - The [Wizard](/class/magic-user/wizard)
- The [Specialist](/class/specialist)

<div class="tags-expo-section">
    {% for tag in site.tags %}
    <h2 id="{{ tag[0] | slugify }}">{{ tag | first }}</h2>
    <ul class="tags-expo-posts">
      {% for post in tag[1] %}
        <a class="post-title" href="{{ site.baseurl }}{{ post.url }}">
      <li>
        {{ post.title }}
      </li>
      </a>
      {% endfor %}
    </ul>
    {% endfor %}
  </div>

