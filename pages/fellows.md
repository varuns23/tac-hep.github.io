---
permalink: /fellows.html
layout: default
title: TAC/HEP Fellows Program
---

# TAC-HEP Fellows Program

Bla bla bla


{% assign fellows = site.pages | where: "pagetype", "fellow"
                               | last_name_sort: "fellow-name"
                               | reverse
                               | iris_hep_fellow_sort
                               | reverse %}
{% assign active-fellows = fellows | select: "active" | where_exp: "item", "item.hidden != true" %}
{% assign inactive-fellows = fellows | reject: "active" | where_exp: "item", "item.hidden != true" %}


{%- if active-fellows.size > 0 %}
# Current TAC-HEP Fellows

<div class="container-fluid">
  <div class="row">
    {% for person in active-fellows %}
      <div class="card" style="width: 12rem;">
         <img class="card-img-top" src="{{ site.baseurl }}{{person.photo}}" alt="Card image cap">
         <div class="card-body d-flex flex-column">
           <div class="card-text">
              <b><a href="{{ site.baseurl }}{{person.permalink}}">{{person.fellow-name}}</a></b><br>
              <small>{{person.institution}}</small><br><br>
           </div>
           <div class="card-text mt-auto"><i>
             {% include fellow_dates.html dates=person.dates %}
           </i><br></div>
         </div>
      </div>
    {% endfor %}
  </div>
  <br>
</div>

{% endif %}

# Former TAC-HEP Fellows
<div class="container-fluid">
  <div class="row">
    {% for person in inactive-fellows %}
       <div class="card" style="width: 12rem;">
          <img class="card-img-top" src="{{ site.baseurl }}{{person.photo}}" alt="Card image cap">
          <div class="card-body d-flex flex-column">
            <div class="card-text">
               <b><a href="{{ site.baseurl }}{{person.permalink}}">{{person.fellow-name}}</a></b><br>
               <small>{{person.institution}}</small><br><br>
            </div>
            <div class="card-text mt-auto"><i>
            {% include fellow_dates.html dates=person.dates %}
            </i><br></div>
          </div>
       </div>
    {% endfor %}
  </div>
  <br>
</div>

