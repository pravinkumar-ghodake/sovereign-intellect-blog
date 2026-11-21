---
layout: default
title: Trilogies
permalink: /trilogies/
---

# Trilogies

<div align="justify" style="font-family: var(--font-ui); font-size: 1.05rem; line-height: 1.65; color: var(--text-muted); margin-bottom: 2.5rem;">
<strong>Sovereign Intellect</strong> is a sequential archive of structured trilogies dedicated to <strong>intellectual sovereignty</strong>—the practice of owning authorship, anchoring verifiable provenance, and building self-reliant systems of knowledge. Spanning algorithmic defense, single-author rigor, and permanent evidentiary records, each trilogy documents how independent minds protect their work against dilution and erasure in the AI era.
</div>

{% assign series_list = site.data.series %}

{% for trilogy in series_list %}
## [{{ trilogy.title }}]({{ '/series/' | append: trilogy.slug | append: '/' | relative_url }})

{% if trilogy.description %}
<p style="font-family: var(--font-ui); font-size: 0.98rem; color: var(--text-muted); margin-top: 0.35rem;">{{ trilogy.description }}</p>
{% endif %}

<div style="background: var(--bg-secondary); padding: 2rem; border-radius: 8px; border: 1px solid var(--border-color); margin-top: 1.25rem; margin-bottom: 2.5rem;">

{% for part in trilogy.parts %}
<a href="{{ part.url | relative_url }}" style="display: block; text-decoration: none;{% unless forloop.last %} margin-bottom: 1.5rem;{% endunless %}">
<h3 style="margin: 0 0 0.5rem 0; color: var(--accent-color); font-size: 1.25rem;">Part {{ part.number }}: {{ part.title }}</h3>
<p style="margin: 0; color: var(--text-muted); font-size: 1rem; font-family: var(--font-ui);">{{ part.subtitle }}</p>
</a>
{% endfor %}

</div>
{% endfor %}
