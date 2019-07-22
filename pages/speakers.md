---
permalink: /speakers
layout: splash
title: Speakers
classes: wide-hero wide
share: true
header:
#  image: /assets/images/Tech-Exeter-2018-365.jpg
---

<div class="speakers">
<h2>Speakers</h2>

<div class="grid-4col ">
{% assign speakersSorted = site.speakers | sort:"timeslot" %}
{% for speaker in speakersSorted %}
  <div class="speaker">
    <a href="{{ speaker.url }}"><img class=" circle" src="{{speaker.headshot}}"/></a>
    <h2>{{ speaker.name }}</h2>
    <p><strong>{{ speaker.title }}</strong> {% if speaker.company %}  at {{ speaker.company }} {% endif %}</p>
  </div>
{% endfor %}
</div>
</div>

<h2>Speaker topics by tag:</h2>
{% assign alldocs = site.documents  %}	
{% assign grouptag =  alldocs | map: 'tags' | join: ','  | split: ','  | group_by: tag %}
{%- for tag in grouptag -%}
<h3>{{- tag.name -}}</h3>
<ul>
{%- for document in alldocs -%}
  {%- if document.tags contains tag.name -%}
    <li><a href="{{ document.url | capitalize  }}">{{ document.talk-title }} with {{ document.name }}</a></li>
  {%- endif -%}
{%- endfor -%}
</ul>
{%- endfor -%}