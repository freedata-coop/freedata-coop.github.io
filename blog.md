---
layout: default
title: Blog
theme: light
---

{% for post in site.posts %}
### [{{ post.title }}]({{ post.url }})
<small>{{ post.date | date: "%d.%m.%Y" }}</small>
<br>
{{ post.excerpt }}
<hr>
{% endfor %}
