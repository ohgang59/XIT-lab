---
title: "Software"
layout: page
permalink: /software/
---

# {{ page.title }}

Code and software resources connected to {{ site.name }}'s work in AI and communication systems.

{% if site.links.github and site.links.github != "" %}
<div class="section-card" markdown="0">
<h2>{{ site.name }} on GitHub</h2>
<p>Visit the lab's GitHub organization to browse its publicly available repositories.</p>
<a href="{{ site.links.github | escape }}" target="_blank" rel="noopener noreferrer" class="btn-pill btn-git">{% include icon.html name="github" %} Visit GitHub</a>
</div>
{% endif %}

{% comment %}Mark actual lab projects with lab: true in _data/software.yml. Template projects remain excluded.{% endcomment %}
{% assign projects = site.data.software | where: "lab", true %}

{% if projects.size > 0 %}
## Projects

<div class="grid-auto" style="grid-template-columns: repeat(auto-fit, minmax(min(100%, 280px), 1fr));" markdown="0">
{% for project in projects %}
<article class="card-academic">
<h3>{{ project.name | escape }}</h3>
{% if project.authors %}<p class="text-muted">{{ project.authors | escape }}</p>{% endif %}
<p>{{ project.description | escape }}</p>
<div class="d-flex flex-wrap gap-2">
{% if project.repo and project.repo != "" %}<a href="{{ project.repo | escape }}" class="btn-pill btn-git">Code</a>{% endif %}
{% if project.website and project.website != "" %}<a href="{{ project.website | escape }}" class="btn-pill btn-website">Website</a>{% endif %}
{% if project.docs and project.docs != "" %}<a href="{{ project.docs | escape }}" class="btn-pill btn-link">Documentation</a>{% endif %}
{% if project.paper and project.paper != "" %}<a href="{{ project.paper | escape }}" class="btn-pill btn-paper">Paper</a>{% endif %}
</div>
</article>
{% endfor %}
</div>
{% else %}
<div class="section-card" markdown="0">
<h2>Project Information</h2>
<p>Individual software projects are not currently catalogued on this site. For available code, documentation, and usage conditions, consult the relevant GitHub repository.</p>
</div>
{% endif %}

<div class="callout callout-info" markdown="0">
<h2 class="callout-title">Code Related to a Paper</h2>
<p>If you are looking for an implementation associated with a publication, consult the <a href="{{ '/publications/' | relative_url }}">publication profiles</a> or <a href="{{ '/team/' | relative_url }}">contact the relevant co-director</a>.</p>
</div>
