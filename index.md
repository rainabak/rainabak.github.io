---
title: 홈
layout: default
---

# 프론트엔드 개발 정리

최신 노트

{% assign sorted = site.notes | sort: 'date' | reverse %}
{% for note in sorted limit:6 %}
<div class="card">
  <h3><a href="{{ note.url | relative_url }}">{{ note.title }}</a></h3>
  <p>{{ note.excerpt | default: note.description }}</p>
  {% if note.tags %}
  <p>
    {% for t in note.tags %}
      <span class="tag">#{{ t }}</span>
    {% endfor %}
  </p>
  {% endif %}
  <small>{{ note.date | date: "%Y-%m-%d" }}</small>
</div>
{% endfor %}
