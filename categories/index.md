---
title: Categories
layout: default
permalink: /categories/
---

# Categories
{% assign cats = site.notes | map: 'categories' | uniq | sort %}
<ul>
{% for c in cats %}
  <li><a href="#{{ c | slugify }}">{{ c }}</a></li>
{% endfor %}
</ul>

{% for c in cats %}
## <a id="{{ c | slugify }}"></a>{{ c }}
<ul>
  {% for note in site.notes %}
    {% if note.categories == c %}
      <li><a href="{{ note.url | relative_url }}">{{ note.title }}</a></li>
    {% endif %}
  {% endfor %}
</ul>
{% endfor %}
