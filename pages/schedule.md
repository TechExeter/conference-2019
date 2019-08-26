---
permalink: /schedule
layout: splash
title: Schedule
classes: wide-hero wide
share: true
header:
#  image: /assets/images/Tech-Exeter-2018-365.jpg
---
{% assign scheduleSorted = site.speakers | concat: site.data.schedule | sort:"track" | sort:"timeslot" %}

<style type="text/css">
  #schedule {

    margin:1em 0em 2em;
    background:#fff;
    box-shadow:0px 0px 10px #999;
    padding:0.25em;
    display: grid;
    grid-gap: 0.2em;
    gap:0.2em;
    grid-template-areas:
      "t-0815 t123-0815 t123-0815 t123-0815"
      "t-0900 t123-0900 t123-0900 t123-0900"
      "t-0915 t123-0915 t123-0915 t123-0915"
      "t-0930 t1-0930 t1-0930 t1-0930"
      "t-0945 t1-0930 t1-0930 t1-0930"
      "thead t1head t2head t3head"
      "t-1000 t1-1000 t2-1000 t3-1000"
      "t-1015 t1-1000 t2-1000 t3-1000"
      "t-1030 t1-1030 t2-1000 t3-1000"
      "t-1045 t1-1030 t2-1045 t3-1045"
      "t-1100 t123-1100 t123-1100 t123-1100"
      "t-1115 t123-1100 t123-1100 t123-1100"
      "t-1130 t1-1130 t2-1130 t3-1130"
      "t-1145 t1-1130 t2-1130 t3-1130"
      "t-1200 t1-1130 t2-1200 t3-1200"
      "t-1215 t1-1215 t2-1200 t3-1200"
      "t-1230 t1-1215 t2-1230 t3-1230"
      "t-1245 t1-1215 t2-1230 t3-1230"
      "t-1300 t123-1300 t123-1300 t123-1300"
      "t-1315 t123-1300 t123-1300 t123-1300"
      "t-1330 t123-1300 t123-1300 t123-1300"
      "t-1345 t123-1300 t123-1300 t123-1300"
      "t-1400 t1-1400 t2-1400 t3-1400"
      "t-1415 t1-1400 t2-1400 t3-1400"
      "t-1430 t1-1400 t2-1430 t3-1400"
      "t-1445 t1-1445 t2-1430 t3-1445"
      "t-1500 t1-1445 t2-1500 t3-1445"
      "t-1515 t1-1445 t2-1500 t3-1445"
      "t-1530 t123-1530 t123-1530 t123-1530"
      "t-1545 t123-1530 t123-1530 t123-1530"
      "t-1600 t1-1600 t2-1600 t3-1600"
      "t-1615 t1-1600 t2-1600 t3-1600"
      "t-1630 t1-1630 t2-1600 t3-1600"
      "t-1645 t1-1645 t2-1645 t3-1645"
      "t-1700 t123-1700 t123-1700 t123-1700"
      "t-1715 t123-1715 t123-1715 t123-1715"
      "t-1730 t123-1730 t123-1730 t123-1730"
      "t-1745 t123-1745 t123-1745 t123-1745";
  }
  #schedule .small-time {
    display:none;
  }

  @media screen and (max-width: 40em) {
      #schedule {

        box-shadow:none;
        padding:0px;

        grid-gap: 0px;
        gap:0px;
      }
      #schedule .time {
        display:none;
      }

      #schedule .small-time {
        display:inline-block;
      }
  }

 #workshops {

    margin:1em 0em 2em;
    background:#fff;
    box-shadow:0px 0px 10px #999;
    padding:0.25em;
    display: grid;
    grid-gap: 1em;
    gap:1em;
    grid-template-areas:
      "wmorning wmorning"
      "w1000 w1130"
      "wafternoon wafternoon"
      "w1400 w1445";
  }

  #workshops .description { 
    margin:1em 0em 0.5em;
  }
  #workshops .heading h2 { 
    background: #11999E;
    color: #fff;
    padding: 0.5em;
    margin:0px;
  }
  #workshops h2 { margin-top:0px; border-bottom:none; }

</style>

<h1 style="margin-top:1em;">Talk Schedule</h1>

<div id="schedule">

  {% for speaker in scheduleSorted %}
  {% if speaker.type != "Track Host" and speaker.track != "Workshop" %}
    <div class="item {{ speaker.type }} t{{ speaker.track }}" style="grid-area: t{{ speaker.track }}-{{ speaker.timeslot | replace: ".", ""  | replace: ":", "" }};" {% if speaker.type == "time" %} id="time_{{ speaker.timeslot | replace: ".", ""  | replace: ":", "" }}" {% endif %}>
    <div class="small-time">{{ speaker.timeslot }} </div>
    {% if speaker.url %}
    <a href="{{ speaker.url }}">
    {% endif %}
    <h2>{{ speaker.talk-title }}</h2>
    {% if speaker.url %}
    </a>
    {% endif %}
    <div class="description">{{ speaker.description }}</div>
    {% if speaker.type != "time" and  speaker.type != "break" and speaker.type != "lunch" %}
    <div class="type"> {{ speaker.type }}</div>
    {% endif %}
    <div class="speaker">{{ speaker.name }}</div>
    </div>
    {% endif %}
  {% endfor %}

  <div class="item head t1" style="grid-area: t1head;" id="track_1">
  <h2>Track 1</h2>
  TECH
  </div>
  <div class="item head t2" style="grid-area: t2head;" id="track_2">
  <h2>Track 2</h2>
  HACK
  </div>
  <div class="item head t3" style="grid-area: t3head;" id="track_3">
  <h2>Track 3</h2>
  DEVELOP
  </div>

</div>

<h1>Workshops</h1>
All workshops will be taking place on floor 2 of Building One.
Spaces are limited so be sure to <a href="https://docs.google.com/forms/d/e/1FAIpQLSdhKUMymab32hHXFB-yqV-d1LaeXADM6LfdL0F9srh2Gfr5DA/viewform?usp=sf_link" target="_blank">register your interest</a>.
<div id="workshops">
  <div class="heading" style="grid-area: wmorning;">
  <h2>Morning Workshops</h2>
  </div>
  <div class="heading" style="grid-area: wafternoon;">
  <h2>Afternoon Workshops</h2>
  </div>
  {% for speaker in scheduleSorted %}
  {% if speaker.track == "Workshop" %}
  <div class="item workshop" style="grid-area: w{{ speaker.timeslot | replace: ".", ""  | replace: ":", "" }};">
  <a href="{{ speaker.url }}"><h2>{{ speaker.talk-title }}</h2></a>
  <div class="speaker">{{ speaker.name }}</div>
  <div class="type"><strong>{{ speaker.timeslot }} </strong> {{ speaker.type }}</div>
  <div class="description">{{ speaker.description }}</div>
  <a class="btn btn--primary" href="https://docs.google.com/forms/d/e/1FAIpQLSdhKUMymab32hHXFB-yqV-d1LaeXADM6LfdL0F9srh2Gfr5DA/viewform?usp=sf_link" target="_blank">Register Here</a>
  </div>
  {% endif %}
  {% endfor %}
</div>


<div style="text-align:center;"><em>* Schedule is subject to change</em></div>
