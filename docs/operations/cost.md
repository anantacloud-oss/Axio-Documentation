---
layout: default
nav_order: 3
parent: Operations
title: Cost Explorer
permalink: /axio/operations/cost/
---

<link rel="stylesheet" href="{{ '/assets/css/cost-explorer.css' | relative_url }}">

<div class="cost-page" markdown="1">

# Cost Explorer

<p class="cost-intro">
Open <strong>Operations → Cost Explorer</strong> for <strong>authoritative cloud billing</strong>, <strong>IaC planning estimates</strong>, showback, optimization, and <strong>finance reconciliation</strong>.
Select a <strong>Terraform stack</strong>, choose a <strong>pricing engine</strong>, run <strong>Scan now</strong>, and review rollups across your organization hierarchy — before or after deployment.
</p>

<p class="cost-intro">
Access requires <code>cost:read</code>. Running stack scans, saving schedules, syncing billing, generating chargeback invoices, acknowledging anomalies, and changing alert settings require <code>cost:manage</code>.
</p>

<div class="cost-info-box">
  <div class="cost-info-icon">ⓘ</div>
  <div>
    <h3>Why cost analysis?</h3>
    <p>
      Cost analysis shows estimated and actual spend so you can compare options, rightsizing, and commitment purchases,
      reconcile cloud bills to attributed inventory, and catch budget or anomaly spikes before they surprise finance.
    </p>
  </div>
</div>

## Stack-level cost analysis

<p>
In the <strong>Stack-level cost analysis</strong> section, pick a <strong>Terraform stack</strong> and <strong>pricing engine</strong>, then run <strong>Scan now</strong>.
Each scan prices all Terraform workspaces in that stack. Expand <strong>Schedule for &lt;stack&gt;</strong> to enable a <strong>recurring scan</strong> (Daily, Weekly, or Monthly with local time; Weekly includes day of week, Monthly includes day of month 1–28).
</p>

<ul>
  <li><strong>Built-in pricing</strong> — Planning-layer estimates (always available)</li>
  <li><strong>Configured Infracost</strong> — Provider-accurate estimates when Infracost is configured under <strong>Administration → Integrations → Infracost</strong> (<code>/admin/integrations/infracost</code>)</li>
</ul>

<p>
In-app planning totals and estimate counts appear in the stack scan summary. Use the <strong>display currency</strong> chip in the page header to view amounts in a supported display currency where configured.
</p>

## Above the tabs (always visible)

<p>These panels are not separate tabs — they sit above the six result tabs:</p>

<ul>
  <li><strong>Overview hero</strong> — Monthly spend, savings opportunity, authoritative vs planning scope, reconciliation hints</li>
  <li><strong>Alert history</strong> — Recent budget and billing alerts</li>
  <li><strong>Cloud billing</strong> — Connect and sync AWS, Azure, and GCP billing sources; charts and sync run history (<code>cost:manage</code> to sync)</li>
  <li><strong>Finance reconciliation</strong> — Compare cloud bill to attributed spend, variance, and drill-down (<code>cost:manage</code> to run reconciliation)</li>
  <li><strong>Stack-level cost analysis</strong> — Scan bar and schedules (described above)</li>
</ul>

<p>
Open <strong>Budget and anomaly alerts</strong> from the overview hero to configure thresholds (budget warn/critical, anomaly deltas, email). Deep links: <code>#finops-alert-settings</code>, <code>#finops-cloud-billing</code>.
</p>

## How it works

<p>
Axio discovers Terraform resources in the selected stack (and, when billing is connected, ingests authoritative cloud usage). Results feed forecasts, showback, chargeback, opportunities, and anomaly detection.
</p>

<div class="cost-flow">

  <div class="cost-flow-card cost-flow-blue">
    <div class="cost-flow-icon">▱</div>
    <strong>1. Select stack</strong>
    <p>Choose a Terraform stack and pricing engine</p>
  </div>

  <div class="cost-flow-arrow">→</div>

  <div class="cost-flow-card cost-flow-green">
    <div class="cost-flow-icon">◉</div>
    <strong>2. Scan &amp; price</strong>
    <p>Price each Terraform workspace in the stack (and/or sync cloud billing)</p>
  </div>

  <div class="cost-flow-arrow">→</div>

  <div class="cost-flow-card cost-flow-purple">
    <div class="cost-flow-icon">▥</div>
    <strong>3. Roll up spend</strong>
    <p>Totals consolidate by org, project, workspace, environment, and stack</p>
  </div>

  <div class="cost-flow-arrow">→</div>

  <div class="cost-flow-card cost-flow-orange">
    <div class="cost-flow-icon">♧</div>
    <strong>4. Insights</strong>
    <p>Opportunities, commitments, anomalies, reconciliation, and chargeback</p>
  </div>

</div>

## Page tabs

<p>Cost Explorer organizes detailed views into six tabs:</p>

<table class="cost-table">
<thead>
<tr>
  <th>Tab</th>
  <th>What it shows</th>
</tr>
</thead>
<tbody>
<tr>
  <td><strong>Overview</strong></td>
  <td>Allocation coverage, budget utilization, savings breakdown, spend by team, top recommendations, cost estimates table, finance trust metrics</td>
