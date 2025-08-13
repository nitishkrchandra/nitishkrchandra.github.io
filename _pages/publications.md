---
layout: single
title: "Publications"
permalink: /publications/
author_profile: true
---

<ol>
{% for pub in site.data.publications %}
  <li>
    <p><strong>{{ pub.title }}</strong><br>
    {{ pub.authors }}<br>
    <em>{{ pub.venue }}</em>
    {% if pub.url %}
      <br><a href="{{ pub.url }}" target="_blank" rel="noopener noreferrer">[Link]</a>
    {% endif %}
    </p>
  </li>
{% endfor %}
</ol>
