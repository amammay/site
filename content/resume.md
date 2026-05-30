---
title: "Resume"
layout: "single"
url: "/resume/"
summary: "Alex Mammay's Professional Resume - Software Engineer"
showToc: false
ShowBreadCrumbs: false
---

<div class="resume-container">
  
  <!-- Print Action Button -->
  <div class="resume-actions">
    <button class="print-btn" onclick="window.print()">
      <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><polyline points="6 9 6 2 18 2 18 9"></polyline><path d="M6 18H4a2 2 0 0 1-2-2v-5a2 2 0 0 1 2-2h16a2 2 0 0 1 2 2v5a2 2 0 0 1-2 2h-2"></path><rect x="6" y="14" width="12" height="8"></rect></svg>
      Print / Save PDF
    </button>
  </div>

  <!-- Header -->
  <header class="resume-header">
    <h1 class="resume-name">Alex Mammay</h1>
    <p class="resume-title">Software Engineer</p>
    <div class="resume-contact">
      <span>📍 Pittsburgh, PA</span>
      <span>📧 <a href="mailto:alexmammay@gmail.com">alexmammay@gmail.com</a></span>
      <span>🌐 <a href="https://mammay.dev">mammay.dev</a></span>
      <span>🐙 <a href="https://github.com/amammay" target="_blank" rel="noopener">github.com/amammay</a></span>
      <span>💼 <a href="https://www.linkedin.com/in/alex-mammay-7a969ba6/" target="_blank" rel="noopener">linkedin.com/in/alex-mammay</a></span>
    </div>
  </header>

  <!-- Summary -->
  <section class="resume-section">
    <h2 class="resume-section-title">Professional Summary</h2>
    <p>
      Platform-oriented Software Engineer with 7+ years of experience designing shared libraries, developer tooling, and distributed infrastructure in Go. Currently owning an internal Go SDK adopted across 40+ microservices, with shipped contributions spanning distributed locking, idempotency, Kafka schema validation, webhook delivery, observability bootstrapping, and auditing systems. Background in cloud-native product development on GCP and AWS with Kubernetes, and a track record of turning complex backend problems into reusable, well-documented platform primitives.
    </p>
  </section>

  <!-- Skills -->
  <section class="resume-section">
    <h2 class="resume-section-title">Technical Skills</h2>
    <div class="skills-grid">
      <div class="skills-category">
        <div class="skills-category-title">Languages</div>
        <div class="skills-list">Go (Golang), Node.js, Python, SQL, JavaScript (TypeScript), HTML/CSS</div>
      </div>
      <div class="skills-category">
        <div class="skills-category-title">APIs & Messaging</div>
        <div class="skills-list">gRPC, Protocol Buffers, REST APIs, Webhooks (HMAC SHA-256), Kafka, GCP Pub/Sub, WebSockets, JSON Schema, Avro, CloudEvents</div>
      </div>
      <div class="skills-category">
        <div class="skills-category-title">Cloud & Infrastructure</div>
        <div class="skills-list">AWS, Google Cloud Platform (GCP), Docker, Kubernetes, Terraform, GitHub Actions, Cloud Tasks, OpenTelemetry</div>
      </div>
      <div class="skills-category">
        <div class="skills-category-title">Frameworks & Databases</div>
        <div class="skills-list">Angular, Firestore, MongoDB, PostgreSQL, Redis, MySQL</div>
      </div>
    </div>
  </section>

