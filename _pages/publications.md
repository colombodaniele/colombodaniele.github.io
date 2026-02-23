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

{%- assign working_papers = site.publications | where_exp: "p", "p.status != 'wip'" -%}
{%- for post in working_papers reversed -%}
  {% include archive-single.html %}
{%- endfor -%}

## Work in progress

{%- assign wip_papers = site.publications | where: "status", "wip" -%}
{%- for post in wip_papers reversed -%}
  {% include archive-single.html %}
{%- endfor -%}
