---
layout: page
title: Kokkelering
permalink: /Kokkelering/
---
Oppskrifter og andre artikler relatert til kokkeleringen jeg bedriver

<ul class="post-list">
    {% for post in site.posts |%}
    {% if post.categories contains 'food' %}
    <li>
    <span class="post-meta">{{ post.date | date: "%b %-d, %Y" }}</span>
    <h2>
        <a class="post-link" href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
    </h2>
    </li>
    {% endif %}
{% endfor %}
</ul>