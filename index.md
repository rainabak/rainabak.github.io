---
title: Home
layout: default
---

<section class="hero">
  <h1>FE Notes</h1>
  <p>프론트엔드 개발 지식을 빠르게 찾고, 차곡차곡 쌓는 공간</p>
</section>

<section class="section">
  <h2>최신 글</h2>
  <div class="cards">
    {% assign sorted = site.notes | sort: 'date' | reverse %}
    {% for note in sorted limit:6 %}
    <article class="card">
      <h3><a href="{{ note.url | relative_url }}">{{ note.title }}</a></h3>
      <p>{{ note.description | default: note.excerpt }}</p>
      <small>{{ note.date | date: "%Y-%m-%d" }}</small>
      <div>
        {% if note.tags %}
          {% for t in note.tags %}
            <span class="tag">#{{ t }}</span>
          {% endfor %}
        {% endif %}
      </div>
    </article>
    {% endfor %}
  </div>
</section>

<section class="section">
  <h2>카테고리</h2>
  <div>
    <a class="cat" href="{{ '/categories/' | relative_url }}">전체 보기</a>
    <a class="cat" href="{{ '/categories/react/' | relative_url }}">React</a>
    <a class="cat" href="{{ '/categories/javascript/' | relative_url }}">JavaScript</a>
    <a class="cat" href="{{ '/categories/css/' | relative_url }}">CSS</a>
    <a class="cat" href="{{ '/categories/tooling/' | relative_url }}">Tooling</a>
    <a class="cat" href="{{ '/categories/test/' | relative_url }}">Test</a>
  </div>
</section>

<section class="section">
  <h2>태그</h2>
  {% assign all = "" | split: "" %}
  {% for note in site.notes %}
    {% assign all = all | concat: note.tags %}
  {% endfor %}
  {% assign tags = all | uniq | sort %}
  {% for t in tags %}
    <a class="tag" href="{{ '/tags/#' | append: t | slugify | relative_url }}">#{{ t }}</a>
  {% endfor %}
</section>
