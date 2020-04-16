---
layout: page
title: Webinar
lang: it
ref: startup-webinar
permalink: /it/restart/webinar
child_of_ref: restart
order: 2
---

<div class="card-columns">
  {% for webinar in site.data.startup.webinars %}
  {% assign member = webinar.coordinator | downcase | replace: ' ', '-' %}
  <div class="card border rounded">
    {% if webinar.image != nil and webinar.image != "" %}
    <img class="card-img-top" src="/assets/images/restart/{{ webinar.ref }}.{{ webinar.image }}" alt="{{ webinar.title }}">
    {% endif %}
    <div class="card-body">
      {% if webinar.permalink %}
        <a href="{{ webinar.permalink }}" class="card-link"><h5 class="card-title">{{ webinar.title }}</h5></a>
      {% else %}
        <h5 class="card-title">{{ webinar.title }}</h5>
      {% endif %}

      {% if webinar.description != nil and webinar.description != "" %}
      <p>{{ webinar.description }}</p>
      {% endif %}

      {% if webinar.date != nil and webinar.date != "" %}
      <p>{{ webinar.date }}</p>
      {% endif %}

        {% for social-link in member.social-links %}
        <!--<li class="list-inline-item">
          <a href="{{ social-link[1] }}" title="{{ social-link[0] }}" target="_blank">
            <svg class="icon"><use xlink:href="{{ site.baseurl }}/assets/bootstrap-italia/dist/svg/sprite.svg#it-{{ social-link[0] }}"></use></svg>
            <span class="sr-only">{{ social-link[0] }}</span>
          </a>
        </li>-->
        <a href="{{ social-link[1] }}" title="{{ social-link[0] }}" target="_blank">{{ social-link[0] }} </a>
        {% endfor %}

    </div>
  </div>
  {% endfor %}
</div>