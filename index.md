---
layout: default
---

<div align="justify" style="font-family: var(--font-ui); font-size: 1.1rem; line-height: 1.7; margin-bottom: 3rem;">
<strong>Sovereign Intellect</strong> publishes structured trilogies on how independent researchers own their claims, anchor their provenance, and resist algorithmic erasure in the AI era. We believe that in the age of AI and hyper-authorship, the individual mind must build its own fortress.
</div>

{% assign series_list = site.data.series %}
{% assign series_count = series_list | size %}

## Current Trilogy

{% assign current_trilogy = series_list | last %}
### [{{ current_trilogy.title }}]({{ '/series/' | append: current_trilogy.slug | append: '/' | relative_url }})

<div style="background: var(--bg-secondary); padding: 2rem; border-radius: 8px; border: 1px solid var(--border-color); margin-top: 1.5rem;">

{% for part in current_trilogy.parts %}
<a href="{{ part.url | relative_url }}" style="display: block; text-decoration: none;{% unless forloop.last %} margin-bottom: 1.5rem;{% endunless %}">
<h3 style="margin: 0 0 0.5rem 0; color: var(--accent-color); font-size: 1.25rem;">Part {{ part.number }}: {{ part.title }}</h3>
<p style="margin: 0; color: var(--text-muted); font-size: 1rem; font-family: var(--font-ui);">{{ part.subtitle }}</p>
</a>
{% endfor %}

</div>

{% if series_count > 1 %}

## Previous Trilogy

{% assign prev_index = series_count | minus: 2 %}
{% assign prev_trilogy = series_list[prev_index] %}

### [{{ prev_trilogy.title }}]({{ '/series/' | append: prev_trilogy.slug | append: '/' | relative_url }})

<div style="background: var(--bg-secondary); padding: 2rem; border-radius: 8px; border: 1px solid var(--border-color); margin-top: 1.5rem; margin-bottom: 1.5rem;">

{% for part in prev_trilogy.parts %}
<a href="{{ part.url | relative_url }}" style="display: block; text-decoration: none;{% unless forloop.last %} margin-bottom: 1.5rem;{% endunless %}">
<h3 style="margin: 0 0 0.5rem 0; color: var(--accent-color); font-size: 1.25rem;">Part {{ part.number }}: {{ part.title }}</h3>
<p style="margin: 0; color: var(--text-muted); font-size: 1rem; font-family: var(--font-ui);">{{ part.subtitle }}</p>
</a>
{% endfor %}

</div>

<div style="font-family: var(--font-ui); font-size: 0.95rem; text-align: right; margin-top: 0.5rem;">
  <a href="{{ '/trilogies/' | relative_url }}">Browse all trilogies &rarr;</a>
</div>

{% endif %}
