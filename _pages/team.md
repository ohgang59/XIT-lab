---
title: "Team"
layout: page
permalink: /team/
directors:
  - name: Byung Chang Chung
    email: bcchung@gnu.ac.kr
    scholar: "https://scholar.google.com/citations?user=Z8_fEX8AAAAJ&hl=ko&oi=ao"
    focus: Trustworthy AI and network / communication security
  - name: Junbeom Kim
    email: junbeom@gnu.ac.kr
    scholar: "https://scholar.google.com/citations?user=IHggtk0AAAAJ&hl=ko&oi=ao"
    focus: Communication MIMO system optimization
---

# {{ page.title }}

{{ site.name }} is co-directed by **Prof. Byung Chang Chung** and **Prof. Junbeom Kim** at {{ site.institution }}. Their complementary research areas connect trustworthy AI and communication security with communication-system optimization.

## Co-Directors

<div class="team-grid" markdown="0">
{% for director in page.directors %}
<section class="team-card">
<p class="team-info">Professor &amp; Co-Director</p>
<h3 class="team-name">{{ director.name | escape }}</h3>
<p>{{ director.focus | escape }}</p>
<p class="team-info">{{ site.institution }}</p>
<div class="team-links flex-wrap gap-2">
<a href="{{ director.scholar | escape }}" target="_blank" rel="noopener noreferrer" class="btn-pill btn-website" aria-label="{{ director.name | escape }} on Google Scholar">Google Scholar</a>
<a href="mailto:{{ director.email }}" class="btn-pill btn-link" aria-label="Email {{ director.name | escape }}">Email</a>
</div>
</section>
{% endfor %}
</div>

{% comment %}
The data files still contain template examples. Only records explicitly marked
lab: true are displayed here; add that field to actual lab members and alumni.
The directors above also supply profile links to other pages.
{% endcomment %}
{% assign members = site.data.team_members | where: "lab", true %}
{% assign alumni = site.data.alumni | where: "lab", true %}

{% if members.size > 0 %}
## Members

<div class="team-grid" markdown="0">
{% for member in members %}
<article class="team-card">
{% if member.photo and member.photo != "" %}<img src="{{ member.photo | prepend: '/images/' | relative_url }}" alt="{{ member.name | escape }}" class="team-photo" width="100" height="100" loading="lazy">{% endif %}
<h3 class="team-name">{{ member.name | escape }}</h3>
<p class="team-info">{{ member.info | escape }}</p>
<div class="team-links flex-wrap gap-2">
{% if member.email and member.email != "" %}<a href="mailto:{{ member.email }}" class="btn-pill btn-link">Email</a>{% endif %}
{% if member.website and member.website != "" %}<a href="{{ member.website | escape }}" class="btn-pill btn-website">Website</a>{% endif %}
{% if member.scholar and member.scholar != "" %}<a href="{{ member.scholar | escape }}" class="btn-pill btn-link">Google Scholar</a>{% endif %}
{% if member.github and member.github != "" %}<a href="{{ member.github | escape }}" class="btn-pill btn-git">GitHub</a>{% endif %}
</div>
</article>
{% endfor %}
</div>
{% endif %}

{% if alumni.size > 0 %}
## Alumni

<div class="section-card" style="overflow-x: auto;" markdown="0">
<table class="alumni-table">
<thead><tr><th scope="col">Name</th><th scope="col">Years</th><th scope="col">Details</th></tr></thead>
<tbody>
{% for member in alumni %}
<tr><td>{{ member.name | escape }}</td><td>{{ member.duration | escape }}</td><td>{{ member.info | escape }}</td></tr>
{% endfor %}
</tbody>
</table>
</div>
{% endif %}

<div class="section-card" markdown="0">
<h2>Student and Research Inquiries</h2>
{% if members.size == 0 %}<p>A student and researcher directory is not currently listed on this site.</p>{% endif %}
<p>For information about the team, graduate study, or research collaboration, contact the co-director whose research area matches your interests.</p>
<a href="{{ '/research/' | relative_url }}" class="btn-pill btn-link">Research areas</a>
</div>
