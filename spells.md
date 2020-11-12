---
layout: page
title: Spells
permalink: /spells/
---

---

# Spell Schools 
### 1. Animorphosis 
All iterations of [animal] should be replaced by a specific animal specie when the spell is first found.
<ol>
{% capture posts %}
{% for post in site.tags.animorphosis %}
|{{ post.title }}#{{ post.url }}
  {% endfor %}
{% endcapture %}
{% assign sortedposts = posts | split: '|' | sort %}
{% for post in sortedposts %}
    {% assign postitems = post | split: '#' %}
<li> <a class="post-title" href="{{ postitems[1] }}">{{ postitems[0] }}
{{ post.title }} </li>
</a>
{% endfor %}
</ol>

### 2. Apotropaism
### 3. Cunning Craft
### 4. Diabolism
### 5. Elementalism
### 6. Necromancy
### 7. Physiurgy
### 8. Psychomancy
### 9. Rope Tricks
### 10. Spiritualism
### 11. Translocation
### 12. Vivimancy

<br>

---

### Lexicon

<ins>R</ins> : Range	  <ins>D</ins> : Duration

<ins>[dice]</ins> : the number of rolled dices.

<ins>[sum]</ins> : the sum of the rolled dices.

<ins>Sigil</ins> : Your unique symbol. It takes 10 minute to scribe and you can only have one per Magic User level at a time. It is permanent until you cast a sigil spell above your limit. If you do, the oldest sigil fades but is still visible.

<ins>Valuable / Treasure</ins> : Means the spell uses a component worth [valuables or treasures](/2020/11/10/extra-rules/).

<ins>HD</ins> : Means Hit Dice, the level of the monster, which the Referee knows. The minimum level is 1.

<ins>Catastrophe</ins> : Terrible consequences for misusing magic. Happens when a spell creates a paradox, or when more dices are cast than allowed.

<ins>Duration Philosophy</ins> : Each duration unit reflects the intended use of the spell:
- <ins>rounds</ins> is for in combat.
- <ins>minutes</ins> is for conversation and is measured in real time.
- <ins>10 minutes</ins> is for exploration (a battle takes 10 minutes, exploring a room takes 10 minutes, etc).
- <ins>hours</ins> is for between rests. A game session.
- <ins>sigil</ins> is permanent, but are capped by the number of Magic User templates.

<ins>Range Philosophy</ins> : 
A human moves 30’ in a turn, so all ranges are in 30’ increment to ease calculation when playing without a grid.

***The bolden italic words under a spell description are its spell words. You can mix and match the spell words you know to create new spells.***
