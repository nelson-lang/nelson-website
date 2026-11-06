---
title: News
description: Release announcements and news about Nelson, with an RSS feed you can subscribe to.
---

# News

Announcements about releases, features, and the project. You can subscribe to the
<a href="{{ '/feed.xml' | relative_url }}">RSS feed</a> to follow along.

<ul class="post-list" markdown="0">
{% for post in site.posts %}
  <li>
    <span class="post-list-date">{{ post.date | date: "%Y-%m-%d" }}</span>
    <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    {% if post.description %}<span class="post-list-sum">{{ post.description }}</span>{% endif %}
  </li>
{% endfor %}
</ul>

[Back to home](index.html)
