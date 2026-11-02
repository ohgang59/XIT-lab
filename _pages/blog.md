---
title: "Blog"
layout: page
permalink: /blog/
---

# {{ page.title }}

Research notes and updates from {{ site.name }}.

{% comment %}Add lab: true to actual lab posts. The two template demonstration posts are not listed here.{% endcomment %}
{% assign posts = site.posts | where: "lab", true | sort: "date" | reverse %}

{% if posts.size > 0 %}
## Research Notes

{% for post in posts %}
<article class="section-card" markdown="0">
<p class="text-muted"><time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%B %-d, %Y" }}</time>{% if post.author %} &middot; {{ post.author | escape }}{% endif %}</p>
<h2><a href="{{ post.url | relative_url }}">{{ post.title | escape }}</a></h2>
<p>{{ post.excerpt | strip_html | truncatewords: 45 }}</p>
<a href="{{ post.url | relative_url }}" class="btn-pill btn-link" aria-label="Read {{ post.title | escape }}">Read article</a>
</article>
{% endfor %}
{% else %}
<div class="section-card" markdown="0">
<h2>Research Notes</h2>
<p>No lab research articles are currently posted here. Explore our <a href="{{ '/research/' | relative_url }}">research overview</a> and <a href="{{ '/publications/' | relative_url }}">publication profiles</a> for information about the lab's work.</p>
</div>
{% endif %}

{% if site.data.news.size > 0 %}
<div class="section-card" markdown="0">
<h2>Latest Lab Updates</h2>
<div class="news-timeline">
{% for article in site.data.news limit:3 %}
<article class="news-item">
<div class="news-date"><time datetime="{{ article.date | date: '%Y-%m-%d' }}">{{ article.date | date: "%B %-d, %Y" }}</time></div>
<div class="news-headline">{{ article.headline }}</div>
</article>
{% endfor %}
</div>
<p style="margin-top: var(--space-4);"><a href="{{ '/allnews.html' | relative_url }}">See all news &rarr;</a></p>
</div>
{% endif %}
