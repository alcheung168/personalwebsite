---
layout: single
title: "Projects"
permalink: /projects/
custom_css:
  - /assets/css/projects.css
---

<section class="page__hero--overlay">
  <div class="wrapper no-photo">
    <div class="card-content">
      <h1 class="page__title">Projects</h1>
      <p class="page__lead">
        <span class="subtitle">Wavelet-based IoT Device-Type Identification</span>
        <span class="mini">
          Research program at Cal Poly Pomona focusing on classifying IoT devices by type
          from encrypted network traffic. Awarded 2nd place in the Poster Competition at CPP’s
          Cybersecurity Awareness Fair and submitted to conferences including IEEE, NDSS, and Electronics.
        </span>
      </p>

      <p class="page__lead">
        <a class="btn-hero" href="#overview">View Overview</a>
        <a class="btn-hero" href="{{ "/assets/img/research_poster.pdf" | relative_url }}" target="_blank">
          View Poster (PDF)
        </a>
        <a class="btn-hero" href="https://ndss26-fall.hotcrp.com/paper/1953?cap=hcav1953AAnRbiQXsdrdShBPEqShBTeB" target="_blank" rel="noopener">
          NDSS Submission
        </a>
      </p>

      <a href="#overview" class="see-more">See more below</a>
    </div>
  </div>
</section>

---

<section id="overview" class="content-section section-projects">
  <div class="section-inner">
    <h2>Research Program Overview</h2>
    <p>
      This research explores how encrypted traffic patterns can be used to identify
      <strong>IoT device types</strong> (e.g., cameras, sensors, smart plugs) without relying
      on payload inspection or vendor-specific identifiers. The work is part of a research
      program at Cal Poly Pomona and was awarded
      <strong>2nd place</strong> in the Poster Competition at CPP’s
      <em>Cybersecurity Awareness Fair</em>.
    </p>
    <p>
      Our goal is to provide a practical fingerprinting approach for defenders to
      inventory their networks, detect rogue devices, and understand risk at the
      device-type level.
    </p>
  </div>
</section>

<section id="methodology" class="content-section section-projects with-image">
  <div class="section-inner two-col">
    <div>
      <h2>Methodology & Classifiers</h2>
      <p>
        At a high level, our pipeline:
      </p>
      <ul>
        <li>Captures network traffic from representative IoT devices in a controlled lab.</li>
        <li>Extracts flow-level features (timing, sizes, directions) and applies
            <strong>wavelet transforms</strong> to highlight device-specific patterns.</li>
        <li>Feeds these features into traditional machine learning classifiers
            (for example, k-NN, Random Forest, or SVM) tuned to distinguish device types.</li>
      </ul>
      <p>
        You can fill in this section with the exact classifiers and feature sets you used
        (e.g., which wavelet families, how many decomposition levels, final feature vector size, etc.).
      </p>
    </div>
    <div class="media">
      <p>
        <strong>Poster (PDF):</strong><br>
        <a href="{{ "/assets/img/research_poster.pdf" | relative_url }}" target="_blank">
          Download the research poster
        </a>
      </p>
      <p>
        Optionally, you can embed a thumbnail image or a screenshot of the poster here.
      </p>
    </div>
  </div>
</section>

<section id="performance" class="content-section section-projects">
  <div class="section-inner">
    <h2>Performance Summary</h2>
    <p>
      This section is where you describe your evaluation setup and results in more detail:
    </p>
    <ul>
      <li>Datasets: number of devices and device types, capture duration, and lab setup.</li>
      <li>Train/validation/test split strategy.</li>
      <li>Metrics: accuracy, precision/recall, confusion matrices, or macro-averaged scores.</li>
      <li>Key findings (e.g., which device types are easiest or hardest to distinguish, impact of feature choices).</li>
    </ul>
    <p>
      Replace this text with your actual metrics and insights when you’re ready.
    </p>
  </div>
</section>

<section id="publications" class="content-section section-projects">
  <div class="section-inner">
    <h2>Publications & Submissions</h2>
    <p>
      This work has been submitted to multiple venues, including:
    </p>
    <ul>
      <li>
        <strong>NDSS (Network and Distributed System Security Symposium)</strong> – Fall Workshop submission.<br>
        <a href="https://ndss26-fall.hotcrp.com/paper/1953?cap=hcav1953AAnRbiQXsdrdShBPEqShBTeB"
           target="_blank" rel="noopener">View NDSS submission →</a>
      </li>
      <li>
        <strong>IEEE</strong> – conference submission (details/links can be added here).
      </li>
      <li>
        <strong>Electronics (MDPI)</strong> – journal submission (details/links can be added here).
      </li>
    </ul>
    <p>
      As decisions are returned, you can update this section with accepted papers, DOIs,
      and camera-ready links.
    </p>
  </div
