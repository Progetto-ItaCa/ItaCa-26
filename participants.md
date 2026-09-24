---
title: Participants
permalink: /Participants/

layout: page
---

{% assign ps = site.data.participants | sort: 'surname' %}

{% for p in ps %}
{% if p.affiliation %}
* {{p.name}} {{p.surname}} ({{p.affiliation}})
{% else %}
* {{p.name}} {{p.surname}}
{% endif %}
{% endfor %}
