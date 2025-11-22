---
layout: default
title: Blog
theme: light
---

<section class="blog-hero">
  <div class="kicker">FreeData · Blog</div>
  <p class="lead">{{ page.title }}</p>
</section>

<hr class="divider"/>

<section class="blog-list">
{% for post in site.posts %}
  <article class="blog-card">
    <div class="blog-meta">
      <span class="blog-date">{{ post.date | date: "%d.%m.%Y" }}</span>
      {% if post.category %}
        <span class="blog-tag">{{ post.category }}</span>
      {% endif %}
    </div>

    <h2 class="blog-title">
      <a href="{{ post.url }}">{{ post.title }}</a>
    </h2>

    <p class="blog-excerpt">
      {{ post.excerpt | strip_html | truncate: 220 }}
    </p>

    <div class="blog-read">
      <a href="{{ post.url }}">Weiterlesen →</a>
    </div>
  </article>
{% endfor %}
</section>