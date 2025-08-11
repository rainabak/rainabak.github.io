---
title: 홈
layout: default
---

# 프론트엔드 개발 정리

환영합니다!  
이 사이트는 프론트엔드 개발을 공부하면서 정리한 내용을 기록하는 곳입니다.

## 최신 글

{% assign sorted = site.notes | sort: 'date' | reverse %}
{% for note in sorted limit:5 %}
- [{{ note.title }}]({{ note.url | relative_url }}) — {{ note.date | date: "%Y-%m-%d" }}
{% endfor %}

---
