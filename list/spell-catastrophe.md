---
layout: post
permalink: /list/spell-catastrophe
title: Catastrophes
---

Every time you roll doubles on you Spell Dices, you gain 1 Doom Point. Roll a D20. If you roll equal or below your doom score, you trigger a catastrophe. They will end your wizardly career if you don’t quest to avoid your doom. Choose the following table that makes the most thematic sense:

### You wicked wizard! You attracted the attention of the wrong entity! Roll a D10

1. Your powers have transgressed the limits set to mortals by the divine Authority. Your forehead is branded with heretical writing, recognizable by the learned as an invocation to be judged. If this writing is intoned by a _any_ spellcaster or cleric, a greater divine servant will be summoned.
2. Every time an intelligent life dies from the consequences of one of your spells, the departed soul is fed to a [dretch demon](/monsters/dretch) which is immediately summoned, and confused and ornery from being so disturbed.
3. Anyone that performs a paid service for the you in the future incurs a debt to a devil duke. However, they are not so informed. If they do not discharge the debt, any offspring they have will be replaced with a demon changeling marked with your sigil. 
4. The attention of the demon lord Kezgefligrox is attracted, who can now see whatever the sorcerer sees, and speak using the sorcerer's mouth, though the voice becomes different and ominous. The sorcerer's eyes now glow a faint orange in darkness.
5. One randomly determined person near the casting of the spell is permanently marked with a demonic sigil. This sigil conjures an [imp](/monsters/dretch) each time the afflicted person sleeps. Determine demon reaction as normal.
6. The sorcerer and all allies nearby grow long, curving, goatlike horns. These are permanent, and mark those so affected as traffickers in demon magic.
7. The sorcerer is permanently imbued with the nature of demons, and becomes subject to many demonic weaknesses. For example, holy water becomes damaging, circles of protection keep the sorcerer out, and so forth. Further, the sorcerer loses the ability to cross running water without collapsing into unconsciousness. Crossing a line ofsalt, such as used with some magic circles, causes the sorcerer 1d6 damage.

{% capture posts %}
  {% for post in site.tags.beast %}
    |{{ post.title }}#{{ post.url }}
  {% endfor %}
{% endcapture %}
{% assign sortedposts = posts | split: '|' | sort %}
<ol>
{% for post in sortedposts %}
{% if post.tags contains "jungle" %}
{% assign postitems = post | split: '#' %}
{% unless forloop.first %}
  <li> <a href="{{ postitems[1] }}"> {{ postitems[0] }}</a></li>
{% endunless %}
{% endif %}
{% endfor %}
</ol>

:P
