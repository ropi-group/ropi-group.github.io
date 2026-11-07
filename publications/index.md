---
title: Publications
nav:
  order: 2
  tooltip: Papers, code, and demos
---

# Publications

{% assign featured = site.papers | sort: "date" | reverse %}
{% if featured.size > 0 %}
## Selected Papers

<div class="paper-grid">
{% for paper in featured %}
  {% include card.html title=paper.title subtitle=paper.venue link=paper.url image=paper.image description=paper.description %}
{% endfor %}
</div>

{% include section.html %}
{% endif %}

## All Publications

See also
{% include button.html type="google-scholar" link="5XJkgHYAAAAJ" style="bare" %}
{% include button.html type="dblp" link="166/5186" style="bare" %}

{% include search-box.html %}

{% include tags.html tags="journal, conference, book chapter" %}

{% include search-info.html %}

{% include list.html data="citations" component="citation" %}
