---
layout: media
title: My project
permalink:
categories:
modified:
excerpt:
image:
  feature:
  teaser:
  thumb:
---

<div class="tiles">
{% for post in site.categories.project%}
	{% include post-grid.html %}
{% endfor %}
</div><!-- /.tiles -->
