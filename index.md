---
layout: default
title: mcgrue.github.io
---

<div class="posts">
    {% for post in site.posts %}
        <article>
            <h1 class="post-title"><a href="{{ post.url }}">{{ post.title }}</a></h1>
            <h2 class="date">posted {{ post.date | date: "%B %d, %Y" }} | tagged
                {% for tag in post.tags %}
                    <a href="/tag/{{ tag }}">{{ tag }}</a>
                {% endfor %}
            </h2>
            {{ post.content }}
        </article>
    {% endfor %}
</div>
