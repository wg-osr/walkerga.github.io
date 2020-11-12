---
layout: page
title: Classes
permalink: /classes/
---

- The [Fighter](/class/fighter)
- The [Magic User](/class/magic-user)
   - The [Wizard](/class/magic-user/wizard)
- The [Specialist](/class/specialist)

{% for tag in tags %}
	<h2 id="{{ tag | slugify }}">{{ tag }}</h2>
	<ul>
	 {% for post in site.posts %}
		 {% if post.tags contains tag %}
		 <li>
		 <h3>
		 <a href="{{ post.url }}">
		 {{ post.title }}
		 </a>
		 {% for tag in post.tags %}
			 <a class="tag" href="/_post/tags/#{{ tag | slugify }}">{{ tag }}</a>
		 {% endfor %}
		 </h3>
		 </li>
		 {% endif %}
	 {% endfor %}
	</ul>
{% endfor %}
