---
layout: page
title: Blog
permalink: blog
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
        <a class='title' href='{{ post.url }}'>{{ post.title }}</a>
      </li>
    {% endfor %}
  </ul>
</div>
{% endfor %} 
</div>

