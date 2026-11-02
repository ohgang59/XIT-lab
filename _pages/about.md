---
title: "About"
layout: page
permalink: /about/
---

# {{ page.title }}

**{{ site.name }}** is the {{ site.title }} at {{ site.institution }}. We work across IT, AI applications, and communication-system technologies, with Physical AI as a core focus.

<div class="section-card pi-card" markdown="0">
<img src="{{ '/images/logo.png' | relative_url }}" alt="X-IT Lab logo" width="240" style="width: 100%; max-width: 240px; height: auto;">
<div>
<h2 class="pi-name">Cross. Connection. Action.</h2>
<p>The X in X-IT stands for the cross of disciplines. Our work connects AI with communication systems and the physical world, bringing together trustworthy learning, network security, and communication-system optimization.</p>
<a href="{{ '/research/' | relative_url }}" class="btn-pill btn-website">Explore our research</a>
</div>
</div>

## AI in the Physical World

Physical AI interacts with the real world through robots, drones, vehicles, and sensor networks. We study trustworthy AI, federated and distributed learning, and communication-system optimization to understand how AI can operate safely on real communication infrastructure.

<div class="chip-container" markdown="0">
<a href="{{ '/research/#physical-ai' | relative_url }}" class="chip">Physical AI</a>
<a href="{{ '/research/#federated-learning' | relative_url }}" class="chip">Federated Learning</a>
<a href="{{ '/research/#trustworthy-ai' | relative_url }}" class="chip">Trustworthy AI</a>
<a href="{{ '/research/#network-security' | relative_url }}" class="chip">Network Security</a>
<a href="{{ '/research/#mimo-optimization' | relative_url }}" class="chip">MIMO Optimization</a>
<a href="{{ '/research/#communication-systems' | relative_url }}" class="chip">Communication Systems</a>
</div>

<div class="section-card" markdown="0">
<h2>Joint Leadership</h2>
<p>The lab brings together two complementary research perspectives:</p>
<ul>
{% for director in site.data.pi[0].education %}
<li>{{ director }}</li>
{% endfor %}
</ul>
<a href="{{ '/team/' | relative_url }}" class="btn-pill btn-link">Meet the team</a>
</div>

## Study and Career Directions

The lab's research connects to AI and network engineering, AI security research, Physical AI in robotics and mobility, and further graduate study in related fields.

<div class="callout callout-info" markdown="0">
<h2 class="callout-title">Get in Touch</h2>
<p>For research, collaboration, or graduate-study inquiries, contact <a href="mailto:bcchung@gnu.ac.kr">Prof. Byung Chang Chung</a> or <a href="mailto:junbeom@gnu.ac.kr">Prof. Junbeom Kim</a>.</p>
</div>
