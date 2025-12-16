---
layout: single
title: "Competitions"
permalink: /competitions/
custom_css:
  - /assets/css/competitions.css
---

<!-- ========================= HERO SECTION ========================= -->
<section class="page__hero--overlay">
  <div class="wrapper no-photo">
    <div class="card-content">
      <h1 class="page__title">Competitions</h1>
      <p class="page__lead">
        <span class="subtitle">Blue-team and red-team experience through collegiate cybersecurity competitions.</span>
        <span class="mini">
          My primary focus is <strong>CCDC</strong>, where our team defends a live enterprise network from
          professional red-teamers while handling business tasks and service uptime. Alongside CCDC, I compete in
          SWIFT’s internal <strong>Red vs. Blue</strong> events and started my journey with <strong>Hivestorm</strong>.
        </span>
      </p>
      <p class="page__lead">
        <a class="btn-hero" href="#ccdc">CCDC</a>
        <a class="btn-hero" href="#rvb">SWIFT Red vs. Blue</a>
        <a class="btn-hero" href="#hivestorm">Hivestorm</a>
      </p>
      <a href="#ccdc" class="see-more">See more below</a>
    </div>
  </div>
</section>

---

<!-- ========================= CCDC SECTION ========================= -->
<section id="ccdc" class="content-section section-comps">
  <div class="section-inner">
    <h2>Collegiate Cyber Defense Competition (CCDC)</h2>
    <p>
      The <strong>Collegiate Cyber Defense Competition (CCDC)</strong> is a blue-team competition where student teams
      are tasked with defending a realistic enterprise network against a live red team. While attacks are ongoing, teams
      must also respond to business “injects” such as policy requests, change tickets, and incident reports.
    </p>
    <p>
      I participate in the <strong>Western Regional CCDC (WRCCDC)</strong> with Cal Poly Pomona’s team. The environment
      includes a mix of Windows and Linux systems, critical services (web, mail, directory services, databases), and
      user accounts that must remain functional while being secured.
    </p>
    <h3>Key Responsibilities & Skills</h3>
    <ul>
      <li>Hardening servers and workstations under time pressure while minimizing disruption.</li>
      <li>Locking down services (web, SSH, RDP, databases) and tightening network access control.</li>
      <li>Monitoring logs and alerts to detect active red-team activity and lateral movement.</li>
      <li>Coordinating with teammates to divide roles (Windows, Linux, networking, forensics).</li>
      <li>Responding to “injects” with clear documentation and justifications for security changes.</li>
    </ul>
    <p>
      Learn more about the regional competition here:
      <a href="https://wrccdc.org/" target="_blank" rel="noopener">WRCCDC Official Site →</a>
    </p>
  </div>
</section>

---

<!-- ========================= SWIFT RvB SECTION ========================= -->
<section id="rvb" class="content-section section-comps">
  <div class="section-inner">
    <h2>SWIFT Red vs. Blue (RvB)</h2>
    <p>
      SWIFT’s internal <strong>Red vs. Blue (RvB)</strong> events at Cal Poly Pomona are shorter,
      more focused scrimmages where students can rotate between attacking and defending roles.
      These events are a great way to practice techniques in a controlled, fast-paced setting.
    </p>
    <h3>Experience & Takeaways</h3>
    <ul>
      <li><strong>Blue Team:</strong> Hardening Linux and Windows VMs, closing unnecessary ports, auditing services.</li>
      <li><strong>Red Team:</strong> Enumerating services, exploiting misconfigurations, and testing basic payloads.</li>
      <li><strong>Team Skills:</strong> Communicating findings quickly, sharing indicators of compromise, and tracking changes.</li>
      <li><strong>Process:</strong> Learning to balance speed with stability—avoiding “fixes” that break critical services.</li>
    </ul>
    <p>
      These scrimmages helped me translate theoretical Security+/Network+ knowledge into hands-on defensive
      and offensive techniques.
    </p>
  </div>
</section>

---

<!-- ========================= HIVESTORM SECTION ========================= -->
<section id="hivestorm" class="content-section section-comps with-image">
  <div class="section-inner two-col">
    <div>
      <h2>Hivestorm</h2>
      <p>
        <strong>Hivestorm</strong> was my first cybersecurity competition and a major step into practical blue-team work.
        It is a defensive competition where teams secure and maintain a set of systems against misconfigurations and
        vulnerabilities, while being scored on service uptime and issue remediation.
      </p>
      <h3>What I Learned</h3>
      <ul>
        <li>System hardening basics: user management, file permissions, and service configuration.</li>
        <li>Prioritizing fixes that have the most impact on scoring and security.</li>
        <li>Working under time pressure while staying organized and documenting changes.</li>
        <li>Using checklists, scripts, and notes to avoid repeating manual work across machines.</li>
      </ul>
      <p>
        Hivestorm gave me the confidence to move into larger, more complex competitions like SWIFT RvB and CCDC.
      </p>
    </div>
    <div class="media">
      <img src="{{ "/assets/img/hivestorm.jpg" | relative_url }}"
           alt="Screenshot or photo from the Hivestorm competition"
           style="max-width: 100%; height: auto; border-radius: 14px; box-shadow: 0 12px 34px rgba(0,0,0,.35);">
    </div>
  </div>
</section>

---

<!-- ========================= SUMMARY SECTION ========================= -->
<section id="comps-summary" class="content-section section-comps">
  <div class="section-inner">
    <h2>How Competitions Shape My Skills</h2>
    <p>
      Competitions like <strong>CCDC</strong>, <strong>SWIFT RvB</strong>, and <strong>Hivestorm</strong> provide a bridge
      between certification knowledge and real-world practice. They reinforce:
    </p>
    <ul>
      <li>Technical depth in networking, operating systems, and security controls.</li>
      <li>Teamwork and communication under pressure.</li>
      <li>Operational thinking: keeping systems usable while making them secure.</li>
      <li>Continuous learning through post-event reviews and write-ups.</li>
    </ul>
    <p>
      Together, these experiences shape how I approach my research, projects, and future work
      in defensive cybersecurity.
    </p>
  </div>
</section>
