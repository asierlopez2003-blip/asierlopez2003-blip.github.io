---
layout: archive
title: "CV"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}

{% assign titulos     = site.data.titulos %}
{% assign experiencia = site.data.experiencia %}
{% assign habilidades = site.data.habilidades %}
{% assign congresos  = site.data.congresos %}

This is the condensed version. The [academic record](/expediente/) is the
complete one, including supervision, awards and project detail.

Education
======

{%- assign educacion = "fisica,internacional" | split: "," %}
{%- for grupo in titulos %}
{%- if educacion contains grupo.id %}
### {{ grupo.name }}
{%- for e in grupo.entries %}
* **{{ e.title }}**, {{ e.institution }}{% if e.ended == "present" %} (ongoing){% else %}, {{ e.ended }}{% endif %}
{%- if e.grade %} — grade {{ e.grade }}{% endif %}
{%- if e.supervisor %} — supervisor {{ e.supervisor }}{% endif %}{% if e.co_supervisor %} — co-supervisor {{ e.co_supervisor }}{% endif %}
{%- endfor %}
{%- endif %}
{%- endfor %}

Research Experience
======

{%- for e in experiencia %}
* **{{ e.role }}**, {{ e.org }}{% if e.location %}, {{ e.location }}{% endif %} ({{ e.started }}–{{ e.ended }}){% if e.supervisor %} — supervisor {{ e.supervisor }}{% endif %}{% if e.co_supervisor %} — co-supervisor {{ e.co_supervisor }}{% endif %}
{%- endfor %}

Certifications
======

{%- assign certificados = "computacion,biomedical" | split: "," %}
{%- for grupo in titulos %}
{%- if certificados contains grupo.id %}
### {{ grupo.name }}
{%- for e in grupo.entries %}
* {{ e.title }}{% if e.ended == "present" %} (ongoing){% endif %}{% if e.credits %} — {{ e.credits }}{% endif %} — {{ e.institution }}
{%- endfor %}
{%- endif %}
{%- endfor %}

Technical Skills
======

{%- for h in habilidades %}
{%- unless h.name == "Languages" %}
### {{ h.name }}

{% for i in h.items %}{% if i.name %}{{ i.name }}{% else %}{{ i }}{% endif %}{% unless forloop.last %}, {% endunless %}{% endfor %}

{%- endunless %}
{%- endfor %}

Languages
======

{%- for h in habilidades %}
{%- if h.name == "Languages" %}
{% for i in h.items %}* {{ i.name }} — {{ i.level }}
{% endfor %}
{%- endif %}
{%- endfor %}

Conferences &amp; Presentations
======

{%- if congresos and congresos.size > 0 %}
{%- for c in congresos %}
* {{ c.title }} — {{ c.kind }}, {{ c.event }}, {{ c.location }} ({{ c.date }})
{%- endfor %}
{%- else %}
* No talks recorded yet.
{%- endif %}

<!--
  A per-application PDF is not linked here on purpose. Those are generated with
  RenderCV from `cv/cv.yaml`, which is reconstructed in Phase 5, so each version
  can be filtered for a specific call instead of being one fixed document.
-->
