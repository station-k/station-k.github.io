---
layout: default
title: We notice
permalink: /we-notice/
lang: en
tags:
- With Ukraine in mind
- Knomads making it
---

**Coming up soon!**

{%- if site.posts.size > 0 -%}
{% assign sorted_tags = site.tags | sort %}
{% for tag in sorted_tags %}
{%- if page.tags contains tag[0] -%}
<h2>{{ tag[0] | upcase }}</h2>
<hr>
<ul class="post-list">
{%- for post in tag[1] -%}
{% if post.parent_page == "we-notice" %}
{% if post.lang == site.active_lang %}
<li>
{%- assign date_format = site.minima.date_format | default: "%m/%d/%Y" -%}
<span class="post-meta">{{ post.date | date: date_format }}</span>
<h3>
<a class="post-link" href="{{ post.url | relative_url }}">
    {{ post.title | escape }}
</a>
</h3>
{%- if site.show_excerpts -%}
{{ post.excerpt }}
{%- endif -%}
</li>
{% endif %}
{% endif %}
{%- endfor -%}
</ul>
{% endif %}
{% endfor %}


{%- endif -%}