---
layout: archive
title: "Working papers"
permalink: /publications/
author_profile: true
---

{% if author.googlescholar %}
  You can also find my articles on <u><a href="{{author.googlescholar}}">my Google Scholar profile</a>.</u>
{% endif %}

{% include base_path %}

{% for post in site.publications reversed %}
  {% include archive-single.html %}
{% endfor %}

## Work in progress

<ul>
  <li><strong>Project title 1</strong> (with Coauthor A, Coauthor B) — <em>in progress</em></li>
  <li><strong>Project title 2</strong> (with Coauthor C) — <em>in progress</em></li>
  <li><strong>Project title 3</strong> — <em>in progress</em></li>
</ul>
