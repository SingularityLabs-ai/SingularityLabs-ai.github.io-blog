---
permalink: /posts/
layout: default
title: Posts
---


{% for post in site.posts %}
- [{{ post.title }}]({{ post.url }})
{% endfor %}

    <!-- <p class="rss-subscribe">subscribe <a href="/feed.xml">via RSS</a></p></div> -->