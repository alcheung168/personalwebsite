---
layout: single
title: "Projects"
permalink: /projects/
custom_css:
  - /assets/css/projects.css
---

<!-- ========================= HERO SECTION ========================= -->
<section class="page__hero--overlay">
  <div class="wrapper no-photo">
    <div class="card-content">
      <h1 class="page__title">Wavelet-Based IoT Device Fingerprinting</h1>
      <p class="page__lead">
        <span class="subtitle">A scalable, resilient framework for identifying IoT devices using encrypted network traffic.</span>
        <span class="mini">
          Awarded <strong>2nd Place</strong> at CPP’s Cybersecurity Awareness Fair Poster Competition and submitted to
          <strong>NDSS</strong>, <strong>IEEE</strong>, and <strong>Electronics (MDPI)</strong>. This research introduces a novel
          fingerprinting method that applies <strong>Wavelet Transforms</strong> (DWT/WST) to network-layer traffic—supporting both
          wired and wireless devices while outperforming traditional time-domain and RF-based methods.
        </span>
      </p>
      <p class="page__lead">
        <a class="btn-hero" href="{{ "/assets/img/research_poster.pdf" | relative_url }}" target="_blank">Poster (PDF)</a>
        <a class="btn-hero" href="https://ndss26-fall.hotcrp.com/paper/1953?cap=hcav1953AAnRbiQXsdrdShBPEqShBTeB"
           target="_blank" rel="noopener">NDSS Submission</a>
      </p>
      <a href="#overview" class="see-more">See more below</a>
    </div>
  </div>
</section>

---

<!-- ========================= OVERVIEW SECTION ========================= -->
<section id="overview" class="content-section section-projects">
  <div class="section-inner">
    <h2>Research Overview</h2>
    <p>
      IoT device fingerprinting traditionally relies on identifiers like MAC addresses or Radio Frequency (RF) emissions.
      However, these approaches fail in modern environments where devices use mixed wired/wireless connectivity,
      identifiers can be spoofed, and RF-based methods are blind to Ethernet traffic.
    </p>
    <p>
      Our research introduces the <strong>Wavelet-Based IoT Device Fingerprint</strong>, the first framework to apply
      <strong>frequency-domain wavelet analysis to encrypted network traffic</strong> for fingerprinting.
      Wavelet-based features capture multi-scale temporal patterns in packet timing and volume—revealing stable,
      device-specific characteristics even when traffic is sparse, noisy, or irregular.
    </p>
    <p>
      This approach significantly improves classification accuracy across diverse IoT environments and remains robust
      even under adversarial conditions such as DDoS attacks.
    </p>
  </div>
</section>

---

<!-- ========================= PIPELINE SECTION ========================= -->
<section id="pipeline" class="content-section section-projects">
  <div class="section-inner">
    <h2>System Architecture</h2>
    <p>
      The full framework consists of four major modules, as described in our paper:
    </p>
    <ul>
      <li>
        <strong>Traffic-to-Image Encoder:</strong>
        Converts raw packet captures into eight time-series signals (e.g., Tx/Rx packet count,
        payload sizes, IAT, TCP window size), then stacks them into a 2D traffic matrix.
      </li>
      <li>
        <strong>Wavelet-Based Feature Extraction:</strong>
        We evaluate both DWT and WST—capturing low-frequency behavior and high-frequency
        burst patterns in IoT communication.
      </li>
      <li>
        <strong>PCA Feature Reduction:</strong>
        Wavelet coefficients are high-dimensional; experiments show 30 PCA components retain
        nearly all useful structure.
      </li>
      <li>
        <strong>Decision Engine:</strong>
        Classifiers (KNN, SVM, Random Forest, XGBoost) distinguish device identity and device type.
      </li>
    </ul>
    <p>
      This four-stage pipeline enables accurate fingerprinting for both wired and wireless IoT devices—
      unifying environments where RF-only methods fail.
    </p>
    <p class="poster-link">
      <strong>Research Poster:</strong>
      <a href="{{ "/assets/img/research_poster.pdf" | relative_url }}" target="_blank">
        Download Poster (PDF)
      </a>
    </p>
  </div>
</section>


---

<!-- ========================= DATASETS SECTION ========================= -->
<section id="datasets" class="content-section section-projects">
  <div class="section-inner">
    <h2>Datasets</h2>
    <p>
      We evaluated the system using three real-world IoT datasets—ranging from small homogeneous networks to large-scale,
      heterogeneous deployments with multiple protocols and attack scenarios:
    </p>
    <table>
      <thead>
        <tr>
          <th>Dataset</th>
          <th>Devices</th>
          <th>Protocols</th>
          <th>Traffic</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>UNSW IoT</td>
          <td>28</td>
          <td>WiFi, MQTT, CoAP, Ethernet</td>
          <td>Benign</td>
        </tr>
        <tr>
          <td>CIC IoT 2022</td>
          <td>60</td>
          <td>WiFi, Zigbee, Z-Wave, Ethernet</td>
          <td>Benign + Attack</td>
        </tr>
        <tr>
          <td>CIC IoT 2023</td>
          <td>105</td>
          <td>WiFi, Zigbee, Z-Wave, MQTT, Ethernet</td>
          <td>Benign + Attack</td>
        </tr>
      </tbody>
    </table>
  </div>
</section>

---

