---
layout: single
title: "Research"
permalink: /research/
author_profile: true
---

A selection of my key research projects and contributions.

{% for project in site.research %}
<table style="width:100%; border: none;">
  <tr style="border: none;">
    <td style="width: 25%; padding: 10px; border: none; vertical-align: top;">
      {% if project.header.teaser %}
        <img src="{{ project.header.teaser | relative_url }}" alt="Project teaser">
      {% endif %}
    </td>
    <td style="width: 75%; padding: 10px; border: none; vertical-align: top;">
      <h3>{{ project.title }}</h3>
      <p>{{ project.excerpt }}</p>
      <p><a href="{{ project.url | relative_url }}">Read more...</a></p>

      {% if project.links %}
        <p>
        {% for link in project.links %}
          <a href="{{ link.url }}" style="margin-right: 15px;">{{ link.label }}</a>
        {% endfor %}
        </p>
      {% endif %}

    </td>
  </tr>
</table>
<hr>
{% endfor %}
