---
layout: default
---

<div align="justify" style="font-family: var(--font-ui); font-size: 1.1rem; line-height: 1.7; margin-bottom: 2rem;">
<strong>Sovereign Intellect</strong> publishes structured trilogies on <strong>intellectual sovereignty</strong> — how independent scientists and polymaths own claims, anchor verifiable provenance, and resist algorithmic erasure in the AI era. Amid hyper-authorship, disciplinary silos, and automated synthesis stripping origin, discovery alone no longer protects originality. Cross-disciplinary minds spanning code, theory, mechanics, and culture need timestamped, machine-readable proof — a permanent fortress so no theorem, artifact, or insight is absorbed, fragmented, or claimed without credit.
</div>


{% assign series_list = site.series | sort: "order" %}
{% assign series_count = series_list | size %}
{% assign current_trilogy = series_list | last %}

<h2 style="margin-bottom: 0.5rem;">
<a href="{{ '/series/' | append: current_trilogy.slug | append: '/' | relative_url }}" style="color: var(--accent-color);">{{ current_trilogy.title }}</a>
<span style="display: inline-block; font-family: var(--font-ui); font-size: 0.75rem; font-weight: 600; letter-spacing: 0.08em; text-transform: uppercase; color: var(--accent-color); border: 1px solid var(--accent-color); padding: 2px 8px; border-radius: 4px; margin-left: 0.75rem; vertical-align: middle;">Current Trilogy</span>
</h2>

<div style="background: var(--bg-secondary); padding: 2rem; border-radius: 8px; border: 1px solid var(--border-color); margin-top: 1.5rem;">

{% assign current_parts = site.posts | where: "series", current_trilogy.slug | sort: "part" %}
{% for essay in current_parts %}
<a href="{{ essay.url | relative_url }}" style="display: block; text-decoration: none;{% unless forloop.last %} margin-bottom: 1.5rem;{% endunless %}">
<h4 style="margin: 0 0 0.5rem 0; color: var(--accent-color); font-size: 1.25rem;">Part {{ essay.part }}: {{ essay.title }}</h4>
<p style="margin: 0; color: var(--text-muted); font-size: 1rem; font-family: var(--font-ui);">{{ essay.subtitle }}</p>
</a>
{% endfor %}

</div>

{% if series_count > 1 %}

{% assign prev_index = series_count | minus: 2 %}
{% assign prev_trilogy = series_list[prev_index] %}

<h2 style="margin-top: 3.5rem; margin-bottom: 0.5rem;">
<a href="{{ '/series/' | append: prev_trilogy.slug | append: '/' | relative_url }}" style="color: var(--accent-color);">{{ prev_trilogy.title }}</a>
<span style="display: inline-block; font-family: var(--font-ui); font-size: 0.75rem; font-weight: 600; letter-spacing: 0.08em; text-transform: uppercase; color: var(--text-muted); border: 1px solid var(--text-muted); padding: 2px 8px; border-radius: 4px; margin-left: 0.75rem; vertical-align: middle;">Previous Trilogy</span>
</h2>

<div style="background: var(--bg-secondary); padding: 2rem; border-radius: 8px; border: 1px solid var(--border-color); margin-top: 1.5rem;">

{% assign prev_parts = site.posts | where: "series", prev_trilogy.slug | sort: "part" %}
{% for essay in prev_parts %}
<a href="{{ essay.url | relative_url }}" style="display: block; text-decoration: none;{% unless forloop.last %} margin-bottom: 1.5rem;{% endunless %}">
<h4 style="margin: 0 0 0.5rem 0; color: var(--accent-color); font-size: 1.25rem;">Part {{ essay.part }}: {{ essay.title }}</h4>
<p style="margin: 0; color: var(--text-muted); font-size: 1rem; font-family: var(--font-ui);">{{ essay.subtitle }}</p>
</a>
{% endfor %}

</div>

<div style="margin-top: 1.75rem; text-align: right;">
<a href="{{ '/trilogies/' | relative_url }}" style="font-family: var(--font-ui); font-size: 1rem; color: var(--accent-color);">View all trilogies →</a>
</div>

{% endif %}
