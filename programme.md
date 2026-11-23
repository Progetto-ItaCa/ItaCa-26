---
title: Programme
permalink: /programme/
layout: page
---

{% assign all_talks = site.data.talks.accepted %}

{% if site.data.talks.invited %}
  {% assign all_talks = all_talks | concat: site.data.talks.invited %}
{% endif %}

{% for day in site.data.schedule %}

<h3 class="programme-day">{{ day.day }}</h3>

<table class="programme-table">
  <tbody>
  {% for slot in day.slots %}

    <tr class="programme-{{ slot.type }}">
      <td class="programme-time">{{ slot.start }}</td>
      <td class="programme-time">{{ slot.end }}</td>

      <td class="programme-details">

        {% if slot.type == "talk" or slot.type == "guest" %}

          {% assign t = all_talks | where: "slot", slot.id | first %}

          {% if t %}

            <span class="programme-speaker">
              {{ t.author.name }} {{ t.author.surname }}
              {% if slot.type == "guest" %}
                <span class="programme-guest-label">Guest talk</span>
              {% endif %}
            </span>

            {% if t.title %}
              {% if t.abs %}
                <a class="programme-title"
                   href="{{ '/assets/abstracts/' | append: t.abs | relative_url }}"
                   target="_blank" rel="noopener">
                  {{ t.title }}
                </a>
              {% else %}
                <span class="programme-title">{{ t.title }}</span>
              {% endif %}
            {% endif %}

          {% else %}

            {% if slot.type == "guest" %}
              Guest talk
            {% else %}
              Talk {{ slot.id }}
            {% endif %}

          {% endif %}

        {% else %}

          {{ slot.label }}

        {% endif %}

      </td>
    </tr>

  {% endfor %}
  </tbody>
</table>

{% endfor %}

<p class="programme-note">
  Coffee breaks are offered by the organisers.
  Lunch is not provided.
</p>