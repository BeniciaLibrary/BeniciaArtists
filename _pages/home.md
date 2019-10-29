---
title: Home
layout: base
permalink: /
---

<section class="usa-section home-hero bg-blue-light" markdown="0">
  <div class="usa-grid">
    <h1 class="mb4">{{ site.description }}</h1>
    <a class="usa-button usa-button-big usa-button-primary m0 no-print" href="{{ '/about/' | relative_url }}">Learn more</a>
  </div>
</section>

<section class="usa-section home-grid" markdown="0">
{% assign rows = 2 %}
{% for i in (1..rows) %}
  {% assign offset = forloop.index0 | times: 2 %}
  <div class="usa-grid md-flex">
    {% for artist in site.data.artists limit: 2 offset: offset %}
    {% assign _artist = site.data.artist[artist.key] %}
    <a href="{{ '/artists/' | append: _artist.key | relative_url }}" class="usa-width-one-half p3 lg-p4 clearfix">
      <img class="home-featured" src="{{ '/media/artists/' | append: _artist.image | relative_url }}"/>
      <div class="overflow-hidden">
        <h3 class="arrow">{{ _artist.name }}</h3>
        <p class="my0">{{ _artist.biography | truncate: 255 }}</p>
      </div>
    </a>
    {% endfor %}
  </div>
{% endfor %}
</section>

<section class="usa-section bg-tan home-events" markdown="0">
  <div class="usa-grid">
    <h2 class="mt0 mb3">Recent and upcoming events</h2>
    {% assign events = site.data.events | sort: 'date' %}
    {% assign events_sorted = events | reverse %}
    {% for event in events_sorted %}
      <p class="m0 h5 caps sans-serif">{{ event.date | date: "%B %e, %Y" }}</p>
      <h4 class="m0 h3">{% if event.link %}<a href="{{ event.link }}" class="text-decoration-none">{% endif %}{{ event.title }}{% if event.link %}</a>{% endif %}</h4>
      {% if event.description %}{{ event.description | markdownify }}{% endif %}
    {% endfor %}
  </div>
</section>
