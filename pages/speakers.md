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
{% for speaker in site.speakers %}
  <div class="speaker">
    <a href="{{ speaker.url }}"><img class=" circle" src="{{speaker.headshot}}"/></a>
    <h2>{{ speaker.name }}</h2>
    <p><strong>{{ speaker.title }}</strong> at {{ speaker.company }}</p>
  </div>
{% endfor %}
</div>

</div>