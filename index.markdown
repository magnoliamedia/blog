---
title: Voterheads Blog
layout: home
---

{% if site.paginate %}
  {% assign posts = paginator.posts %}
{% else %}
  {% assign posts = site.posts %}
{% endif %}

{%- if posts.size > 0 -%}
  {%- for post in posts -%}
    <div>
      <p class="text-sm text-gray-500">
        <time datetime="{{ post.date | date: "%Y-%m-%d" }}">
          {{ post.date | date: "%b %-d, %Y" }}
        </time>
      </p>

      <a href="{{ post.url | relative_url }}" class="mt-2 block">
        <h2 class="text-xl font-semibold text-gray-900">{{ post.title | escape }}</h2>
        <div class="mt-3 text-base text-gray-500">{{ post.excerpt }}</div>
      </a>

      <div class="mt-3">
        <a href="{{ post.url | relative_url }}" class="text-base font-semibold text-indigo-600 hover:text-indigo-500">
          Read more
        </a>
      </div>
    </div>
  {%- endfor -%}

  {% if site.paginate %}
    <div class="pager">
      <ul class="pagination">
      {%- if paginator.previous_page %}
        <li><a href="{{ paginator.previous_page_path | relative_url }}" class="previous-page">{{ paginator.previous_page }}</a></li>
      {%- else %}
        <li><div class="pager-edge">•</div></li>
      {%- endif %}
        <li><div class="current-page">{{ paginator.page }}</div></li>
      {%- if paginator.next_page %}
        <li><a href="{{ paginator.next_page_path | relative_url }}" class="next-page">{{ paginator.next_page }}</a></li>
      {%- else %}
        <li><div class="pager-edge">•</div></li>
      {%- endif %}
      </ul>
    </div>
  {%- endif %}
{%- endif -%}

<script defer data-domain="blog.voterheads.com" src="https://plausible.io/js/script.js"></script>
