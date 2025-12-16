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
        <span class="subtitle">Wavelet-Based IoT Device Fingerprinting for Network Security</span>
        <span class="mini">
          Research program at Cal Poly Pomona exploring how network traffic can be used
          to fingerprint IoT devices and identify device <em>types</em> for network defense.
          Awarded <strong>2nd place</strong> in the Poster Competition at CPP’s
          Cybersecurity Awareness Fair and submitted to venues including IEEE, NDSS, and Electronics.
        </span>
      </p>
      <p class="page__lead">
        <a class="btn-hero" href="{{ "/assets/img/research_poster.pdf" | relative_url }}" target="_blank">
          View Poster (PDF)
        </a>
        <a class="btn-hero" href="https://ndss26-fall.hotcrp.com/paper/1953?cap=hcav1953AAnRbiQXsdrdShBPEqShBTeB"
           target="_blank" rel="noopener">
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
      Modern networks are full of heterogeneous IoT devices that often run opaque firmware and
      communicate over encrypted channels. Our project asks a simple question:
      <strong>can we reliably identify what type of IoT device is on the network by looking only at
      its encrypted traffic patterns?</strong>
    </p>
    <p>
      To answer this, we proposed a <strong>wavelet-based IoT device fingerprinting framework</strong>
      that passively observes traffic at the gateway and extracts multi-scale features from packet
      timing and size patterns. This framework supports both wired and wireless devices and does not
      require any modification to the devices themselves. :contentReference[oaicite:0]{index=0}
    </p>
    <p>
      The work was conducted under Professor Abdelfattah Amamra in the Computer Science Department
      at Cal Poly Pomona and earned <strong>2nd place</strong> in the
      <em>CPP Cybersecurity Awareness Fair</em> Poster Competition.
    </p>
  </div>
</section>

<section id="pipeline" class="content-section section-projects with-image">
  <div class="section-inner two-col">
    <div>
      <h2>System Pipeline</h2>
      <p>
        Our pipeline operates entirely at the network layer and is designed for deployment at a
        gateway or monitoring tap:
      </p>
      <ul>
        <li>Passively capture traffic from IoT devices in a lab environment.</li>
        <li>Aggregate packets into flows and sample statistics over fixed time intervals.</li>
        <li>
          Apply <strong>Discrete Wavelet Transform (DWT)</strong> and
          <strong>Wavelet Scattering Transform (WST)</strong> to capture multi-scale patterns
          in the time–frequency domain. :contentReference[oaicite:1]{index=1}
        </li>
        <li>
          Reduce feature dimensionality with <strong>PCA</strong>, keeping ~30 most informative features
          to balance accuracy and efficiency.
        </li>
        <li>
          Train machine learning classifiers (XGBoost, Random Forest, SVM, KNN) to perform:
          <ul>
            <li><strong>Individual device identification</strong></li>
            <li><strong>Device type classification</strong> (camera, sensor, plug, etc.)</li>
          </ul>
        </li>
      </ul>
    </div>
    <div class="media">
      <p><strong>Research Poster</strong></p>
      <p>
        You can view the full poster here:<br>
        <a href="{{ "/assets/img/research_poster.pdf" | relative_url }}" target="_blank">
          Wavelet-Based IoT Device Fingerprinting for Network Security (PDF)
        </a>
      </p>
    </div>
  </div>
</section>

<section id="datasets" class="content-section section-projects">
  <div class="section-inner">
    <h2>Experimental Datasets</h2>
    <p>
      We evaluated the framework on three publicly available IoT datasets to test scalability
      and generality across protocols and environments: :contentReference[oaicite:2]{index=2}
    </p>
    <ul>
      <li>
        <strong>UNSW IoT</strong> – 28 devices, WiFi / CoAP / Ethernet, benign traffic.
      </li>
      <li>
        <strong>CIC IoT 2022</strong> – 60 devices, WiFi / Zigbee / Z-Wave / Ethernet,
        benign and attack traffic.
      </li>
      <li>
        <strong>CIC IoT 2023</strong> – 105 devices, WiFi / Zigbee / Z-Wave / MQTT / Ethernet,
        benign and attack traffic.
      </li>
    </ul>
    <p>
      These datasets include both normal behavior and DDoS-style attacks, allowing us to test
      fingerprint robustness under noisy conditions.
    </p>
  </div>
</section>

<section id="sampling" class="content-section section-projects">
  <div class="section-inner">
    <h2>Sampling Rate Analysis</h2>
    <p>
      The sampling interval controls how coarsely we summarize traffic. We evaluated sampling
      rates from 1 to 60 seconds and found that a <strong>1-second window</strong> provides the
      best trade-off—fine-grained enough to capture transient behaviors without introducing
      excessive noise. :contentReference[oaicite:3]{index=3}
    </p>
  </div>
</section>

