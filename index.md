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
{% include "widget/blogger.njk" %}
{% include "widget/pagination.njk" %}
