---
layout: default
nav_order: 3
parent: Operations
title: Cost Explorer
permalink: /axio/operations/cost/
---

<link rel="stylesheet" href="{{ '/assets/css/cost-explorer.css' | relative_url }}">

<div class="cost-page">

  <header class="cost-hero">
    <div class="cost-hero-top">
      <div class="cost-hero-icon" aria-hidden="true">◈</div>
      <span class="cost-eyebrow">OPERATIONS / FINOPS</span>
    </div>

    <h1>Cost Explorer</h1>

    <p class="cost-hero-description">
      Understand cloud spending, estimate infrastructure costs, identify
      savings opportunities, and reconcile actual billing with attributed
      resource usage — all from one place.
    </p>

    <div class="cost-hero-tags">
      <span>Cloud billing</span>
      <span>IaC cost estimates</span>
      <span>FinOps optimization</span>
      <span>Finance reconciliation</span>
    </div>
  </header>

  <section class="cost-intro-section">
    <div class="cost-section-kicker">GETTING STARTED</div>

    <p class="cost-intro">
      Open <strong>Operations → Cost Explorer</strong> for
      <strong>authoritative cloud billing</strong>,
      <strong>IaC planning estimates</strong>, showback, optimization,
      and <strong>finance reconciliation</strong>.
      Select a <strong>Terraform stack</strong>, choose a
      <strong>pricing engine</strong>, run <strong>Scan now</strong>,
      and review rollups across your organization hierarchy — before
      or after deployment.
    </p>

    <div class="cost-access-grid">
      <article class="cost-access-card">
        <div class="cost-access-icon cost-access-icon-blue" aria-hidden="true">◉</div>
        <div>
          <h3>Read access</h3>
          <code>cost:read</code>
          <p>View cost estimates, billing summaries, showback, anomalies, and invoices.</p>
        </div>
      </article>

      <article class="cost-access-card">
        <div class="cost-access-icon cost-access-icon-purple" aria-hidden="true">⚙</div>
        <div>
          <h3>Management access</h3>
          <code>cost:manage</code>
          <p>Run scans, save schedules, sync billing, reconcile costs, and manage alerts.</p>
        </div>
      </article>
    </div>

    <div class="cost-info-box">
      <div class="cost-info-icon" aria-hidden="true">ⓘ</div>
      <div>
        <h3>Why cost analysis?</h3>
        <p>
          Cost analysis shows estimated and actual spend so you can compare
          options, evaluate rightsizing and commitment purchases, reconcile
          cloud bills to attributed inventory, and catch budget or anomaly
          spikes before they surprise finance.
        </p>
      </div>
    </div>
  </section>

  <section class="cost-section" id="stack-cost-analysis">

    <div class="cost-section-heading">
      <span class="cost-section-number">01</span>
      <div>
        <h2>Stack-level cost analysis</h2>
        <p>Estimate infrastructure costs before or after deployment.</p>
      </div>
    </div>

    <p>
      In the <strong>Stack-level cost analysis</strong> section, select a
      <strong>Terraform stack</strong> and <strong>pricing engine</strong>,
      then run <strong>Scan now</strong>. Each scan prices all Terraform
      workspaces in that stack.
    </p>

    <div class="cost-action-panel">
      <div class="cost-action-panel-heading">
        <span class="cost-action-icon" aria-hidden="true">↻</span>
        <div>
          <h3>Configure recurring scans</h3>
          <p>Automate cost estimates on a schedule for each stack.</p>
        </div>
      </div>

      <p>
        Expand <strong>Schedule for &lt;stack&gt;</strong> to enable a
        recurring scan.
      </p>

      <div class="cost-schedule-grid">
        <div class="cost-schedule-item">
          <strong>Daily</strong>
          <span>Run every day at the configured local time.</span>
        </div>
        <div class="cost-schedule-item">
          <strong>Weekly</strong>
          <span>Choose a day of the week and local time.</span>
        </div>
        <div class="cost-schedule-item">
          <strong>Monthly</strong>
          <span>Choose a day from 1–28 and local time.</span>
        </div>
      </div>
    </div>

    <h3 class="cost-subheading">Choose your pricing engine</h3>

    <div class="cost-engine-grid">
      <article class="cost-engine-card cost-engine-built-in">
        <div class="cost-engine-card-top">
          <span class="cost-engine-icon" aria-hidden="true">◇</span>
          <span class="cost-engine-label">ALWAYS AVAILABLE</span>
        </div>
        <h3>Built-in pricing</h3>
        <p>Planning-layer cost estimates available without an Infracost integration.</p>
      </article>

      <article class="cost-engine-card cost-engine-infracost">
        <div class="cost-engine-card-top">
          <span class="cost-engine-icon" aria-hidden="true">↗</span>
          <span class="cost-engine-label">WHEN CONFIGURED</span>
        </div>
        <h3>Configured Infracost</h3>
        <p>
          Provider-accurate estimates when Infracost is configured under
          <strong>Administration → Integrations → Infracost</strong>.
        </p>
      </article>
    </div>

    <p>
      In-app planning totals and estimate counts appear in the stack scan
      summary. Use the <strong>display currency</strong> chip in the page
      header to view amounts in a supported display currency where configured.
    </p>

  </section>

  <section class="cost-section" id="overview-panels">

    <div class="cost-section-heading">
      <span class="cost-section-number">02</span>
      <div>
        <h2>Overview and monitoring</h2>
        <p>Important cost information stays visible above the result tabs.</p>
      </div>
    </div>

    <p>
      These panels are not separate tabs — they sit above the six result tabs.
    </p>

    <div class="cost-overview-grid">

      <article class="cost-overview-card">
        <span class="cost-overview-icon cost-overview-purple" aria-hidden="true">◈</span>
        <h3>Overview hero</h3>
        <p>Monthly spend, savings opportunity, authoritative versus planning scope, and reconciliation hints.</p>
      </article>

      <article class="cost-overview-card">
        <span class="cost-overview-icon cost-overview-orange" aria-hidden="true">⚑</span>
        <h3>Alert history</h3>
        <p>Review recent budget and billing alerts.</p>
      </article>

      <article class="cost-overview-card">
        <span class="cost-overview-icon cost-overview-blue" aria-hidden="true">☁</span>
        <h3>Cloud billing</h3>
        <p>
          Connect and sync AWS, Azure, and GCP billing sources.
          View charts and sync run history.
          <code>cost:manage</code> is required to sync.
        </p>
      </article>

      <article class="cost-overview-card">
        <span class="cost-overview-icon cost-overview-green" aria-hidden="true">⇄</span>
        <h3>Finance reconciliation</h3>
        <p>
          Compare cloud bills with attributed spend, investigate variance,
          and drill into details. Running reconciliation requires
          <code>cost:manage</code>.
        </p>
      </article>

      <article class="cost-overview-card cost-overview-card-wide">
        <span class="cost-overview-icon cost-overview-purple" aria-hidden="true">▤</span>
        <h3>Stack-level cost analysis</h3>
        <p>Run on-demand scans and configure recurring schedules for Terraform stacks.</p>
      </article>

    </div>

    <div class="cost-note">
      <strong>Budget and anomaly alerts</strong>
      <p>
        Open <strong>Budget and anomaly alerts</strong> from the overview
        hero to configure warning and critical budget thresholds, anomaly
        deltas, and email notifications.
      </p>
    </div>

  </section>

  <section class="cost-section" id="cost-workflow">

    <div class="cost-section-heading">
      <span class="cost-section-number">03</span>
      <div>
        <h2>How it works</h2>
        <p>From infrastructure discovery to financial insights.</p>
      </div>
    </div>

    <p>
      Axio discovers Terraform resources in the selected stack and, when
      billing is connected, ingests authoritative cloud usage. Results feed
      forecasts, showback, chargeback, opportunities, and anomaly detection.
    </p>

    <div class="cost-flow">

      <article class="cost-flow-card cost-flow-blue">
        <div class="cost-flow-icon" aria-hidden="true">▱</div>
        <span class="cost-flow-step">STEP 01</span>
        <strong>Select stack</strong>
        <p>Choose a Terraform stack and pricing engine.</p>
      </article>

      <div class="cost-flow-arrow" aria-hidden="true">→</div>

      <article class="cost-flow-card cost-flow-green">
        <div class="cost-flow-icon" aria-hidden="true">◉</div>
        <span class="cost-flow-step">STEP 02</span>
        <strong>Scan and price</strong>
        <p>Price each Terraform workspace and/or sync cloud billing.</p>
      </article>

      <div class="cost-flow-arrow" aria-hidden="true">→</div>

      <article class="cost-flow-card cost-flow-purple">
        <div class="cost-flow-icon" aria-hidden="true">▥</div>
        <span class="cost-flow-step">STEP 03</span>
        <strong>Roll up spend</strong>
        <p>Consolidate totals by organization, project, workspace, environment, and stack.</p>
      </article>

      <div class="cost-flow-arrow" aria-hidden="true">→</div>

      <article class="cost-flow-card cost-flow-orange">
        <div class="cost-flow-icon" aria-hidden="true">♧</div>
        <span class="cost-flow-step">STEP 04</span>
        <strong>Generate insights</strong>
        <p>Identify savings, commitments, anomalies, reconciliation differences, and chargeback.</p>
      </article>

    </div>

  </section>

  <section class="cost-section" id="cost-tabs">

    <div class="cost-section-heading">
      <span class="cost-section-number">04</span>
      <div>
        <h2>Page tabs</h2>
        <p>Explore detailed views of infrastructure spending and optimization.</p>
      </div>
    </div>

    <div class="cost-table-wrapper">
      <table class="cost-table">
        <thead>
          <tr>
            <th>Tab</th>
            <th>What it shows</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td><strong class="cost-table-label">Overview</strong></td>            
            <td>Allocation coverage, budget utilization, savings breakdown, spend by team, top recommendations, cost estimates, and finance trust metrics.</td>
          </tr>
          <tr>
            <td><strong class="cost-table-label">Costs</strong></td>
            <td>Monthly cost, annual forecast, potential savings, idle resources, cost by Terraform target, optimization recommendations, and cost estimates.</td>
          </tr>
          <tr>
            <td><strong class="cost-table-label">Showback</strong></td>
            <td>Consolidated spend grouped by dimension from cost estimates or inventory.</td>
          </tr>
          <tr>
            <td><strong class="cost-table-label">Opportunities</strong></td>
            <td>Commitment recommendations such as Savings Plans and Reserved Instances, rightsizing, advisor-style opportunities, and optional FinOps remediation tickets.</td>
          </tr>
          <tr>
            <td><strong class="cost-table-label">Chargeback</strong></td>
            <td>Generate monthly invoices by scope, list invoices, and download CSV exports.</td>
          </tr>
          <tr>
            <td><strong class="cost-table-label">Anomalies</strong></td>
            <td>Unexpected spend spikes from snapshot comparison, including severity, dimension, source, and status.</td>
          </tr>
        </tbody>
      </table>
    </div>

    <div class="cost-subsection">
      <h3>Cost estimates table</h3>
      <p>
        The <strong>Cost estimates</strong> table on <strong>Overview</strong>
        and <strong>Costs</strong> supports cascading filters for organization,
        project, workspace, environment, and stack. Click a resource count to
        open resource-level pricing details.
      </p>

      <div class="cost-table-wrapper">
        <table class="cost-table">
          <thead>
            <tr>
              <th>Column</th>
              <th>Description</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td>Organization / Project / Workspace / Environment / Stack</td>
              <td>Hierarchy attribution from the scanned stack.</td>
            </tr>
            <tr>
              <td>TF workspace</td>
              <td>Terraform workspace name within the stack.</td>
            </tr>
            <tr>
              <td>Monthly</td>
              <td>Estimated monthly cost for that row.</td>
            </tr>
            <tr>
              <td>Resources</td>
              <td>Number of priced resources; click to open the detail dialog.</td>
            </tr>
            <tr>
              <td>Savings</td>
              <td>Potential monthly savings for that estimate.</td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>

  </section>

  <section class="cost-section" id="cost-capabilities">

    <div class="cost-section-heading">
      <span class="cost-section-number">05</span>
      <div>
        <h2>Cost management capabilities</h2>
        <p>Scan infrastructure, optimize spend, and support financial reporting.</p>
      </div>
    </div>

    <div class="cost-two-column">

      <div class="cost-capabilities-panel">
        <h3>What you can do</h3>

        <ul class="cost-check-list">
          <li>Scan Terraform stacks on demand or on a Daily, Weekly, or Monthly schedule per stack.</li>
          <li>Switch between <strong>Built-in pricing</strong> and <strong>Configured Infracost</strong> when integrated.</li>
          <li>Sync cloud billing connectors and reconcile bills to attributed spend.</li>
          <li>Compare costs against a previous scan baseline, including estimate and per-target deltas.</li>
          <li>Review opportunities for rightsizing, idle waste, commitments, and cloud advisor findings.</li>
          <li>Run <strong>Check for anomalies</strong> on the Anomalies tab (<code>cost:manage</code>).</li>
          <li>Generate chargeback invoices (<code>cost:manage</code>) and download invoice CSV files (<code>cost:read</code>).</li>
          <li>Create FinOps remediation tickets from opportunities (<code>cost:manage</code>).</li>
        </ul>
      </div>

      <aside class="cost-report-box">
        <div class="cost-report-heading">
          <span class="cost-report-icon" aria-hidden="true">▤</span>
          <h3>Resource detail includes</h3>
        </div>

        <ul>
          <li>Per-resource monthly and annual cost.</li>
          <li>Discovery source: provisioned Terraform state, workspace config cache, or repository IaC (preview).</li>
          <li>Cost delta versus the previous scan.</li>
          <li>Idle resource count and optimization recommendations.</li>
          <li>Infracost badge when that engine was used.</li>
        </ul>
      </aside>

    </div>

  </section>

  <section class="cost-section" id="cost-permissions">

    <div class="cost-section-heading">
      <span class="cost-section-number">06</span>
      <div>
        <h2>Permissions</h2>
        <p>Access is controlled by organization-level cost permissions.</p>
      </div>
    </div>

    <div class="cost-table-wrapper">
      <table class="cost-table">
        <thead>
          <tr>
            <th>Permission</th>
            <th>Capability</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td><code>cost:read</code></td>
            <td>
              View Cost Explorer, including billing summaries, reconciliation
              results, estimates, showback, the anomalies list, and invoice
              lists and downloads.
            </td>
          </tr>
          <tr>
            <td><code>cost:manage</code></td>
            <td>
              Run stack scans, save scan schedules, sync cloud billing,
              run reconciliation, generate chargeback invoices, capture
              anomaly snapshots, acknowledge anomalies, configure alert
              settings, and create or update FinOps remediations.
            </td>
          </tr>
        </tbody>
      </table>
    </div>

  </section>

  <section class="cost-section" id="cost-anomalies">

    <div class="cost-section-heading">
      <span class="cost-section-number">07</span>
      <div>
        <h2>Anomalies</h2>
        <p>Identify unexpected changes in cloud spending.</p>
      </div>
    </div>

    <div class="cost-anomaly-panel">
      <div class="cost-anomaly-icon" aria-hidden="true">⌁</div>
      <div class="cost-anomaly-content">
        <h3>Detect and investigate spend spikes</h3>
        <p>
          On the <strong>Anomalies</strong> tab, click
          <strong>Check for anomalies</strong> to capture a baseline
          snapshot and compare current spend. This action requires
          <code>cost:manage</code>.
        </p>
        <p>
          Open anomalies show severity, dimension, source, previous
          versus current amounts, and percentage change. Use
          <strong>Acknowledge</strong> to close reviewed items
          (<code>cost:manage</code>).
        </p>
      </div>
    </div>

    <div class="cost-note">
      <div class="cost-note-heading">
        <span aria-hidden="true">✦</span>
        <strong>Recommended starting point</strong>
      </div>
      <p>
        Run at least one <strong>stack scan</strong> and/or connect
        <strong>cloud billing</strong> before relying on Showback,
        Opportunities, or Anomalies. These views combine scan attribution,
        inventory, and billing data when available.
      </p>
    </div>

  </section>

</div>

  <nav class="page-navigation cost-page-navigation" aria-label="Documentation navigation">

    <a class="nav-button previous"
       href="{{ '/axio/operations/drift/' | relative_url }}">
       ← Drift Detection
    </a>

    <a class="nav-button next"
       href="{{ '/axio/operations/technical-debt/overview/' | relative_url }}">
       Technical Debt →
    </a>

  </nav>

