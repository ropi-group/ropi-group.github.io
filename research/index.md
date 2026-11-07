---
title: Research
nav:
  order: 1
  tooltip: Our research areas
---

# Research

Our research lies at the intersection of artificial intelligence, computer vision, and robotics.
We work both on advancing the theory of learning and perception methods and on deploying them on
real robotic and autonomous systems.

{% for area in site.data.research_areas %}
{% include section.html %}

<div class="area-section" id="{{ area.id }}">
  <h2>{% include icon.html icon=area.icon %}{{ area.title }}</h2>
  {% if area.image %}
    {% include figure.html image=area.image %}
  {% endif %}
  {{ area.description | markdownify }}

  {% capture filter %}item['areas'].to_a.include?('{{ area.id }}'){% endcapture %}
  {% assign area_papers = site.papers | data_filter: filter | sort: "date" | reverse %}
  {% if area_papers.size > 0 %}
    <h3>Related papers</h3>
    <div class="paper-grid">
      {% for paper in area_papers %}
        {% include card.html title=paper.title subtitle=paper.venue link=paper.url image=paper.image description=paper.description %}
      {% endfor %}
    </div>
  {% endif %}
</div>
{% endfor %}
