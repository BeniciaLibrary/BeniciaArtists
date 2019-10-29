---
title: Artists
permalink: /artists/
sidenav: artists
---

### History

{{ site.data.descriptions.history }}

### Directory

This is the currently maintained list of artists. If you'd like to be added to, or to propose adding someone to this list, please [contact us](mailto:{{ site.email }}) or review our [contributing guidelines]({{ site.baseurl }}/about#contributions).

{% assign _genres = site.data.genres | sort: 'name' %}
{% for genre in _genres %}
<h4 id="{{ genre.name | replace: ' ', '_' }}">{{ genre.name }}</h4>
<ul class="usa-accordion-bordered mt4">
{% assign _artists = genre.artists | sort %}
{% for key in _artists %}
{% assign _artist = site.data.artist[key] %}
<li>
<button class="usa-accordion-button list-artist" aria-expanded="false">
<a href="{{ '/artists/' | append: _artist.key | relative_url }}" style="text-decoration: none;">{{ _artist.name }}</a>
</button>
</li>
{% endfor %}
</ul>
{% endfor %}
