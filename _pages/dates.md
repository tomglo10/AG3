---
layout: post
title: By Date
permalink: /dates/
content-type: eg
---

<style>
.date-content a {
    text-decoration: none;
    color: #376a8c; /* Matches your clinical blue theme */
    font-family: 'Open Sans', sans-serif;
}

.date-content a:hover {
    text-decoration: underline;
    color: #2c5570;
}

.date-content h3 {
    font-family: 'Lora', serif;
    color: #222;
    margin-bottom: 15px;
}
</style>

<main class="date-content">
    {% comment %} Sort all posts by date descending first {% endcomment %}
    {% assign sortedPosts = site.posts | sort: 'date' | reverse %}
    {% assign postsByDay = sortedPosts | group_by_exp:"post", "post.date | date: '%B %d, %Y'" %}

    {% for day in postsByDay %}
      <h3 id="{{ day.name | slugify }}" style="border-bottom: 1px solid #eee; padding-top: 1em;">
        <i class="far fa-calendar-check"></i> {{ day.name }}
      </h3>
      <ul style="padding-left: 10px;">
          {% for post in day.items %}
            <li style="padding-bottom: 0.6em; list-style: none;">
                <a href="{{ post.url | relative_url }}" style="font-weight: 600;">{{ post.title }}</a>
                {% if post.author %} <small style="color: #888;">— {{ post.author }}</small> {% endif %}
            </li>
          {% endfor %}
      </ul>
    {% endfor %}
</main>
