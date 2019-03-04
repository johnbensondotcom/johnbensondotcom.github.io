---
layout: page
title: Forensics & E-Discovery
permalink: /reference/
---

<ul>
    {% for reference in site.reference %}
        <li>
            <a href="{{ reference.url }}">{{ reference.title }}</a>
         - {{ reference.headline }}
      </li>
    {% endfor %}
</ul>