<!-- ========================= SAMPLING RATE SECTION ========================= -->
<section id="sampling" class="content-section section-projects">
  <div class="section-inner">
    <h2>Sampling Rate Sensitivity</h2>
    <p>
      Experiments evaluated sampling intervals from <strong>1–60 seconds</strong>.  
      Across all datasets and models, accuracy sharply decreases as intervals increase.
      The <strong>1-second window</strong> captures essential device behavior while minimizing noise.
    </p>
  </div>
</section>

---

<!-- ========================= PERFORMANCE SECTION ========================= -->
<section id="performance" class="content-section section-projects">
  <div class="section-inner">
    <h2>Performance Evaluation</h2>
    <p>
      Wavelet-based features consistently outperform time-domain baselines for both
      <strong>individual device identification</strong> and <strong>device type classification</strong>.
    </p>
    <h3>Individual Device Identification</h3>
    <p>Baseline vs. DWT vs. WST accuracy across datasets:</p>
    <table>
      <thead>
        <tr>
          <th>Dataset</th>
          <th>Baseline</th>
          <th>DWT</th>
          <th>WST</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>CIC IoT 2022</td>
          <td>72%</td>
          <td>99%</td>
          <td>98%</td>
        </tr>
        <tr>
          <td>CIC IoT 2023</td>
          <td>69%</td>
          <td>99%</td>
          <td>91%</td>
        </tr>
        <tr>
          <td>UNSW IoT</td>
          <td>64%</td>
          <td>81%</td>
          <td>90%</td>
        </tr>
      </tbody>
    </table>
    <p>
      <img src="{{ "/assets/img/graphs/iot_device_identification_accuracy.png" | relative_url }}"
           alt="Device Identification Accuracy Graph"
           style="max-width: 100%; border-radius: 8px; box-shadow: 0 12px 34px rgba(0,0,0,.35);">
    </p>
    <h3>Device Type Classification</h3>
    <table>
      <thead>
        <tr>
          <th>Dataset</th>
          <th>Baseline</th>
          <th>DWT</th>
          <th>WST</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>CIC IoT 2022</td>
          <td>54%</td>
          <td>90%</td>
          <td>92%</td>
        </tr>
        <tr>
          <td>CIC IoT 2023</td>
          <td>68%</td>
          <td>99%</td>
          <td>96%</td>
        </tr>
        <tr>
          <td>UNSW IoT</td>
          <td>64%</td>
          <td>84%</td>
          <td>87%</td>
        </tr>
      </tbody>
    </table>
    <p>
      <img src="{{ "/assets/img/graphs/iot_device_type_accuracy.png" | relative_url }}"
           alt="Device Type Accuracy Graph"
           style="max-width: 100%; border-radius: 8px; box-shadow: 0 12px 34px rgba(0,0,0,.35);">
    </p>

  </div>
</section>

---

<!-- ========================= ADVERSARIAL SECTION ========================= -->
<section id="robustness" class="content-section section-projects">
  <div class="section-inner">
    <h2>Robustness Under DDoS Traffic</h2>
    <p>
      Under attack conditions, baseline features collapse (accuracy < 20%).
      Wavelet features remain stable:
    </p>
    <ul>
      <li><strong>DWT:</strong> 40–68% accuracy</li>
      <li><strong>WST:</strong> 47–73% accuracy (best overall robustness) </li>
    </ul>
    <p>
      This demonstrates the resilience of frequency-domain representations during network saturation.
    </p>
  </div>
</section>

---

<!-- ========================= CONTRIBUTIONS SECTION ========================= -->
<section id="contributions" class="content-section section-projects">
  <div class="section-inner">
    <h2>Key Contributions</h2>
    <ul>
      <li>First application of wavelet-based analysis to network-layer IoT device fingerprinting.</li>
      <li>Supports both wired and wireless devices, unlike RF-only approaches.</li>
      <li>Extracts multi-scale temporal patterns from encrypted traffic.</li>
      <li>Achieves near-perfect accuracy across datasets with DWT/WST + XGBoost.</li>
      <li>Significantly more robust to adversarial traffic (DDoS) than baseline methods.</li>
    </ul>
  </div>
</section>

---

<!-- ========================= PUBLICATIONS SECTION ========================= -->
<section id="publications" class="content-section section-projects">
  <div class="section-inner">
    <h2>Publications & Submissions</h2>
    <ul>
      <li>
        <strong>NDSS 2026 Workshop</strong> – Submitted
        (<a href="https://ndss26-fall.hotcrp.com/paper/1953?cap=hcav1953AAnRbiQXsdrdShBPEqShBTeB" target="_blank">View Submission</a>)
      </li>
      <li><strong>IEEE</strong> – Extended submission in progress</li>
      <li><strong>Electronics (MDPI)</strong> – Planned journal submission</li>
      <li><strong>CPP Cybersecurity Awareness Fair</strong> – Poster awarded <strong>2nd Place</strong></li>
    </ul>
  </div>
</section>

---

<!-- ========================= FUTURE WORK SECTION ========================= -->
<section id="future-work" class="content-section section-projects">
  <div class="section-inner">
    <h2>Future Work</h2>
    <ul>
      <li>Deploy real-time fingerprinting on low-cost gateway hardware.</li>
      <li>Integrate federated learning for privacy-preserving edge training.</li>
      <li>Explore hybrid deep learning models for complex traffic patterns.</li>
      <li>Scale the evaluation to enterprise-level IoT environments.</li>
    </ul>
  </div>
</section>
