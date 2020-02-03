---
layout: archive
title: "Vita"
permalink: /vita/
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}

Education
======
* MSci Mathematics, Imperial College London, 2015-2019
* Ph.D in Pure Mathematics, Stony Brook University, 2019-

Awards
======
  * IBM Prize for Excellence in Pure Mathematics, 2019
  * FONS Prize for Excellence in Support of Teaching, 2019
  * G-Research Prize, 2017
  * President's Undergraduate Scholarship, 2015-2019

Publications
======
  <ul>{% for post in site.publications %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>

Talks
======
  <ul>{% for post in site.talks %}
    {% include archive-single-talk-cv.html %}
  {% endfor %}</ul>

Teaching
======
  <ul>{% for post in site.teaching %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>
