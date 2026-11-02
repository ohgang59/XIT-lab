---
title: "Talks"
layout: page
permalink: /talks/
---

# {{ page.title }}

Presentations and seminar information related to {{ site.name }}'s research in AI, security, and communication systems.

{% comment %}Mark actual lab talks with lab: true in _data/talks.yml. Template talks remain excluded.{% endcomment %}
{% assign talks = site.data.talks | where: "lab", true | sort: "year" | reverse %}
{% assign invited = talks | where: "type", "invited" %}
{% assign contributed = talks | where_exp: "talk", "talk.type != 'invited'" %}

{% if invited.size > 0 %}
## Invited Talks

<div class="section-card" markdown="0">
{% for talk in invited %}{% include talk.html talk=talk %}{% endfor %}
</div>
{% endif %}

{% if contributed.size > 0 %}
## Presentations

<div class="section-card" markdown="0">
{% for talk in contributed %}{% include talk.html talk=talk %}{% endfor %}
</div>
{% endif %}

{% if talks.size == 0 %}
<div class="section-card" markdown="0">
<h2>Presentation Archive</h2>
<p>No lab talks or presentation materials are currently listed on this site.</p>
<p>For an overview of the work, browse our <a href="{{ '/research/' | relative_url }}">research areas</a> and <a href="{{ '/publications/' | relative_url }}">publication profiles</a>.</p>
</div>
{% endif %}

## Seminar and Speaker Inquiries

{% assign team_page = site.pages | where: "permalink", "/team/" | first %}
<div class="team-grid" markdown="0">
{% for director in team_page.directors %}
<section class="team-card">
<h3 class="team-name">{{ director.name | escape }}</h3>
<p class="team-info">{{ director.focus | escape }}</p>
<div class="team-links">
<a href="mailto:{{ director.email }}" class="btn-pill btn-link" aria-label="Contact {{ director.name | escape }} about a seminar">Contact {{ director.name | escape }}</a>
</div>
</section>
{% endfor %}
</div>

<div class="callout callout-info" markdown="0">
<h2 class="callout-title">Planning a Research Discussion?</h2>
<p>When contacting a co-director, include the topic, event format, and proposed date so the inquiry has the relevant context.</p>
</div>
