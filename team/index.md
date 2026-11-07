---
title: Team
nav:
  order: 3
  tooltip: People of RoPI
---

# Team

{% include list.html data="members" component="portrait" filter="role == 'principal-investigator'" %}

{% assign groups = "phd|PhD Students,msc|MSc Students,undergrad|Undergraduate Students,alumni|Alumni" | split: "," %}
{% for g in groups %}
  {% assign key = g | split: "|" | first %}
  {% assign label = g | split: "|" | last %}
  {% assign people = site.data.students | where: "group", key %}
  {% if people.size > 0 %}
<div class="student-group">
  <h2>{{ label }}</h2>
  <ul class="student-list">
    {% for s in people %}
      <li>
        <span class="student-name">{% if s.website %}<a href="{{ s.website }}">{{ s.name }}</a>{% else %}{{ s.name }}{% endif %}</span>
        {% if s.years %}<span class="student-years">{{ s.years }}</span>{% endif %}
        {% if s.topic %}<span class="student-topic">{{ s.topic }}</span>{% endif %}
        {% if s.github %}{% include button.html type="github" text="" link=s.github style="bare" %}{% endif %}
        {% if s.scholar %}{% include button.html type="google-scholar" text="" link=s.scholar style="bare" %}{% endif %}
      </li>
    {% endfor %}
  </ul>
</div>
  {% endif %}
{% endfor %}

{% include section.html %}

## Join Us

We are always looking for motivated students interested in robotics, computer vision, and machine
learning. If you are interested in a thesis or a PhD position, please get in touch.

{% include button.html type="email" text="passalis@csd.auth.gr" link="passalis@csd.auth.gr" %}
