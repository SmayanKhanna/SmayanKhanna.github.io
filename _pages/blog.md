---
layout: default
permalink: /blog/
title: writing
nav: true
nav_order: 1
---

<div class="post">

  <ul class="post-list">

    {% assign allowed_posts = "2015-10-20-math,2015-07-15-code" | split: "," %}

    {% for post in site.posts %}
      {% assign post_slug = post.slug %}
      {% if allowed_posts contains post_slug %}

        {% assign read_time = post.content | number_of_words | divided_by: 180 | plus: 1 %}
        {% assign year = post.date | date: "%Y" %}

        <li>
          <h3>
            <a class="post-title" href="{{ post.url | relative_url }}">{{ post.title }}</a>
          </h3>
          <p>{{ post.description }}</p>
          <p class="post-meta">
            {{ read_time }} min read &nbsp; &middot; &nbsp;
            {{ post.date | date: '%B %d, %Y' }}
          </p>
        </li>

      {% endif %}
    {% endfor %}

  </ul>

</div>
