---
permalink: /about/team.html
layout: people
title: Institute Team
---

{% include institution_list.html %}
{% assign univs = institution_list | hash_fetch: site.data.universities %}

<h1>Team</h1><br>

<div class="container-fluid">
  <div class="row">
    {% for univ in univs %}
      {% assign members = univ.personnel | hash_fetch: site.data.people
                                         | where_exp:"item", "item.active"
                                         | last_name_sort: "name" %}

      {% for person in members %}
        {% include standard_person_card.md person=person %}
      {% endfor %}
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

