---
title: "News"
layout: page
permalink: /allnews.html
---

# {{ page.title }}

Announcements and updates from {{ site.name }} at {{ site.institution }}.

<div class="section-card" markdown="0">
<h2>Lab News</h2>
{% if site.data.news.size > 0 %}
<div class="news-timeline">
{% for article in site.data.news %}
<article class="news-item">
<div class="news-date"><time datetime="{{ article.date | date: '%Y-%m-%d' }}">{{ article.date | date: "%B %-d, %Y" }}</time></div>
<div class="news-headline">{{ article.headline }}</div>
</article>
{% endfor %}
</div>
{% else %}
<p>No lab announcements are currently listed.</p>
{% endif %}
</div>

<div class="d-flex flex-wrap gap-2" markdown="0">
<a href="{{ '/' | relative_url }}" class="btn-pill btn-link">Back to home</a>
<a href="{{ '/blog/' | relative_url }}" class="btn-pill btn-link">Research notes &amp; updates</a>
</div>