<!-- Experience -->
<section class="resume-section">
  <h2 class="resume-section-title">Professional Experience</h2>

  <!-- Job 1 -->
  <div class="resume-item">
    <div class="resume-item-header">
      <div>
        <span class="resume-item-title">Software Engineer</span>
        <span class="resume-item-org"> | Bread Financial, Remote</span>
      </div>
      <span class="resume-item-date">Oct 2021 -- Present</span>
    </div>
    <ul class="resume-item-bullets">
      <li>Engineered core features for a business workflow engine utilized across multiple product teams to configure and process complex transaction logic, including credit card debt consolidation and in-store virtual card eligibility.</li>
      <li>Maintain ownership of <strong>gokit</strong>, the internal core Go library utilized across 40+ microservices; designed a Go-based <strong>Redlock</strong> distributed locker and a standardized <strong>idempotency module</strong> (HTTP, gRPC, Kafka) coordinating payload hashing with distributed lock synchronization.</li>
      <li>Standardized message schemas on <strong>Kafka</strong> topics by implementing validation hooks for JSON Schema, Protobuf, and Avro, performing just‑in‑time schema reference traversal for each type using <strong>protoreflect</strong> on the consumer side.</li>
      <li>Created high-level bootstrapping client abstractions around the <strong>CloudEvents</strong> specification for Sarama and Confluent Kafka (supporting cgo/no-cgo configurations) to simplify consumer group joining and performance tuning.</li>
      <li>Designed a standardized company-wide bootstrapping wrapper for <strong>OpenTelemetry</strong> in Go applications, incorporating an OpenTracing compatibility shim to automatically upgrade legacy service instrumentation via the OpenTracing-to-OTel bridge.</li>
      <li>Architected and shipped a <strong>Webhook Platform</strong> with decoupled control and data planes, supporting real-time external event delivery signed with detached JSON Web Signatures (JWS HMAC-SHA256) and verified using cached, rotating JSON Web Key Sets (JWKS).</li>
      <li>Led the implementation of a PROV‑DM‑compliant auditing platform: MongoDB backend with aggregation pipelines and $graphLookup, and enhanced the Go <code>database/sql</code> driver to embed Postgres transaction IDs (<code>xmin</code>) for CDC correlation.</li>
    </ul>
  </div>

  <!-- Job 2 -->
  <div class="resume-item">
    <div class="resume-item-header">
      <div>
        <span class="resume-item-title">Software Engineer</span>
        <span class="resume-item-org"> | Highmark Health, Pittsburgh PA</span>
      </div>
      <span class="resume-item-date">Jan 2018 -- Oct 2021</span>
    </div>
    <ul class="resume-item-bullets">
      <li>Designed and built a parallelized E2E test execution pipeline in <strong>Node.js</strong> and Cypress, leveraging <strong>GCP Cloud Run</strong> and <strong>Firestore</strong> to cut test cycles from 4 hours to 20 minutes.</li>
      <li>Architected and developed real-time chat applications for members and customer service advocates using <strong>Angular</strong>, <strong>Go</strong>, <strong>GCP Pub/Sub</strong>, <strong>Firestore</strong>, and <strong>Cloud Tasks</strong>.</li>
      <li>Served as lead developer for a member-facing AI chatbot powered by <strong>Dialogflow</strong>, managing dynamic flows for checking coverage, finding doctors, and retrieving plan benefits.</li>
    </ul>
  </div>

  <!-- Job 3 -->
  <div class="resume-item">
    <div class="resume-item-header">
      <div>
        <span class="resume-item-title">Software Engineer Intern</span>
        <span class="resume-item-org"> | Highmark Health, Pittsburgh PA</span>
      </div>
      <span class="resume-item-date">May 2017 -- Dec 2017</span>
    </div>
  </div>
</section>


<!-- Education -->
<section class="resume-section">
  <h2 class="resume-section-title">Education</h2>
  
  <div class="resume-item">
    <div class="resume-item-header">
      <div>
        <span class="resume-item-title">Bachelor of Science in Information Sciences and Technology</span>
        <span class="resume-item-org"> | The Pennsylvania State University</span>
      </div>
      <span class="resume-item-date">Graduated Dec 2017</span>
    </div>
    <ul class="resume-item-bullets">
      <li>Cumulative GPA: 3.59/4.0</li>
    </ul>
  </div>
</section>

</div>