<section id="performance" class="content-section section-projects">
  <div class="section-inner">
    <h2>Performance Summary</h2>
    <p>
      We compare baseline time-domain features against wavelet-based features (DWT and WST)
      across all datasets and tasks. Wavelet features consistently yield large accuracy gains
      for both <strong>individual device identification</strong> and
      <strong>device type classification</strong>.
    </p>
    <h3>Individual Device Identification</h3>
    <p>
      Accuracy comparison for identifying specific IoT devices (per device) using XGBoost:
    </p>
    <!-- Table: Device Identification Accuracy -->
    <table>
      <thead>
        <tr>
          <th>Dataset</th>
          <th>Baseline<br>(time-domain)</th>
          <th>DWT<br>(wavelet features)</th>
          <th>WST<br>(wavelet scattering)</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>CICIoT2022</td>
          <td>72%</td>
          <td>99%</td>
          <td>98%</td>
        </tr>
        <tr>
          <td>CICIoT2023</td>
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
      Wavelet-based features dramatically improve identification accuracy, reaching up to
      <strong>99–100%</strong> on several datasets.
    </p>
    <!-- Graph: Device Identification Accuracy -->
    <p>
      <img src="{{ "/assets/img/graphs/iot_device_identification_accuracy.png" | relative_url }}"
           alt="Bar chart showing individual device identification accuracy for baseline, DWT, and WST across CICIoT2022, CICIoT2023, and UNSW IoT datasets."
           style="max-width: 100%; height: auto; border-radius: 8px; box-shadow: 0 12px 34px rgba(0,0,0,.35);">
    </p>
    <h3>Device Type Classification</h3>
    <p>
      Accuracy comparison for classifying devices by type (e.g., camera, sensor, plug):
    </p>
    <!-- Table: Device Type Classification Accuracy -->
    <table>
      <thead>
        <tr>
          <th>Dataset</th>
          <th>Baseline<br>(time-domain)</th>
          <th>DWT<br>(wavelet features)</th>
          <th>WST<br>(wavelet scattering)</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>CICIoT2022</td>
          <td>54%</td>
          <td>90%</td>
          <td>92%</td>
        </tr>
        <tr>
          <td>CICIoT2023</td>
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
      Device type classification also benefits strongly from wavelet features, achieving
      <strong>near-perfect accuracy</strong> on multiple datasets and providing a practical way
      to inventory device types in an encrypted network.
    </p>
    <!-- Graph: Device Type Classification Accuracy -->
    <p>
      <img src="{{ "/assets/img/graphs/iot_device_type_accuracy.png" | relative_url }}"
           alt="Bar chart showing device type classification accuracy for baseline, DWT, and WST across CICIoT2022, CICIoT2023, and UNSW IoT datasets."
           style="max-width: 100%; height: auto; border-radius: 8px; box-shadow: 0 12px 34px rgba(0,0,0,.35);">
    </p>
  </div>
</section>


<section id="contributions" class="content-section section-projects">
  <div class="section-inner">
    <h2>Key Contributions</h2>
    <ul>
      <li>
        <strong>Wavelet IoT Device Fingerprint Framework:</strong>
        Novel use of DWT and WST on network-layer traffic to overcome limitations of
        RF-based and time-domain approaches.
      </li>
      <li>
        <strong>Multi-Scale Pattern Capture:</strong>
        Demonstrated that wavelet features capture both coarse device behavior and fine-grained
        timing quirks, leading to robust fingerprints across heterogeneous devices.
      </li>
      <li>
        <strong>Superior Performance:</strong>
        Consistent, large accuracy gains across three real-world datasets for both
        device ID and device type ID.
      </li>
      <li>
        <strong>Deployment-Ready Design:</strong>
        Passive gateway-level collection supporting both wired and wireless IoT devices
        without firmware changes or special RF hardware.
      </li>
    </ul>
  </div>
</section>

<section id="publications" class="content-section section-projects">
  <div class="section-inner">
    <h2>Publications & Submissions</h2>
    <ul>
      <li>
        <strong>NDSS 2026 Conference</strong> – Wavelet-based IoT fingerprinting paper submitted and currently under review.<br>
        <a href="https://ndss26-fall.hotcrp.com/paper/1953?cap=hcav1953AAnRbiQXsdrdShBPEqShBTeB"
           target="_blank" rel="noopener">View NDSS submission →</a>
      </li>
      <li>
        <strong>IEEE & Electronics (MDPI)</strong> – Additional submissions in progress
        focusing on extended evaluation and systemization.
      </li>
      <li>
        <strong>CPP Cybersecurity Awareness Fair</strong> – Poster presented and awarded
        <strong>2nd place</strong> in the student poster competition.
      </li>
    </ul>
  </div>
</section>

<section id="future-work" class="content-section section-projects">
  <div class="section-inner">
    <h2>Future Work</h2>
    <ul>
      <li>Real-time deployment and optimization on low-cost gateway hardware.</li>
      <li>Exploring <strong>federated learning</strong> for privacy-preserving fingerprinting.</li>
      <li>Integrating deep learning models with wavelet features for more complex traffic patterns.</li>
      <li>Evaluating at larger scale in distributed IoT environments.</li>
    </ul>
  </div>
</section>

