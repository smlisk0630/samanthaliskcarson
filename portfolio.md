---
layout: page
title: Portfolio
permalink: portfolio
description: View Samantha's portfolio, including articles on the intersection of AI and the environment, how to handle e-waste, the Right to Repair, and more.
---
{% comment %}
{% raw %}
<div>
  {% for post in site.posts %}
    <div class="py-1">
      <h3><a href="{{site.baseurl}}{{ post.url }}">{{ post.title}}</a></h3>
      <div class="text-sm text-gray-400">{{post.date | date: "%B %-d, %Y"}}</div>
    </div>
  {% endfor %}
</div>
{% endraw %}
{% endcomment %}

<div>
{% assign years = site.posts
   | group_by_exp: "post", "post.date | date: '%Y'"
%}
{% for year in years %}
  <p>{{ year.name }}</p>
  <ul>
    {% for post in year.items %}
    <li>
        <div class="text-gray-400">{{post.date | date: "%b %d  "}}
        <a class='title' href='{{ post.url }}'>{{ post.title }}</a></div>
    </li>
    {% endfor %}
  </ul>

{% endfor %}

