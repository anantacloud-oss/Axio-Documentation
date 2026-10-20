---
title: Technical Debt — Governance & SLA
layout: default
parent: Technical Debt
nav_order: 5
permalink: /axio/operations/technical-debt/technical-debt-governance/
---

<link rel="stylesheet" href="{{ '/assets/css/technical-debt-governance.css' | relative_url }}">


<div class="td-gov-page">
 
  <header class="td-gov-header">
    <h1>Technical Debt — Governance &amp; SLA</h1>
    <p class="td-gov-subtitle">Ownership, due dates, policies and escalation for technical debt</p>
    <p>Phase 5 introduces governance and SLA management for technical debt. It helps you define ownership, set due dates, apply policies, track exceptions and ensure timely remediation with clear escalation rules.</p>
  </header>

  <section class="td-gov-metrics" aria-label="Governance metrics">
    <article class="td-gov-metric td-gov-blue">
      <span class="td-gov-metric-icon">♟</span>
      <div><p>Items with Owner</p><strong>208</strong><span class="td-gov-change td-gov-good">↑ 18%</span><small>vs previous period</small></div>
    </article>
    <article class="td-gov-metric td-gov-red">
      <span class="td-gov-metric-icon">◷</span>
      <div><p>Overdue Items</p><strong>32</strong><span class="td-gov-change td-gov-bad">↑ 6%</span><small>vs previous period</small></div>
    </article>
    <article class="td-gov-metric td-gov-purple">
      <span class="td-gov-metric-icon">▤</span>
      <div><p>SLA Violations</p><strong>12</strong><span class="td-gov-change td-gov-bad">↑ 20%</span><small>vs previous period</small></div>
    </article>
    <article class="td-gov-metric td-gov-green">
      <span class="td-gov-metric-icon">✓</span>
      <div><p>Within SLA</p><strong>204</strong><span class="td-gov-change td-gov-good">↑ 15%</span><small>vs previous period</small></div>
    </article>
  </section>

  <div class="td-gov-main-grid">
    <div>
      <section class="td-gov-section">
        <h2>Ownership model</h2>
        <p>Assign owners to technical debt items to ensure accountability and faster resolution.</p>
        <div class="td-gov-table-wrap">
          <table class="td-gov-table">
            <thead><tr><th>Item type</th><th>Default owner</th><th>Owner source</th><th>Example</th></tr></thead>
            <tbody>
              <tr><td>Cloud resource</td><td>Platform Team</td><td>Tag (owner), LDAP group</td><td>EC2 instance (owner: platform)</td></tr>
              <tr><td>Security finding</td><td>Security Team</td><td>Security Hub, Code scanning</td><td>S3 public access (owner: security)</td></tr>
              <tr><td>Policy violation</td><td>Compliance Team</td><td>Policy mapping</td><td>Encryption disabled (owner: compliance)</td></tr>
              <tr><td>Drift item</td><td>Infra Team</td><td>Resource tag, service catalog</td><td>Unapproved change (owner: infra)</td></tr>
              <tr><td>Code dependency</td><td>Application Team</td><td>GitHub CODEOWNERS</td><td>Outdated library (owner: app team)</td></tr>
            </tbody>
          </table>
        </div>
      </section>

      <section class="td-gov-section td-gov-sla-section">
        <h2>SLA policies</h2>
        <p>Define remediation timelines based on severity, item type and business impact.</p>
        <div class="td-gov-table-wrap">
          <table class="td-gov-table">
            <thead><tr><th>Severity</th><th>Default SLA (days)</th><th>Example item types</th></tr></thead>
            <tbody>
              <tr><td><span class="td-gov-severity td-gov-critical"></span>Critical</td><td>7</td><td>Public S3 bucket, Critical CVE, Policy violation (encryption)</td></tr>
              <tr><td><span class="td-gov-severity td-gov-high"></span>High</td><td>30</td><td>Outdated runtime, High risk security finding</td></tr>
              <tr><td><span class="td-gov-severity td-gov-medium"></span>Medium</td><td>60</td><td>Deprecated instance type, Drift detection</td></tr>
              <tr><td><span class="td-gov-severity td-gov-low"></span>Low</td><td>90</td><td>Recommendations, Informational findings</td></tr>
            </tbody>
          </table>
        </div>
      </section>

      <section class="td-gov-section td-gov-policy-section">
        <h2>Policy configuration (example)</h2>
        <p>Define custom policies for ownership, SLA and escalation.</p>
        <div class="td-gov-code">
          <div class="td-gov-code-toolbar"><span>yaml</span><b>▢</b></div>
          <pre><code><span class="td-yaml-key">policy</span>:
  <span class="td-yaml-key">itemType</span>: SECURITY_FINDING
  <span class="td-yaml-key">severity</span>: CRITICAL
  <span class="td-yaml-key">slaDays</span>: 7
  <span class="td-yaml-key">owner</span>: security-team
  <span class="td-yaml-key">escalation</span>:
    - afterDays: 7
      notify: ["team-lead", "security-head"]</code></pre>
        </div>
      </section>
    </div>

    <div>
      <section class="td-gov-section td-gov-workflow-section">
        <h2>Governance workflow</h2>
        <p>Automated governance with clear escalation paths.</p>
        <div class="td-gov-workflow">
          <article class="td-gov-workflow-card td-gov-workflow-blue"><span>▤</span><p>Identify<br>technical debt item</p></article>
          <span class="td-gov-flow-arrow">→</span>
          <article class="td-gov-workflow-card td-gov-workflow-purple"><span>♟</span><p>Assign owner<br>and due date</p></article>
          <span class="td-gov-flow-arrow">→</span>
          <article class="td-gov-workflow-card td-gov-workflow-amber"><span>⬟</span><p>Apply policies<br>and SLA</p></article>
          <div class="td-gov-flow-down">↓</div>
          <div class="td-gov-decision">Within SLA?</div>
          <div class="td-gov-branch td-gov-yes">Yes</div>
          <div class="td-gov-branch td-gov-no">No</div>
          <article class="td-gov-outcome td-gov-outcome-yes"><span>✓</span><p>Track progress<br>and close</p></article>
          <article class="td-gov-outcome td-gov-outcome-no"><span>♟</span><p>Trigger escalation<br>and notify owner</p></article>
        </div>
      </section>

      <section class="td-gov-section td-gov-escalation-section">
        <h2>Escalation rules</h2>
        <p>Automatically escalate overdue items to the right teams.</p>
        <div class="td-gov-table-wrap">
          <table class="td-gov-table">
            <thead><tr><th>Condition</th><th>Escalate to</th><th>Action</th></tr></thead>
            <tbody>
              <tr><td>Overdue &gt; 7 days</td><td>Owner + Team Lead</td><td>Create notification</td></tr>
              <tr><td>Overdue &gt; 30 days</td><td>Department Head</td><td>Create issue + email</td></tr>
              <tr><td>Overdue &gt; 90 days</td><td>Cloud Center of Excellence</td><td>Create incident</td></tr>
              <tr><td>SLA breach (critical)</td><td>Security/Compliance</td><td>Immediate alert (Slack/Email)</td></tr>
            </tbody>
          </table>
        </div>
      </section>

      <section class="td-gov-benefits">
        <h2><span>✓</span> Benefits</h2>
        <ul>
          <li>Clear ownership and accountability</li>
          <li>Configurable SLA policies based on risk and business impact</li>
          <li>Automated escalation and notifications</li>
          <li>Better compliance and audit readiness</li>
          <li>Faster remediation and reduced risk</li>
        </ul>
      </section>
    </div>
  </div>
</div>
