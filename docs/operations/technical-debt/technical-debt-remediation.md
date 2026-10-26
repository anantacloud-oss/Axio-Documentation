---
title: Technical Debt — Remediation & Workflows
layout: default
parent: Technical Debt
nav_order: 4
permalink: /axio/operations/technical-debt/technical-debt-remediation/
---

<link rel="stylesheet" href="{{ '/assets/css/technical-debt-remediation.css' | relative_url }}">


<div class="td-rem-page">
  
  <header class="td-rem-header">
    <h1>Technical Debt — Remediation &amp; Workflows</h1>
    <p class="td-rem-subtitle">Plan, approve, execute and verify remediation at scale</p>
    <p>It provides automated and manual remediation workflows for technical debt items with approval gates, change management, and verification. It helps you reduce risk, lower costs and improve compliance by addressing issues across cloud and code.</p>
  </header>

  <section class="td-rem-metrics" aria-label="Remediation metrics">
    <article class="td-rem-metric td-rem-red">
      <span class="td-rem-metric-icon">⚠</span>
      <div><p>Eligible for Remediation</p><strong>68</strong><span class="td-rem-change td-rem-bad">↑ 12%</span><small>vs previous period</small></div>
    </article>
    <article class="td-rem-metric td-rem-blue">
      <span class="td-rem-metric-icon">▶</span>
      <div><p>In Progress</p><strong>24</strong><span class="td-rem-change td-rem-bad">↑ 9%</span><small>vs previous period</small></div>
    </article>
    <article class="td-rem-metric td-rem-purple">
      <span class="td-rem-metric-icon">✓</span>
      <div><p>Remediated (last 30 days)</p><strong>54</strong><span class="td-rem-change td-rem-good">↑ 28%</span><small>vs previous period</small></div>
    </article>
    <article class="td-rem-metric td-rem-amber">
      <span class="td-rem-metric-icon">◷</span>
      <div><p>Awaiting Approval</p><strong>16</strong><span class="td-rem-change td-rem-bad">↓ 6%</span><small>vs previous period</small></div>
    </article>
  </section>

  <section class="td-rem-section">
    <h2>Remediation workflow</h2>
    <p>End-to-end workflow from identification to verification.</p>
    <div class="td-rem-workflow">
      <article class="td-rem-step td-rem-step-blue"><span class="td-rem-step-icon">⌕</span><div><strong>1. Identify</strong><p>Select eligible technical debt items</p></div></article>
      <span class="td-rem-arrow">→</span>
      <article class="td-rem-step td-rem-step-purple"><span class="td-rem-step-icon">▤</span><div><strong>2. Plan</strong><p>Generate remediation plan and impact analysis</p></div></article>
      <span class="td-rem-arrow">→</span>
      <article class="td-rem-step td-rem-step-amber"><span class="td-rem-step-icon">♟</span><div><strong>3. Approve</strong><p>Review and approve changes (manual gate)</p></div></article>
      <span class="td-rem-arrow">→</span>
      <article class="td-rem-step td-rem-step-blue"><span class="td-rem-step-icon">⚙</span><div><strong>4. Execute</strong><p>Run automated or manual remediation</p></div></article>
      <span class="td-rem-arrow">→</span>
      <article class="td-rem-step td-rem-step-green"><span class="td-rem-step-icon">✓</span><div><strong>5. Verify</strong><p>Confirm resolution with source evidence</p></div></article>
    </div>
  </section>

  <div class="td-rem-content-grid">
    <div>
      <section class="td-rem-section">
        <h2>Remediation options</h2>
        <p>Choose the right remediation method based on the issue type and policy.</p>
        <div class="td-rem-table-wrap">
          <table class="td-rem-table">
            <thead><tr><th>Method</th><th>Description</th><th>Supported for</th></tr></thead>
            <tbody>
              <tr><td>Automated</td><td>Run pre-defined remediation playbooks</td><td>AWS, GitHub, Policy, Drift</td></tr>
              <tr><td>Manual</td><td>Provide step-by-step instructions</td><td>All sources</td></tr>
              <tr><td>AI-assisted</td><td>Generate fix suggestions using AI</td><td>Code, Configuration</td></tr>
              <tr><td>Custom script</td><td>Execute custom commands or Terraform</td><td>Cloud, Infrastructure</td></tr>
              <tr><td>Bulk remediation</td><td>Remediate multiple items in a campaign</td><td>All sources</td></tr>
            </tbody>
          </table>
        </div>
      </section>

    </div>

    <div>
      <section class="td-rem-section">
        <h2>Example remediation plan</h2>
        <p>A generated plan includes the issue details, impact analysis and execution steps.</p>
        <article class="td-rem-plan">
          <div class="td-rem-plan-heading"><h3>Security Hub finding: S3 bucket public access</h3><span>Critical</span></div>
          <dl>
            <dt>Resource</dt><dd><code>arn:aws:s3:::example-bucket</code></dd>
            <dt>Issue</dt><dd>S3 bucket allows public access</dd>
            <dt>Impact</dt><dd>Data exposure risk</dd>
            <dt>Remediation</dt><dd>Block public access and update bucket policy</dd>
          </dl>
          <div class="td-rem-execution">
            <strong>Execution steps</strong>
            <ol>
              <li><span>1</span>Enable block public access on the bucket</li>
              <li><span>2</span>Update bucket policy to restrict access</li>
              <li><span>3</span>Verify using AWS Security Hub</li>
            </ol>
          </div>
        </article>
      </section>

      <section class="td-rem-section td-rem-types-section">
        <h2>Supported remediation types</h2>
        <div class="td-rem-types">
          <article><span>☁</span><strong>AWS</strong><p>Configuration fixes</p></article>
          <article><span>‹/›</span><strong>GitHub</strong><p>Dependency updates</p></article>
          <article><span>⬟</span><strong>Policy</strong><p>Compliance enforcement</p></article>
          <article><span>⚒</span><strong>Infrastructure</strong><p>Drift remediation</p></article>
          <article><span>▤</span><strong>Cost</strong><p>Optimization recommendations</p></article>
        </div>
      </section>
    </div>
  </div>
</div>
