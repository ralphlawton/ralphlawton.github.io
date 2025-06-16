---
layout: archive
title:  "Research"
permalink: /research/
author_profile: true
---

{% include base_path %}

{% assign working   = site.publications | where: "category", "wp" %}
{% assign published = site.publications | reject: "category", "wp" %}

{% if working != empty %}
## Working Papers & In-progress
<hr>
{% for post in working reversed %}
{% include archive-single.html type="list" %}
{% unless forloop.last %}
<hr>
{% endunless %}
{% endfor %}
{% endif %}


## Published & Accepted
<hr>
{% for post in published reversed %}
{% include archive-single.html type="list" %}
{% unless forloop.last %}
<hr>
{% endunless %}
{% endfor %}
