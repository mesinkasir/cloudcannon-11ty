---
layout: layouts/start.njk
eleventyNavigation:
  key: Home
  order: 1
pagination:
  data: collections.posts
  size: 9
  alias: posts
---

{% include "widget/banner.njk" %}

<div class="container bg-white">
<div class="row">
{% for post in posts %}
<a href="{{ post.url | url }}" title="{{post.data.title}}" class="col-md-4 p-3">
{% if post.data.thumb %}<img class="img-fluid zoom" loading="lazy" height="100%" width="100%"
alt="{{post.data.title}}" src="{{post.data.thumb}}">{% endif %}
<div class="p-3">
{% if post.data.title %}<h2 class="lead"><strong>{{ post.data.title }}</strong></h2>{% endif %}
{% if post.data.description %}<h3 class="lead text-dark">{{ post.data.description }}</h3>{% endif %}
</div>
</a>
{% endfor %}
</div>
</div>

<div class="container bg-white">
<div class="row">
<nav aria-label="Page navigation example">
  <ul class="pagination p-3">
{%- for pageEntry in pagination.pages %}
 <li class="page-item"><a class="page-link" href="{{ pagination.hrefs[ loop.index0 ] }}"{% if page.url == pagination.hrefs[ loop.index0 ] %} aria-current="page"{% endif %}>
Page {{ loop.index }}</a></li>
{%- endfor %}
</ul>
</nav>
</div>
</div>
