---
permalink: /trainees.html
layout: default
title: TAC/HEP Traineeship Program
---

# TAC-HEP Traineeship Program

{% assign members = site.trainees | where_exp:"item", "item.active and item.hidden != true"
                                     | last_name_sort: "name" %}
{% assign former_members = site.trainees | where_exp: "item", "item.active == nil or item.active == false and item.hidden != true"
                                  | last_name_sort: "name" %}


<h1>TAC-HEP Trainees</h1><br>

<div class="container-fluid">
<div class="row">
{% for person in members %}
    {% include standard_person_card.md person=person %}
{% endfor %}
</div>
</div>

{%- comment -%}
<h1>Former Collaborators</h1><br>

<div class="container-fluid">
<div class="row">
{% for person in former_members %}
    {% include standard_person_card.md person=person %}
{% endfor %}
</div>
</div>
{%- endcomment -%}

