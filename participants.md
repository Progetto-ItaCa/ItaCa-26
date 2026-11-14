---
title: Participants
permalink: /Participants/

layout: page
---

{% assign ps = site.data.participants | sort: 'surname' %}

<div class="participant-grid">
{% for p in ps %}
  <div class="participant">
    <span class="participant-name">{{ p.name }} {{ p.surname }}</span>
    {% if p.affiliation %}
      <span class="participant-affiliation">{{ p.affiliation }}</span>
    {% endif %}
  </div>
{% endfor %}
</div>