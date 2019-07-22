---
permalink: /speakers
layout: splash
title: Speakers
classes: wide-hero wide
share: true
header:
#  image: /assets/images/Tech-Exeter-2018-365.jpg
---
{% assign speakersSorted = site.speakers | sort:"track" | sort:"timeslot" %}

<div class="speakers">

  <h2>Keynote</h2>
  {% for speaker in speakersSorted %}
    {% if speaker.name == "Andi Hudson" %}
    <div class="grid-flex">
      <div class="speaker">
        <a href="{{ speaker.url }}"><img class=" circle" src="{{speaker.headshot}}"/></a>
        <h2>{{ speaker.name }}</h2>
        <p><strong>{{ speaker.title }}</strong> {% if speaker.company %}  at {{ speaker.company }} {% endif %}</p>
      </div>
    </div>
    {% endif %}
  {% endfor %}

  <h2>Track Hosts</h2>
  <div class="grid-flex">
  {% for speaker in speakersSorted %}
    {% if speaker.type == "Track Host" %}
      <div class="speaker">
        <a href="{{ speaker.url }}"><img class=" circle" src="{{speaker.headshot}}"/></a>
        <h2>{{ speaker.name }}</h2>
        <p><strong>{{ speaker.title }}</strong> {% if speaker.company %}  at {{ speaker.company }} {% endif %}</p>
      </div>
    {% endif %}
  {% endfor %}
  </div>

  <h2>Speakers</h2>

  <div class="grid-flex">
  {% for speaker in speakersSorted %}
  {% if speaker.name <>"Andi Hudson" and speaker.type <> "Track Host" %}
    <div class="speaker">
      <a href="{{ speaker.url }}"><img class=" circle" src="{{speaker.headshot}}"/></a>
      <h2>{{ speaker.name }}</h2>
      <p><strong>{{ speaker.title }}</strong> {% if speaker.company %}  at {{ speaker.company }} {% endif %}</p>
    </div>
    {% endif %}
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