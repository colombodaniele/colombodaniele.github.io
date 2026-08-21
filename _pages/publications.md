---
layout: archive
title: "Research"
permalink: /papers/
author_profile: true
---

{% include base_path %}

## Working papers

{%- assign working_papers = site.publications | where_exp: "p", "p.status != 'wip'" -%}
{%- for post in working_papers reversed -%}
  {% include research-card.html %}
{%- endfor -%}

## Work in progress

{%- assign wip_papers = site.publications | where: "status", "wip" -%}
{%- for post in wip_papers reversed -%}
  {% include research-card.html %}
{%- endfor -%}
