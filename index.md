---
---

{% include section.html dark=true size="wide" %}

<div class="hero">
  <div class="hero-text">
    <p class="hero-kicker">Aristotle University of Thessaloniki</p>
    <h1 class="hero-title">Robotic Perception<br>and Intelligence</h1>
    <p class="hero-lead">
      RoPI is a research group working at the intersection of artificial intelligence,
      computer vision, and robotics. It is part of the
      <a href="https://aiia.csd.auth.gr/">Artificial Intelligence and Information Analysis (AIIA) Laboratory</a>
      at the <a href="https://www.csd.auth.gr/">School of Informatics</a>,
      <a href="https://www.auth.gr/">Aristotle University of Thessaloniki</a>.
    </p>
    <div class="hero-buttons">
      {% include button.html link="research" text="Our research" icon="fa-solid fa-arrow-right" flip=true %}
      {% include button.html link="publications" text="Publications" style="bare" %}
    </div>
  </div>
  <div class="hero-mark">
    <img src="{{ 'images/logo-light.png' | relative_url }}" alt="RoPI logo">
  </div>
</div>

{% include section.html %}

## Research Areas

<div class="area-grid">
{% for area in site.data.research_areas %}
  <a class="area-card" href="{{ 'research' | relative_url }}#{{ area.id }}">
    <span class="area-icon">{% include icon.html icon=area.icon %}</span>
    <span class="area-title">{{ area.title }}</span>
    <span class="area-summary">{{ area.summary }}</span>
  </a>
{% endfor %}
</div>

{% assign recent = site.papers | sort: "date" | reverse %}
{% if recent.size > 0 %}
{% include section.html %}

## Recent Papers

<div class="paper-grid">
{% for paper in recent limit: 3 %}
  {% include card.html title=paper.title subtitle=paper.venue link=paper.url image=paper.image description=paper.description %}
{% endfor %}
</div>
{% endif %}

{% if site.posts.size > 0 %}
{% include section.html %}

## Latest News

{% for post in site.posts limit: 3 %}
  {% include post-excerpt.html lookup=post.slug %}
{% endfor %}

{% include button.html link="news" text="All news" icon="fa-solid fa-arrow-right" flip=true style="bare" %}
{% endif %}
