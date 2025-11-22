---
layout: default
title: Blog
theme: light
---

<section class="blog-hero">
  <div class="kicker">FreeData · Blog<br></div>
  <!-- <h1>{{ page.title }}</h1> -->
  <p class="lead">Gedanken. Aus dem Mittelstand.</p>
</section>

<hr class="divider"/>

<section class="blog-list">
{% for post in site.posts %}
  <article class="blog-row">
    <div class="blog-row-head">
      <h2 class="blog-title">
        <a href="{{ post.url }}">{{ post.title }}</a>
      </h2>

      <div class="blog-date">
        {{ post.date | date: "%d.%m.%Y" }}
      </div>
    </div>

    <p class="blog-excerpt">
      {{ post.excerpt | strip_html | truncate: 220 }}
    </p>

    <div class="blog-read">
      <a href="{{ post.url }}">Weiterlesen →</a>
    </div>
  </article>
{% endfor %}
</section>
