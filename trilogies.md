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
<h2 style="margin-bottom: 0.5rem;">
<a href="{{ '/series/' | append: trilogy.slug | append: '/' | relative_url }}" style="color: var(--accent-color);">{{ trilogy.title }}</a>{% if forloop.last %} <span style="display: inline-block; font-family: var(--font-ui); font-size: 0.75rem; font-weight: 600; letter-spacing: 0.08em; text-transform: uppercase; color: var(--accent-color); border: 1px solid var(--accent-color); padding: 2px 8px; border-radius: 4px; margin-left: 0.75rem; vertical-align: middle;">Current</span>{% endif %}
</h2>

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

<div style="margin-top: 3rem; text-align: right; font-family: var(--font-ui);">
<a href="{{ '/' | relative_url }}">← Return home</a>
</div>
