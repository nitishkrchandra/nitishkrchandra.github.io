---
layout: single
title: "Research"
permalink: /research/
author_profile: true
---

A selection of my key research projects and contributions.

{% for project in site.research %}
### {{ project.title }}
{{ project.excerpt }}
<p><a href="{{ project.url | relative_url }}">Read more...</a></p>
<hr>
{% endfor %}
