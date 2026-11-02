---
title: "Teaching"
layout: page
permalink: /teaching/
---

# {{ page.title }}

Course information and study directions related to {{ site.name }} at {{ site.institution }}.

{% comment %}Mark actual courses with lab: true in _data/teaching.yml. Template courses remain excluded.{% endcomment %}
{% assign courses = site.data.teaching | where: "lab", true %}

{% if courses.size > 0 %}
## Courses

{% for course in courses %}
<section class="section-card" markdown="0">
<h3>{% if course.course %}{{ course.course | escape }} — {% endif %}{{ course.title | escape }}</h3>
{% if course.term or course.role %}<p class="text-muted">{{ course.term | escape }}{% if course.term and course.role %} &middot; {% endif %}{{ course.role | escape }}</p>{% endif %}
{% if course.description %}<p>{{ course.description | escape }}</p>{% endif %}
{% if course.url and course.url != "" %}<a href="{{ course.url | escape }}" class="btn-pill btn-website">Course website</a>{% endif %}
</section>
{% endfor %}
{% else %}
<div class="section-card" markdown="0">
<h2>Course Information</h2>
<p>Specific courses, syllabi, and teaching schedules are not currently listed on this site. Please contact the relevant co-director for course information.</p>
<a href="{{ '/team/' | relative_url }}" class="btn-pill btn-link">Faculty contacts</a>
</div>
{% endif %}

## Research-Aligned Study Areas

The following areas describe the lab's research interests and provide context for students exploring related study.

<div class="research-grid" style="grid-template-columns: repeat(auto-fit, minmax(min(100%, 300px), 1fr));" markdown="0">
<section class="research-card">
<div class="research-body">
<h3 class="research-title">AI &amp; Distributed Learning</h3>
<p class="research-desc">Physical AI, federated learning, and distributed learning in connected systems.</p>
<a href="{{ '/research/#federated-learning' | relative_url }}" class="btn-pill btn-link">Research context</a>
</div>
</section>
<section class="research-card">
<div class="research-body">
<h3 class="research-title">Trust &amp; Security</h3>
<p class="research-desc">Trustworthy AI and the security of network and communication infrastructure.</p>
<a href="{{ '/research/#trustworthy-ai' | relative_url }}" class="btn-pill btn-link">Research context</a>
</div>
</section>
<section class="research-card">
<div class="research-body">
<h3 class="research-title">Communication Systems</h3>
<p class="research-desc">MIMO systems and communication-system optimization.</p>
<a href="{{ '/research/#mimo-optimization' | relative_url }}" class="btn-pill btn-link">Research context</a>
</div>
</section>
</div>

<div class="callout callout-info" markdown="0">
<h2 class="callout-title">Graduate Study</h2>
<p>Students interested in the lab's research can <a href="{{ '/team/' | relative_url }}">contact the co-directors</a> with their background and research interests.</p>
</div>
