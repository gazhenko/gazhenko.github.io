---
layout: page
permalink: /life/
title: life
description: stuff about life, not tech related.
---

<ul class="post-list">
{% for post in site.life reversed %}
    <li>
        <h2><a class="post-title" href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a></h2>
        <p class="post-meta">{{ post.date | date: '%B %-d, %Y — %H:%M' }}</p>
      </li>
{% endfor %}
</ul>
