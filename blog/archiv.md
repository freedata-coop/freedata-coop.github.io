---
layout: default
title: Archiv
theme: light
---

<section class="blog-hero">
  <div class="kicker">FreeData · Blog</div>
  <h1>Archiv</h1>
  <p class="lead">Alle Beiträge nach Jahr.</p>
</section>

<hr class="divider"/>

{%- assign sorted = site.posts | sort: "date" | reverse -%}
{%- assign years = sorted | group_by_exp: "post", "post.date | date: '%Y'" -%}

<nav class="year-nav">
  {% for y in years %}
    <a href="#y{{ y.name }}">{{ y.name }}</a>
  {% endfor %}
</nav>

<section class="year-archive">
{% for y in years %}
  <h2 id="y{{ y.name }}" class="year-head">{{ y.name }}</h2>

  {% for post in y.items %}
    <article class="blog-row">
      <div class="blog-row-head">
        <h2 class="blog-title"><a href="{{ post.url }}">{{ post.title }}</a></h2>
        <div class="blog-date">{{ post.date | date: "%d.%m.%Y" }}</div>
      </div>
      <p class="blog-excerpt">{{ post.excerpt | strip_html | truncate: 220 }}</p>
    </article>
  {% endfor %}
{% endfor %}
</section>