</tr>
<tr>
  <td><strong>Costs</strong></td>
  <td>Monthly cost, annual forecast, potential savings, idle resources; cost by Terraform target; optimization recommendations; full cost estimates table</td>
</tr>
<tr>
  <td><strong>Showback</strong></td>
  <td>Consolidated spend grouped by dimension (from cost estimates or inventory)</td>
</tr>
<tr>
  <td><strong>Opportunities</strong></td>
  <td>Commitment recommendations (Savings Plans / Reserved Instances), rightsizing and advisor-style opportunities, optional FinOps remediation tickets</td>
</tr>
<tr>
  <td><strong>Chargeback</strong></td>
  <td>Generate monthly invoices by scope; list and download CSV exports</td>
</tr>
<tr>
  <td><strong>Anomalies</strong></td>
  <td>Unexpected spend spikes from snapshot comparison (severity, dimension, source, status)</td>
</tr>
</tbody>
</table>

## Consolidated spend by dimension

<p>
On the <strong>Showback</strong> tab, use <strong>Group by</strong> to break down estimated spend. Available dimensions include:
</p>

<div class="cost-tabs">
  <span class="active">Organization</span>
  <span>Project</span>
  <span>Workspace</span>
  <span>Environment</span>
  <span>Stack</span>
  <span>Team / repository</span>
  <span>Terraform target</span>
  <span>Service</span>
  <span>Cloud provider</span>
  <span>Region</span>
  <span>Engine</span>
</div>

<p>
The <strong>Cost estimates</strong> table (on <strong>Overview</strong> and <strong>Costs</strong>) uses cascading filters for organization, project, workspace, environment, and stack. Click a resource count to open resource-level pricing details.
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
  <td>Hierarchy attribution from the scanned stack</td>
</tr>
<tr>
  <td>TF workspace</td>
  <td>Terraform workspace name within the stack</td>
</tr>
<tr>
  <td>Monthly</td>
  <td>Estimated monthly cost for that row</td>
</tr>
<tr>
  <td>Resources</td>
  <td>Number of priced resources (click to open detail dialog)</td>
</tr>
<tr>
  <td>Savings</td>
  <td>Potential monthly savings for that estimate</td>
</tr>
</tbody>
</table>
</div>

<div class="cost-two-column">

<div>
## What you can do

<ul class="cost-check-list">
  <li>Scan Terraform stacks on demand or on a Daily / Weekly / Monthly schedule (per stack).</li>
  <li>Switch between <strong>Built-in pricing</strong> and <strong>Configured Infracost</strong> (when integrated).</li>
  <li>Sync <strong>cloud billing</strong> connectors and reconcile bills to attributed spend.</li>
  <li>Compare cost against a previous scan baseline (delta on estimates and per-target rows).</li>
  <li>Review <strong>Opportunities</strong> for rightsizing, idle waste, commitments, and cloud advisor findings.</li>
  <li>Detect anomalies with <strong>Check for anomalies</strong> on the Anomalies tab (<code>cost:manage</code>).</li>
  <li>Generate chargeback invoices (<code>cost:manage</code>) and download invoice CSV (<code>cost:read</code>).</li>
  <li>Create FinOps remediation tickets from opportunities (<code>cost:manage</code>).</li>
</ul>
</div>

<div class="cost-report-box">
  <h3>Resource detail includes</h3>
  <ul>
    <li>Per-resource monthly and annual cost</li>
    <li>Discovery source: provisioned Terraform state, workspace config cache, or repository IaC (preview)</li>
    <li>Cost delta vs. previous scan</li>
    <li>Idle resource count and optimization recommendations</li>
    <li>Infracost badge when that engine was used</li>
  </ul>
</div>

</div>

## Permissions

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
  <td>View Cost Explorer (including billing summary, reconciliation, estimates, showback, anomalies list, invoice list/download)</td>
</tr>
<tr>
  <td><code>cost:manage</code></td>
  <td>Run stack scans, save scan schedules, sync cloud billing, run reconciliation, generate chargeback invoices, capture anomaly snapshots, acknowledge anomalies, configure alert settings, create/update FinOps remediations</td>
</tr>
</tbody>
</table>

## Anomalies

<p>
On the <strong>Anomalies</strong> tab, click <strong>Check for anomalies</strong> to capture a baseline snapshot and compare current spend (<code>cost:manage</code>).
Open anomalies show severity, dimension, source, previous vs. current amounts, and percent change. Use <strong>Acknowledge</strong> to close reviewed items (<code>cost:manage</code>).
</p>

<div class="cost-note">

<strong>Tip:</strong> Run at least one <strong>stack scan</strong> and/or connect <strong>cloud billing</strong> before relying on Showback, Opportunities, or Anomalies — those views combine scan attribution, inventory, and billing data when available.

</div>



<div class="page-navigation">

    <a class="nav-button previous"
        href="{{ '/axio/operations/drift/' | relative_url }}">
        ← Drift Detection
    </a>

    <a class="nav-button next"
        href="{{ '/axio/operations/technical-debt/overview/' | relative_url }}">
        Technical Debt →
    </a>

</div>

