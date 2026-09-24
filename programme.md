---
title: Programme 
permalink: /programme/

layout: page
---

{%- assign abs_url = '/assets/abstracts/' -%}
{%- if site.data.talks.invited -%}
  {%- assign all_talks = site.data.talks.accepted | concat: site.data.talks.invited -%}
{%- else -%}
  {%- assign all_talks = site.data.talks.accepted -%}
{%- endif -%}

**Note**: all coffee breaks are offered by the organisation, while the lunch is not.

<br>
{%- assign t = all_talks | where_exp: "item", "item.slot == 3"  -%}
{{ t }} 


<table>
  <tbody>
{%- for d in site.data.schedule -%}
<tr> <th colspan="2"> {{ d.day }} </th> </tr>
{%- for slot in d.slots -%}
{%- if slot.type == "talk" -%}
{%- assign t = all_talks | where_exp: "item", "item.slot == slot.id" | first -%}
<tr>
  <td>{{ slot.time }}</td>
  <td>
    {%- if t -%}
      <a href="{{ t.abs | prepend: abs_url | relative_url }}" target="_blank">{{ t.author.name }} {{ t.author.surname }}</a>
    {%- else -%}
      TBA
    {%- endif -%}
  </td>
</tr>
{%- else -%}
<tr>
  <td><strong>{{ slot.time }}</strong></td>
  <td><strong>{{ slot.type }}</strong></td>
</tr>
{%- endif -%}
{%- endfor -%}
{%- endfor -%}
  </tbody>
</table>

