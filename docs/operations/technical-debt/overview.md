---
layout: default
title: Overview
nav_order: 1
parent: Technical Debt
permalink: /axio/operations/technical-debt/overview/
---

<link rel="stylesheet" href="{{ '/assets/css/technical-debt-overview.css' | relative_url }}">

<div class="td-page">
  
  <header class="td-page-header">
    <h1>Technical Debt</h1>
    <p class="td-subtitle">Foundation, operating model &amp; backlog</p>
    <p class="td-intro">
      Technical Debt helps you identify, prioritize and remediate infrastructure
      and code issues across your environment. It consolidates findings from
      multiple sources such as cloud, security, policy, drift, cost and compliance
      into a single backlog with clear ownership and lifecycle.
    </p>
  </header>

  <section class="td-metrics" aria-label="Technical debt summary">
    <article class="td-metric td-blue">
      <div class="td-metric-icon">▤</div>
      <div>
        <p>Total Debt Items</p>
        <strong>248</strong>
        <span class="td-change td-good">↓ 12%</span>
        <small>vs previous period</small>
      </div>
    </article>

    <article class="td-metric td-red">
      <div class="td-metric-icon">⚠</div>
      <div>
        <p>Critical &amp; High</p>
        <strong>76</strong>
        <span class="td-change td-bad">↑ 8%</span>
        <small>vs previous period</small>
      </div>
    </article>

    <article class="td-metric td-purple">
      <div class="td-metric-icon">◷</div>
      <div>
        <p>Overdue (SLA)</p>
        <strong>32</strong>
        <span class="td-change td-bad">↑ 6%</span>
        <small>vs previous period</small>
      </div>
    </article>

    <article class="td-metric td-green">
      <div class="td-metric-icon">✓</div>
      <div>
        <p>Resolved (last 30 days)</p>
        <strong>54</strong>
        <span class="td-change td-good">↑ 24%</span>
        <small>vs previous period</small>
      </div>
    </article>
  </section>

  <div class="td-main-grid">
    <div class="td-column">
      <section class="td-section">
        <h2>What is Technical Debt?</h2>
        <p>
          Technical Debt refers to known issues, risks or improvement
          opportunities in your infrastructure and code that can lead to higher
          cost, security risks, operational issues or reduced reliability over
          time. Axio automatically collects, normalizes and tracks these items
          from multiple sources and provides tools to prioritize, remediate and
          govern them.
        </p>
      </section>

      <section class="td-panel td-capabilities">
        <h2>Key capabilities</h2>

        <div class="td-capability">
          <span class="td-small-icon">☷</span>
          <div>
            <strong>Multi-source ingestion</strong>
            <p>Security, policy, drift, cost, compliance and cloud lifecycle</p>
          </div>
        </div>

        <div class="td-capability">
          <span class="td-small-icon">▣</span>
          <div>
            <strong>Unified backlog</strong>
            <p>Consolidated view with filtering, ownership and SLA</p>
          </div>
        </div>

        <div class="td-capability">
          <span class="td-small-icon">♟</span>
          <div>
            <strong>Prioritization</strong>
            <p>Explainable scoring with financial and technical impact</p>
          </div>
        </div>

        <div class="td-capability">
          <span class="td-small-icon">⚒</span>
          <div>
            <strong>Remediation workflows</strong>
            <p>Automated and manual remediation with verification</p>
          </div>
        </div>

        <div class="td-capability">
          <span class="td-small-icon">⬟</span>
          <div>
            <strong>Governance</strong>
            <p>SLA, ownership, escalation and exceptions</p>
          </div>
        </div>

        <div class="td-capability">
          <span class="td-small-icon">▥</span>
          <div>
            <strong>Trends &amp; executive insights</strong>
            <p>Historical analytics and reports for different audiences</p>
          </div>
        </div>
      </section>
    </div>

    <div class="td-column">
      <section class="td-panel td-architecture" aria-label="Technical debt data flow">
        <div class="td-source-grid">
          <div class="td-source">
            <span>☁</span>
            <strong>Cloud</strong>
            <small>AWS, Azure,<br>GCP</small>
          </div>

          <div class="td-source">
            <span>⬟</span>
            <strong>Security</strong>
            <small>Findings</small>
          </div>

          <div class="td-source">
            <span>▤</span>
            <strong>Policy</strong>
            <small>Violations</small>
          </div>

          <div class="td-source">
            <span>ϟ</span>
            <strong>Drift</strong>
            <small>Configuration<br>drift</small>
          </div>

          <div class="td-source">
            <span>▤</span>
            <strong>Cost</strong>
            <small>Billing</small>
          </div>

          <div class="td-source">
            <span>✓</span>
            <strong>Compliance</strong>
            <small>Control failures</small>
          </div>
        </div>


        <div class="td-axio-node">
          <div>
            <strong>Axio</strong>
            <small>Technical Debt</small>
          </div>
        </div>


        <div class="td-output-grid">
          <div>
            <span>☷</span>
            <strong>Backlog</strong>
            <small>Unified inventory</small>
          </div>

          <div>
            <span>▥</span>
            <strong>Prioritization</strong>
            <small>Risk &amp; impact</small>
          </div>

          <div>
            <span>⚙</span>
            <strong>Remediation</strong>
            <small>Automated workflows</small>
          </div>

          <div>
            <span>⬟</span>
            <strong>Governance</strong>
            <small>SLA &amp; ownership</small>
          </div>
        </div>
      </section>

      <section class="td-section td-how">
        <h2>How it works</h2>

        <div class="td-steps">
          <div>
            <span>1</span>
            <strong>Ingest findings</strong>
            <small>Collect data from integrated sources.</small>
          </div>

          <div>
            <span>2</span>
            <strong>Reconcile &amp; normalize</strong>
            <small>Create canonical debt items with metadata.</small>
          </div>

          <div>
            <span>3</span>
            <strong>Prioritize</strong>
            <small>Calculate priority score and SLA.</small>
          </div>

          <div>
            <span>4</span>
            <strong>Remediate</strong>
            <small>Execute automated or manual actions.</small>
          </div>

          <div>
            <span>5</span>
            <strong>Verify &amp; close</strong>
            <small>Confirm resolution with source evidence.</small>
          </div>
        </div>
      </section>

      <section class="td-section td-source-types">
        <h2>Supported source types</h2>

        <div class="td-table-wrap">
          <table>
            <thead>
              <tr>
                <th>Source type</th>
                <th>Description</th>
              </tr>
            </thead>
            <tbody>
              <tr>
                <td><code>SECURITY_FINDING</code></td>
                <td>Findings from security scanners (e.g. Security Hub, code scanning)</td>
              </tr>
              <tr>
                <td><code>POLICY_VIOLATION</code></td>
                <td>Violations from policy as code and compliance checks</td>
              </tr>
              <tr>
                <td><code>DRIFT_CHECK</code></td>
                <td>Infrastructure drift findings</td>
              </tr>
              <tr>
                <td><code>CLOUD_BILLING_RECOMMENDATION</code></td>
                <td>Cost and rightsizing recommendations</td>
              </tr>
              <tr>
                <td><code>COMPLIANCE_CONTROL</code></td>
                <td>Failed compliance controls</td>
              </tr>
              <tr>
                <td><code>COST_ANOMALY</code></td>
                <td>Detected cost anomalies</td>
              </tr>
            </tbody>
          </table>
        </div>
      </section>
    </div>
  </div>
</div>


<nav class="page-navigation cost-page-navigation" aria-label="Documentation navigation">

    <a class="nav-button previous"
       href="{{ '/axio/operations/cost/' | relative_url }}">
       ← Cost Explorer
    </a>

    <a class="nav-button next"
       href="{{ '/axio/operations/technical-debt/technical-debt-aws-phase/' | relative_url }}">
       AWS account assessment →
    </a>

  </nav>
