---
layout: default
title: HFTrack
---

<section class="hero" id="top">
  <div class="hero-copy">
    <span class="eyebrow">Bachelor's Degree Thesis · University of Salento</span>
    <h1><span>♥</span> HFTrack</h1>
    <h2>Mobile Frontend Prototype for Heart Failure Monitoring</h2>
    <p>HFTrack is a Flutter mobile frontend prototype for patients, developed as part of a bachelor's thesis on remote monitoring systems for heart failure. It integrates a <strong>Movesense MD sensor</strong> through <strong>Bluetooth Low Energy (BLE)</strong> to acquire and display heart rate and electrocardiogram data in real time.</p>
    <div class="actions">
      <a class="button primary" href="#demo">Watch demo</a>
      <a class="button" href="https://github.com/UniSalento-IDALab-Bachelor-Thesis/tesi-hftrack-FrancescoFerraro">Complete repository</a>
    </div>
  </div>
  <div class="phone-shot">
    <img src="{{ '/docs/hftrack-connected.jpg' | relative_url }}" alt="HFTrack dashboard with Movesense sensor connected">
  </div>
</section>

<div class="notice"><strong>Academic prototype.</strong> HFTrack is not a certified medical device and must not be used for diagnosis, treatment decisions, or emergency monitoring.</div>

<section>
  <div class="section-heading">
    <span class="eyebrow">At a glance</span>
    <h2>Patient-side monitoring in one mobile interface</h2>
  </div>
  <div class="feature-grid">
    <article class="card"><div class="icon">♥</div><h3>Heart Rate</h3><p>Real-time BPM acquired from the Movesense MD wearable.</p></article>
    <article class="card"><div class="icon">⌁</div><h3>Live ECG</h3><p>Continuous ECG visualization with samples acquired at 256 Hz.</p></article>
    <article class="card"><div class="icon">◉</div><h3>BLE + Movesense</h3><p>Sensor discovery, connection management and MDS subscriptions over BLE.</p></article>
    <article class="card"><div class="icon">▤</div><h3>PDF Export</h3><p>User-controlled ECG recording with multi-row document generation.</p></article>
  </div>
</section>

<section id="demo" class="split">
  <div>
    <span class="eyebrow">Application preview</span>
    <h2>HFTrack in action</h2>
    <p>The dashboard combines live wearable measurements with patient-oriented health information. The interface also reacts to Bluetooth and sensor connection states.</p>
    <a class="button primary" href="{{ '/docs/hftrack-demo.mp4' | relative_url }}">▶ Watch the short demo</a>
  </div>
  <div class="screens">
    <figure><img src="{{ '/docs/hftrack-connected.jpg' | relative_url }}" alt="Connected Movesense sensor and live ECG"><figcaption>Movesense connected</figcaption></figure>
    <figure><img src="{{ '/docs/hftrack-bluetooth-disabled.jpg' | relative_url }}" alt="HFTrack with Bluetooth disabled"><figcaption>Bluetooth unavailable</figcaption></figure>
  </div>
</section>

<section class="dark-section">
  <div class="section-heading">
    <span class="eyebrow">Real-time monitoring</span>
    <h2>Movesense MD, BLE and live ECG</h2>
  </div>
  <div class="monitor-grid">
    <div>
      <p>HFTrack uses the <strong>Movesense Device Service (MDS)</strong> and the <strong>Whiteboard resource model</strong>. The smartphone acts as the client and subscribes to the sensor resources required by the frontend.</p>
      <pre><code>/Meas/HR
/Meas/ECG/256</code></pre>
      <p>The ECG resource provides data sampled at <strong>256 Hz</strong>. The application decodes received events and updates the heart-rate value and scrolling ECG chart.</p>
    </div>
    <img src="{{ '/docs/hftrack-connected.jpg' | relative_url }}" alt="HFTrack live ECG screen">
  </div>
</section>

<section>
  <div class="section-heading">
    <span class="eyebrow">Recording</span>
    <h2>ECG recording and PDF export</h2>
    <p>After a recording is stopped, HFTrack can generate a landscape document containing sensor and patient information, timing metadata and consecutive ECG strips.</p>
  </div>
  <div class="pdf-frame">
    <img src="{{ '/docs/ecg-pdf-preview.png' | relative_url }}" alt="HFTrack ECG PDF preview">
  </div>
  <div class="chips">
    <span>Sensor identifier</span><span>Age & sex</span><span>256 Hz sampling</span><span>Start & end time</span><span>Duration</span><span>Multi-row ECG strips</span>
  </div>
</section>

<section>
  <div class="section-heading">
    <span class="eyebrow">Health dashboard</span>
    <h2>Physical and simulated measurements</h2>
    <p>Only heart rate and ECG are acquired from the physical Movesense sensor. Weight, blood pressure and SpO₂ are simulated in the current prototype to demonstrate the interface, charts, data-entry flows and alert logic.</p>
  </div>
  <div class="data-grid">
    <div><strong>♥ Heart rate</strong><span>Movesense MD</span></div>
    <div><strong>⌁ ECG</strong><span>Movesense MD</span></div>
    <div><strong>⚖ Weight</strong><span>Simulated</span></div>
    <div><strong>◫ Blood pressure</strong><span>Simulated</span></div>
    <div><strong>○ SpO₂</strong><span>Simulated</span></div>
  </div>
</section>

<section>
  <div class="section-heading">
    <span class="eyebrow">System design</span>
    <h2>Overall System Architecture</h2>
    <p>The mobile prototype is designed as one component of a broader conceptual architecture for remote monitoring of patients with heart failure.</p>
  </div>
  <div class="architecture">
    <img src="{{ '/docs/architettura_sistema.png' | relative_url }}" alt="Overall architecture for remote heart failure monitoring">
  </div>
  <div class="architecture-flow">
    <span>Movesense MD</span><b>→</b><span>Mobile Gateway</span><b>→</b><span>Cloud Infrastructure</span><b>→</b><span>Clinical Layer</span>
  </div>
  <p class="scope"><strong>Implemented scope:</strong> this repository presents the patient-side mobile frontend prototype. Cloud backend services, MQTT telemetry, remote REST APIs, clinical database persistence, predictive AI services and the healthcare-professional dashboard belong to the proposed architecture but are not implemented in the prototype.</p>
</section>

<section>
  <div class="section-heading">
    <span class="eyebrow">Implementation</span>
    <h2>Technology stack</h2>
  </div>
  <div class="tech-grid">
    <span>Flutter</span><span>Dart</span><span>Provider</span><span>Movesense MD</span><span>Bluetooth Low Energy</span><span>MDS / Whiteboard</span><span>mdsflutter</span><span>flutter_blue_plus</span><span>fl_chart</span><span>pdf / printing</span>
  </div>
</section>

<section class="academic">
  <span class="eyebrow">Academic context</span>
  <h2>Bachelor's Degree Thesis in Computer Engineering</h2>
  <p>HFTrack was developed by <strong>Francesco Ferraro</strong> at the University of Salento during the 2025/2026 academic year.</p>
  <blockquote>Remote Monitoring Systems for Heart Failure: State of the Art and Development of an Application Prototype</blockquote>
  <p>The work studies remote patient monitoring for heart failure and implements the patient-side mobile frontend of the proposed architecture, focusing on usability, local health-data visualization, BLE acquisition, and Movesense integration.</p>
  <a class="button primary" href="https://github.com/UniSalento-IDALab-Bachelor-Thesis/tesi-hftrack-FrancescoFerraro">View complete project & technical documentation</a>
</section>
