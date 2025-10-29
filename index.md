---
layout: splash
title: "I'm Adam Cheung."
subtitle: "Cybersecurity • Networks • Systems"
# hero header
header:
  overlay_image: /assets/img/hero.jpg      # add this image (next step)
  overlay_filter: 0.35                     # darken the image
  overlay_color: "#0a0f1f"                 # subtle midnight tint
  actions:
    - label: "Resume"
      url: "{{ '/assets/resume.pdf' | relative_url }}"
    - label: "Contact"
      url: "mailto:alcheung168@gmail.com"
excerpt: >
  I build secure communication systems, analyze network traffic, and compete in CTFs.
  Here are some highlights ↓
# show avatar + sidebar on splash
author_profile: true
---

{% include feature_row
  id="highlights"
  type="center"
  %}

{% capture feature_row %}
{% endcapture %}

{% assign features = site.projects | sort: 'date' | reverse | slice: 0, 3 %}
{% include feature_row id="highlights" type="center" %}
