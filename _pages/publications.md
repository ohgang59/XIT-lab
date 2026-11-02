---
title: "Publications"
layout: page
permalink: /publications/
---

# {{ page.title }}

Explore the publication profiles of {{ site.name }}'s co-directors, whose research spans trustworthy AI, communication security, and communication-system optimization.

{% assign team_page = site.pages | where: "permalink", "/team/" | first %}

## Researcher Profiles

<div class="team-grid" markdown="0">
{% for director in team_page.directors %}
<section class="team-card">
<h3 class="team-name">{{ director.name | escape }}</h3>
<p class="team-info">{{ director.focus | escape }}</p>
<div class="team-links">
<a href="{{ director.scholar | escape }}" target="_blank" rel="noopener noreferrer" class="btn-pill btn-website" aria-label="View {{ director.name | escape }}'s publications on Google Scholar">View publications on Scholar</a>
</div>
</section>
{% endfor %}
</div>

{% comment %}
Keep the template's Feynman entries out of the lab's publication list.
Add lab = {true} to actual lab entries in assets/ref.bib to list them here.
{% endcomment %}
{% capture lab_publications %}{% bibliography --query @*[lab=true] %}{% endcapture %}

{% if lab_publications contains 'pub-entry' %}
## Lab Publications

<div class="section-card" markdown="0">
<label for="pubSearch">Search lab publications by title, author, or year</label>
<input type="search" id="pubSearch" class="pub-search" placeholder="Search by title, author, or year...">
{{ lab_publications }}
</div>
{% else %}
<div class="section-card" markdown="0">
<h2>Finding a Paper</h2>
<p>Individual lab publications are not currently listed on this site. Use the Google Scholar profiles above to browse each co-director's publications.</p>
<p>For questions about a paper or related research, <a href="{{ '/team/' | relative_url }}">contact the relevant co-director</a>.</p>
</div>
{% endif %}
