---
layout: page
title: Posts
permalink: /posts/
---
{%- if page.title -%}
    {{ page.title }}
    ================
{%- endif -%} 


{{ content }}

{% if site.paginate %} 
    {% assign posts = paginator.posts %} 
{% else %} 
    {% assign posts = site.posts %} 
{% endif %}

{%- if posts.size > 0 -%}
    {%- if page.list\_title -%}
    {{ page.list\_title }}
    ----------------------
    {%- endif -%}

    {%- assign date\_format = site.minima.date\_format | default: "%b %-d, %Y" -%}

    {%- for post in posts -%}*  {{ post.date | date: date\_format }}
        ### [{{ post.title | escape }}]({{ post.url | relative_url }})
        {%- if site.show\_excerpts -%}
            {{ post.excerpt }} 
        {%- endif -%}
    {%- endfor -%}

    {% if site.paginate %}
        {%- if paginator.previous\_page %}*   [{{ paginator.previous\_page }}]({{ paginator.previous_page_path | relative_url }})
        {%- else %}*   •
        {%- endif %}*   

        {{ paginator.page }}
        {%- if paginator.next\_page %}*   [{{ paginator.next\_page }}]({{ paginator.next_page_path | relative_url }})
        {%- else %}*   •
        {%- endif %}
    {%- endif %}
{%- endif -%}

<!-- <p class="rss-subscribe">subscribe <a href="/feed.xml">via RSS</a></p></div> -->
