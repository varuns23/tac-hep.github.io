---
permalink: /about/team_alphabetical.html
layout: people
title: Institute Team
---

{% include institution_list.html %}
{% assign members = site.data.people | values
                                     | where_exp:"item", "item.active"
                                     | where_exp:"item", "item.hidden != true"
                                     | last_name_sort: "name" %}

<h1>Full Team</h1><br>

<div class="container-fluid">
<div class="row">
{% for person in members %}
    {% include standard_person_card.md person=person %}
{% endfor %}
</div>
</div>

<br>
<h1>Collaborators</h1><br>

{% assign collaborator_list = site.data.collaborators | where_exp:"item", "item.active"
                                                      | last_name_sort: "name" %}

<div class="container-fluid">
  <div class="row">
    {% for person in collaborator_list %}
      {% include standard_person_card.md person=person %}
    {% endfor %}
  </div>
</div>


