---
layout: default
---

<div align="justify" style="font-family: var(--font-ui); font-size: 1.1rem; line-height: 1.7; margin-bottom: 3rem;">
<strong>Sovereign Intellect</strong> publishes structured trilogies on how independent researchers own their claims, anchor their provenance, and resist algorithmic erasure in the AI era. We believe that in the age of AI and hyper-authorship, the individual mind must build its own fortress.
</div>

{% assign series_list = site.data.series %}

## Current Trilogy

{% for trilogy in series_list %}
{% if forloop.last %}
### [{{ trilogy.title }}]({{ '/series/' | append: trilogy.slug | append: '/' | relative_url }})

<div style="background: var(--bg-secondary); padding: 2rem; border-radius: 8px; border: 1px solid var(--border-color); margin-top: 1.5rem;">

{% for part in trilogy.parts %}
<a href="{{ part.url | relative_url }}" style="display: block; text-decoration: none;{% unless forloop.last %} margin-bottom: 1.5rem;{% endunless %}">
  <h3 style="margin: 0 0 0.5rem 0; color: var(--accent-color); font-size: 1.25rem;">Part {{ part.number }}: {{ part.title }}</h3>
  <p style="margin: 0; color: var(--text-muted); font-size: 1rem; font-family: var(--font-ui);">{{ part.subtitle }}</p>
</a>
{% endfor %}

</div>
{% endif %}
{% endfor %}

{% assign series_count = series_list | size %}
{% if series_count > 1 %}

## Previous Trilogies

{% for trilogy in series_list %}
{% unless forloop.last %}
### [{{ trilogy.title }}]({{ '/series/' | append: trilogy.slug | append: '/' | relative_url }})

<div style="background: var(--bg-secondary); padding: 2rem; border-radius: 8px; border: 1px solid var(--border-color); margin-top: 1.5rem; margin-bottom: 2rem;">

{% for part in trilogy.parts %}
<a href="{{ part.url | relative_url }}" style="display: block; text-decoration: none;{% unless forloop.last %} margin-bottom: 1.5rem;{% endunless %}">
  <h3 style="margin: 0 0 0.5rem 0; color: var(--accent-color); font-size: 1.25rem;">Part {{ part.number }}: {{ part.title }}</h3>
  <p style="margin: 0; color: var(--text-muted); font-size: 1rem; font-family: var(--font-ui);">{{ part.subtitle }}</p>
</a>
{% endfor %}

</div>
{% endunless %}
{% endfor %}

{% endif %}
