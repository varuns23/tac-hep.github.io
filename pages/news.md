---
permalink: /news.html
layout: default
title: "News, Featured Stories and Links"
---

<h1>News, Featured Stories and Links</h1>
{% for post in site.posts %}
  <div>
    <h4><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></h4>
    <h6><i>{{ post.date | date_to_long_string }}</i></h6>
    {% if post.image %}
    <img src="{{ site.baseurl }}{{post.image}}" style="float:left; margin-left: 10px; margin-right: 10px; width: 35%; max-width: 200px;">
    {% else %}
    <img src="{{ site.baseurl }}/assets/images/Tprime-200pu-PhaseII-black-arctic-main-image-small.jpg" style="float:left; margin-left: 10px; margin-right: 10px; width: 10%">
    {% endif %}
    {% if post.summary %}
        {{ post.summary | markdownify }}
    {%- else %}
        {{ post.excerpt | strip_html }}
    {%- endif %}
    <div style="float: right;">
    <a href="{{ site.baseurl }}{{post.url}}">Read more</a>
    </div>
    <div style="clear:both"></div>
  </div>
  <hr>
{% endfor %}
