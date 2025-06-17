---
layout: archive
title:  "Research"
permalink: /research/
author_profile: true
---

{% include base_path %}

{%- comment -%}
  WORKING PAPERS & IN-PROGRESS
  (category == "wp")
{%- endcomment -%}
{% assign working = site.publications
                   | where: "category", "wp"
                   | sort: "date" %}

{%- comment -%}
  PUBLISHED & ACCEPTED
  (anything whose category is NOT "wp")
{%- endcomment -%}
{% assign published = site.publications
                     | where_exp: "item", "item.category != 'wp'"
                     | sort: "date" %}

{% if working != empty %}
## Working Papers & In-Progress
<hr>
{% for post in working reversed %}
  {% include archive-single.html type="list" %}
  {% unless forloop.last %}<hr>{% endunless %}
{% endfor %}
{% endif %}

## Published & Accepted
<hr>
{% for post in published reversed %}
  {% include archive-single.html type="list" %}
  {% unless forloop.last %}<hr>{% endunless %}
{% endfor %}
