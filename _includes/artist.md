{% assign _artist = site.data.artist[page.key] %}
<div class="usa-grid-full">
<div class="usa-width-one-half">
### Biography
{{ _artist.biography }}
</div>
<div class="usa-width-one-half">
<img src="{{ '/media/artists/' | append: _artist.image | relative_url }}" class="right mr3 thumbnail-artist" alt=""/>
</div>
</div>

### Genres

<ul>
{% assign _genres = _artist.genres | sort %}
{% for genre in _genres %}
<li><a href="{{ '/artists/#' | append: genre | replace: ' ', '_' | relative_url }}">{{ genre }}</a></li>
{% endfor %}
</ul>

### Art

{% if _artist.works.size > 0 %}
{% for work in _artist.works %}
{% assign _art = site.data.art[work] %}
<div class="example-container">
<div class="usa-grid-full">

<aside class="usa-width-one-third usa-layout-docs-sidenav py3 sticky pr5 lg-show clearfix">
<a href="{{ '/media/art/' | append: _art.image | relative_url }}">
<img src="{{ '/media/art/' | append: _art.image | relative_url }}" class="thumbnail-art" alt=""/>
</a>
</aside>

<div class="usa-width-two-thirds usa-layout-docs-main_content clearfix">
##### Title
{{ _art.title }}
##### Brief description
{{ _art.description | truncate: '255' }}
</div>

</div>
</div>
{% endfor %}
{% else %}
Sorry, we do not currently have any works for this artist.
{% endif %}

{% if site.data.resources[page.resources] %}
### Resources
{% endif %}
