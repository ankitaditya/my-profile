<template>
  <div class="exp-list">
    <div class="exp-item">
      <div class="exp-header">
        <span class="exp-role">Director of Artificial Intelligence</span>
        <span class="exp-company">@ Kalkinso Software (OPC) Pvt. Ltd.</span>
        <span class="exp-dates">Jan 2025–Present | New Delhi, India</span>
      </div>
      <ul>
        <li>Delivered LLMs, voice cloning, OCR, and inference pipelines as APIs.</li>
        <li>Implemented secure access and auth via Keycloak (keycloak.i-kalki.com) with role-based and org-based tenancy support.</li>
        <li>Designed a no-code automation builder (workflow.i-kalki.com) enabling clients to chain AI services visually and monitor flows in real-time.</li>
        <li>Shipped AI narration and audiobook production studio for BuckAudio (ai.buckaudio.com) with personalized voice clone deployment.</li>
        <li>Launched infrastructure on ECS/EKS with Terraform/CDK; implemented observability with CloudWatch, X-Ray, and Prometheus stack.</li>
        <li>Built live surveillance AI (STQC-ready) with video analytics and anomaly detection for CCTV ecosystems.</li>
      </ul>
    </div>
    <div class="exp-item">
      <div class="exp-header">
        <span class="exp-role">Software Engineer III / I / Trainee</span>
        <span class="exp-company">@ Zenarate</span>
        <span class="exp-dates">May 2021–Jun 2024 | Remote + Palo Alto, CA</span>
      </div>
      <ul>
        <li>Contributed to AI Coach platform, delivering sub-100ms latency simulators using WebSockets and real-time NLP inference.</li>
        <li>Architected microservices using AWS Lambda + Step Functions; reduced infra costs and improved reliability by 40%.</li>
        <li>Led bundling and build optimizations for React frontends, reducing TTI and improving Lighthouse scores.</li>
        <li>Implemented CI pipelines (Jenkins, GitHub Actions) with contract and integration testing; slashed release failures by 30%.</li>
        <li>Created Elasticsearch-based feedback search with advanced filters, used across 10+ enterprise clients.</li>
      </ul>
    </div>
    <div class="exp-item">
      <div class="exp-header">
        <span class="exp-role">IoT Software Intern</span>
        <span class="exp-company">@ Drone Power Pvt. Ltd.</span>
        <span class="exp-dates">Sep 2020–Dec 2020 | New Delhi, India</span>
      </div>
      <ul>
        <li>Built OCPP-based charger control APIs with real-time telemetry over MQTT and WebSockets.</li>
        <li>Deployed monitoring dashboards for EV infrastructure using Flask, React, and DynamoDB.</li>
        <li>Wrote automated firmware update toolchains with OTA support for IoT devices.</li>
      </ul>
    </div>
  </div>
</template>
<style scoped>
.exp-list {
  display: flex;
  flex-direction: column;
  gap: 2em;
}
.exp-item {
  background: #232323;
  border-radius: 16px;
  padding: 1.5em 1.5em 1em 1.5em;
  box-shadow: 0 1px 8px 0 #9e7fff22;
  transition: box-shadow 0.2s;
}
.exp-item:hover {
  box-shadow: 0 4px 24px 0 #38bdf855;
}
.exp-header {
  display: flex;
  flex-wrap: wrap;
  gap: 1em;
  align-items: baseline;
  margin-bottom: 0.5em;
}
.exp-role {
  font-weight: 700;
  color: #9e7fff;
  font-size: 1.1rem;
}
.exp-company {
  font-weight: 500;
  color: #38bdf8;
  font-size: 1.05rem;
}
.exp-dates {
  color: #a3a3a3;
  font-size: 0.95rem;
  margin-left: auto;
}
ul {
  margin: 0.5em 0 0 1.2em;
  padding: 0;
  color: #fff;
  font-size: 1rem;
}
li {
  margin-bottom: 0.3em;
}
</style>
