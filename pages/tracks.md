---
permalink: /tracks
layout: splash
title: Tracks
classes: wide-hero wide
share: true
header:
tracks:
  - "1"
  - "2"
  - "3"
---
{% assign speakersSorted = site.speakers | concat: site.data.schedule | sort:"timeslot" %}


<div class="tracks">
{% for track in page.tracks %}
  <h2>Track {{ track }}</h2>

  {% for speaker in speakersSorted %}
  {% if speaker.track == track and speaker.type == "Track Host" %}
  <div class="speaker">
      <table>
      <tr><td width="250" style="width:250px;">
        <a href="{{ speaker.url }}"><img class=" circle" src="{{speaker.headshot}}"/></a>
      </td><td>
        <h2>{{ speaker.name }} {% if speaker.pronoun  %} ({{ speaker.pronoun }}) {% endif %}</h2>
        <h3>{{ speaker.type }} for track {{ speaker.track }}</h3>
        <p><strong>{{ speaker.title }}</strong> {% if speaker.company %}  at {{ speaker.company }} {% endif %}</p>
      </td>
      </tr>
      <tr><td colspan="2"><p>{{ speaker.content | markdownify }}</p></td></tr>
      </table>
    </div>
  {% endif %}
  {% endfor %}

  {% for speaker in speakersSorted %}
    {% if speaker.track == "123" and speaker.timeslot <> "08.15" and speaker.timeslot <> "09.00" %}
    <hr/>
    <h2> {{ speaker.timeslot }} {{ speaker.talk-title}}</h2>
    <hr/>
    {% endif %}
    {% if speaker.track == track and speaker.type <> "Track Host" %}
    <div class="speaker">
      <table>
      <tr><td width="250" style="width:250px;">
        <a href="{{ speaker.url }}"><img class=" circle" src="{{speaker.headshot}}"/></a>
      </td><td>
        <h2>{{ speaker.name }} {% if speaker.pronoun  %} ({{ speaker.pronoun }}) {% endif %}</h2>
        <h3>{{ speaker.type }} / Track {{ speaker.track }} / {{ speaker.timeslot }}</h3>
        <p><strong>{{ speaker.title }}</strong> {% if speaker.company %}  at {{ speaker.company }} {% endif %}</p>
      </td>
      </tr>
      <tr><td colspan="2"> <h3>{{ speaker.talk-title }}</h3><p>{{ speaker.content | markdownify }}</p></td></tr>
      </table>
    </div>
    {% endif %}
  {% endfor %}

{% endfor %}

</div>
