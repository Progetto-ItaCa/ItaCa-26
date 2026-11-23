---
title: Speakers
permalink: /speakers/
layout: page
---

{% assign talks = site.data.talks.accepted %}

{% if site.data.talks.invited %}
  {% assign talks = talks | concat: site.data.talks.invited %}
{% endif %}

{% assign authors = talks | map: 'author' | sort: 'surname' %}

<div class="speaker-list">

{% for author in authors %}
  {% for t in talks %}

    {% if t.author.name == author.name and t.author.surname == author.surname %}

      <div class="speaker-entry">

        <div class="speaker-heading">
          <span class="speaker-name">
            {{ t.author.name }} {{ t.author.surname }}
          </span>

          {% if t.slot == "guest" %}
            <span class="programme-guest-label">Guest talk</span>
          {% endif %}
        </div>

        {% if t.author.affiliation %}
          <span class="speaker-affiliation">
            {{ t.author.affiliation }}
          </span>
        {% endif %}

        {% if t.abs %}
          <a class="speaker-talk-title"
             href="{{ '/assets/abstracts/' | append: t.abs | relative_url }}"
             target="_blank" rel="noopener">
            {{ t.title }}
          </a>
        {% else %}
          <span class="speaker-talk-title">{{ t.title }}</span>
        {% endif %}

      </div>

    {% endif %}

  {% endfor %}
{% endfor %}

</div>