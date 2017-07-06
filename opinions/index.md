---
layout: page
title: Opinions
excerpt: "Anything I feel strongly about. Mostly politics."
search_omit: true
---
<center><i>All opinions expressed are my own and do not represent any other entity, including employers (past and present) and any group that I am a member of.</i></center>
<ul class="post-list">
{% for post in site.categories.opinions %} 
  <li><article><a href="{{ site.url }}{{ post.url }}">{{ post.title }} <span class="entry-date"><time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%B %d, %Y" }}</time></span>{% if post.excerpt %} <span class="excerpt">{{ post.excerpt | remove: '\[ ... \]' | remove: '\( ... \)' | markdownify | strip_html | strip_newlines | escape_once }}</span>{% endif %}</a></article></li>
{% endfor %}
</ul>
