---
title: Speakers 
permalink: /speakers/

layout: page
---

{%- if site.data.talks.invited -%}
{%- assign invited = site.data.talks.invited | sort: 'author.surname' -%}
## Invited Talks 
{% for t in invited %}
{%- include talk %}
{% endfor %}
{%- endif -%} 


{%- if site.data.talks.accepted -%}
{%- assign accepted = site.data.talks.accepted | sort: 'author.surname' -%} 
## Contributed Talks 
{% for t in accepted %}
{%- include talk %} 
{% endfor %}
{%- endif -%}

{%- if site.data.talks.posters -%}
{%- assign posters = site.data.talks.posters | sort: 'author.surname' -%} 
## Posters 
{% for t in posters %}
{%- include talk %} 
{% endfor %}
{%- endif -%}




