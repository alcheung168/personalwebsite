---
layout: home
title: "Hi, I'm Adam Cheung"
subtitle: "Cybersecurity & Networks — projects, competitions, and certifications"
author_profile: true
# Show featured portfolio cards on the homepage
entries_layout: grid
---

<!-- Hero buttons -->
<p>
  <a class="btn btn--primary" href="/projects/">View Projects</a>
  <a class="btn" href="/about/">About Me</a>
</p>

<!-- Feature row (3 highlights). Replace images/links with your own -->
{% include feature_row
  id="highlights"
  type="left"
  img_path="/assets/img"
  features = [
    {
      title: "IoT Traffic Classifier",
      excerpt: "C + OpenSSL pipeline for secure data capture and device-type classification.",
      url: "/projects/iot-traffic-classifier/",
      image_path: "/assets/img/iot-classifier-thumb.jpg"
    },
    {
      title: "SWIFT CTF Placements",
      excerpt: "Writeups and techniques from CPP SWIFT competitions.",
      url: "/competitions/swift-ctf-2025/",
      image_path: "/assets/img/ctf-thumb.jpg"
    },
    {
      title: "CompTIA Network+ & Security+",
      excerpt: "Foundational certs with labs and notes.",
      url: "/certifications/comptia-network-plus/",
      image_path: "/assets/img/cert-thumb.jpg"
    }
  ]
%}
