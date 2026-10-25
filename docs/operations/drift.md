---
layout: default
nav_order: 2
parent: Operations
title: Drift Detection
permalink: /axio/operations/drift/
---

<link rel="stylesheet" href="{{ '/assets/css/drift-detection.css' | relative_url }}">

<div class="drift-detection-page" markdown="1">

# Drift Detection

Open **Operations → Drift Detection** to see whether live cloud infrastructure still matches what you declared in code. Axio runs non-destructive IaC plans or previews on your stack's assigned runner and surfaces differences as drift.

Access requires the **`operations`** platform entitlement (Professional and Enterprise) and organization permission **`drift:read`**. Creating watches, running checks, pausing monitors, and org drift settings require **`drift:manage`**. Applying remediation requires **`drift:remediate`**.

<div class="operations-callout operations-callout-info">
  <div class="operations-callout-icon">ⓘ</div>
  <div>
    <strong>Why drift detection?</strong>
    <p>
      Infrastructure can change outside of your pipelines — manual console edits,
      emergency fixes, or external tools. Drift detection identifies those
      differences early so you can investigate, acknowledge, or remediate before
      environments become unreliable.
    </p>
  </div>
</div>

## Supported engines

Drift monitors work with **Terraform**, **OpenTofu**, and **Pulumi** stacks that have deployed infrastructure:

| Engine | Check method |
|--------|----------------|
| **Terraform** | Non-destructive <code>terraform plan -refresh-only</code> on the runner |
| **OpenTofu** | Non-destructive <code>tofu plan -refresh-only</code> on the runner |
| **Pulumi** | Non-destructive Pulumi preview on the runner |

Other IaC engines may appear in inventory but are not yet supported for Operations monitors.

**CloudFormation** stacks appear under **All sources** for visibility, but scheduled Operations monitors apply to IaC workspace watches only. CloudFormation drift uses stack deployment workflows with a **DRIFT_DETECTION** operation instead (open **CloudFormation** from the hub list).

## How it works

Axio compares **desired state** (from your stack workspace or Git repository) with **actual state** in the cloud.

<div class="drift-flow">
  <div class="drift-flow-step drift-flow-blue">
    <div class="drift-flow-icon">&lt;/&gt;</div>
    <strong>1. Desired state</strong>
    <span>Stack workspace or<br>Git repository</span>
  </div>

  <span class="drift-flow-arrow">→</span>

  <div class="drift-flow-step drift-flow-green">
    <div class="drift-flow-icon">☁</div>
    <strong>2. Actual state</strong>
    <span>Live infrastructure<br>in your cloud</span>
  </div>

  <span class="drift-flow-arrow">→</span>

  <div class="drift-flow-step drift-flow-purple">
    <div class="drift-flow-icon">⌕</div>
    <strong>3. Drift check</strong>
    <span>Runner runs plan /<br>preview and compares</span>
  </div>

  <span class="drift-flow-arrow">→</span>

  <div class="drift-result">
    <div class="drift-result-row drift-result-ok">
      <span class="drift-result-icon">✓</span>
      <span><strong>In sync</strong><small>No changes detected</small></span>
    </div>
    <div class="drift-result-row drift-result-alert">
      <span class="drift-result-icon">!</span>
      <span><strong>Drift detected</strong><small>Live state differs from declared</small></span>
    </div>
  </div>
</div>

## Drift Detection dashboard

The page has **four** tabs:

| Tab | Purpose |
|-----|---------|
| **Watched** | Monitors you configured with schedules or manual checks |
| **All sources** | CloudFormation visibility, watched workspace summary, and inventory for ad hoc checks |
| **Governance** | Production SLO, posture reports, retention settings, MSP rollups, and auditor exports |
| **External inventory** | Discovered cloud resources with management, drift, and governance classification |

A status banner on **Watched** and **All sources** summarizes workspaces that need attention, failed checks, drift that is acknowledged or snoozed, or monitors waiting for a first check. The list auto-refreshes about every 30 seconds.

---

## Watched

The **Watched** tab lists IaC workspaces under active drift monitors.

| Field | Description |
|-------|-------------|
| **Stack** | Stack being monitored |
| **Workspace** | Workspace (environment) within the stack; shows **Paused** when the monitor is disabled |
| **Engine** | IaC engine — Terraform, OpenTofu, or Pulumi |
| **Level** | **Stack** (workspace desired state vs live) or **Repository** (Git vs state vs live) |
| **Status** | Result of the latest check (see statuses below) |
| **Last checked** | When the most recent check completed |
| **Duration** | How long the last check took |
| **Schedule** | Check frequency, **Manual checks**, or **Paused** |
| **Actions** | Run check, fix drift (when attention needed), stop watching (icon buttons) |

When check history exists, use **Show trends &amp; analytics** for drift rate charts and scoreboard metrics.

### Drift check statuses

| Status | Meaning |
|--------|---------|
| **In sync** | Live infrastructure matches declared configuration |
| **Drift detected** | Plan or preview found create, update, or destroy changes |
| **Acknowledged** | Display label when drift is detected but temporarily **suppressed** via acknowledge/snooze (underlying status remains drift detected) |
| **Check failed** | The check could not complete (generic error) |
| **Plan failed** | The IaC plan or preview failed on the runner |
| **Runner unavailable** | No runner was available to execute the check |
| **Not checked yet** | Monitor created but no check has run |

---

## All sources

The **All sources** tab provides a hub view:

- **CloudFormation stacks** — Drift status from workflow-based CFN checks (not Operations monitors); rows open **CloudFormation**
- **Watched IaC workspaces** — Summary of monitored stacks with status and schedule
- **Inventory (not watched)** — Deployed stacks and workspaces eligible for drift checks; use **Ad hoc check** to run once without creating a schedule (requires <code>drift:manage</code> and a supported engine)

After an ad hoc check, you can **save the workspace as a watch** for ongoing monitoring.

---

## External inventory

The **External inventory** tab shows cloud resources discovered outside your declared stacks, with filters for management source (Axio-managed, external, unmanaged, and related states), reconciliation coverage, and per-resource drift/governance displays. Use it to find unmanaged or externally changed assets that will not appear on IaC workspace monitors alone.

---

<div class="drift-two-column">

<div class="drift-section">

<h2>Watch a stack</h2>

<p>Use <strong>Watch stack</strong> to add a stack workspace to Drift Detection (<code>drift:manage</code>).</p>

<ol>
  <li>Select the <strong>stack</strong> and <strong>workspace</strong> (one monitor per workspace — e.g. dev, stage, prod).</li>
  <li>Choose <strong>Drift comparison level</strong>:
    <ul>
      <li><strong>Stack workspace</strong> — Compare workspace desired configuration to live infrastructure</li>
      <li><strong>Git repository</strong> — Sync from Git, then compare Git, state, and live cloud (three-way)</li>
    </ul>
  </li>
  <li>Optionally enable <strong>scheduled drift detection</strong> and pick a frequency (continuous interval on the runner).</li>
  <li>Optionally run the <strong>first check immediately</strong>.</li>
  <li>Under <strong>Notification settings</strong>, configure ChatOps/email toggles, and optionally <strong>auto-remediate</strong> (apply when drift is detected).</li>
</ol>

<p>Once watched, the workspace appears on the <strong>Watched</strong> tab with its current status and schedule.</p>

<div class="drift-info-card">

<strong>Prerequisites</strong>

<p>The stack must have deployed infrastructure and a supported IaC engine (Terraform, OpenTofu, or Pulumi). Checks run on the stack's assigned runner policy.</p>

</div>

</div>

<div class="drift-section">

<h2>Check outcomes</h2>

<p>Each watched workspace displays the result of its most recent check.</p>

<div class="drift-status-card drift-success">

<strong>✓ In sync</strong>

<p>The latest check completed successfully and live infrastructure matches the declared configuration.</p>

</div>

<div class="drift-status-card drift-failed">

<strong>! Drift detected</strong>

<p>The plan or preview found differences. Open the monitor detail view to review resource changes, severity, and remediation options.</p>

</div>

<div class="drift-status-card drift-failed">

<strong>× Check or plan failed</strong>

<p>The IaC plan or preview could not complete on the runner. This does not necessarily mean infrastructure drifted — investigate runner availability and workspace configuration first.</p>

</div>

</div>

</div>

<div class="drift-note">

<strong>Note:</strong> A failed check can mean the IaC plan or preview could not complete on the assigned runner — not confirmed infrastructure drift. Open the monitor detail view, review <strong>readiness</strong> <strong>checks</strong>, and run a new check after fixing runner or configuration issues.

</div>

---

<div class="drift-two-column">

<div class="drift-section">

<h2>Check schedule</h2>

<p>When you enable scheduled drift detection on a watch, choose from:</p>

<div class="drift-schedule-grid">

<div class="drift-schedule-card">

<strong>Every 15 minutes</strong>

<span>Frequent monitoring</span>

</div>

<div class="drift-schedule-card">

<strong>Every 30 minutes</strong>

<span>Regular monitoring</span>

</div>

<div class="drift-schedule-card">

<strong>Every hour</strong>

<span>Hourly monitoring</span>

</div>

<div class="drift-schedule-card">

<strong>Every 2 hours</strong>

<span>Periodic monitoring</span>

</div>

<div class="drift-schedule-card">

<strong>Every 4 hours</strong>

<span>Light monitoring</span>

</div>

</div>

<p>Leave scheduling off for <strong>Manual checks</strong> only. The <strong>Schedule</strong> column shows the configured frequency, or <strong>Paused</strong> when the monitor is disabled.</p>

<p><strong>In-app</strong> drift notifications are always enabled for watches. Configure <strong>ChatOps</strong> (Slack, Teams, webhook) and <strong>email</strong> under <strong>Notification</strong><strong>settings</strong> when creating or editing a watch. Subscribe integrations to the <strong>Drift</strong><strong>detected</strong> event under <strong>Administration</strong> → <strong>Integrations</strong> → <strong>ChatOps</strong>.</p>

</div>

<div class="drift-section">

<h2>Manage watched stacks</h2>

<p>The <strong>Actions</strong> column on the Watched tab provides:</p>

<ul>
  <li><strong>Run check now</strong> — Trigger an immediate drift check (<code>drift:manage</code>)</li>
  <li><strong>Preview and fix drift</strong> — Shown when the workspace <strong>needs attention</strong>; opens remediation preview (<code>drift:remediate</code>)</li>
  <li><strong>Stop watching</strong> — Remove the monitor and stop scheduled checks (<code>drift:manage</code>)</li>
</ul>

<p>Click a row to open the <strong>monitor detail</strong> dialog for check history, resource diffs, plan output, readiness checks, insights, acknowledge/snooze controls, and watch settings (schedule, auto-remediate, pause).</p>

<p><strong>Acknowledge</strong> drift to suppress alerts temporarily while you investigate. <strong>Snooze</strong> pauses alerting for a period. <strong>Fix drift</strong> runs guided or apply remediation when permitted by stack policy (including optional <strong>require</strong> <strong>acknowledgment</strong> <strong>before</strong> <strong>remediate</strong> and <strong>block</strong> <strong>stack</strong> <strong>apply</strong> <strong>while</strong> <strong>unacknowledged</strong> <strong>drift</strong> settings).</p>

</div>

</div>


<h2>Permissions</h2>

<table class="approval-lifecycle-table">
  <thead>
    <tr>
      <th>Permission</th>
      <th>Capability</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>drift:read</code></td>
      <td>View monitors, check history, hub/inventory, reports, and SLO status (Operations Drift UI)</td>
    </tr>
    <tr>
      <td><code>drift:manage</code></td>
      <td>Create watches, run checks, ad hoc checks, pause/stop monitors, configure org drift settings</td>
    </tr>
    <tr>
      <td><code>drift:remediate</code></td>
      <td>Preview and apply drift remediation (<code>terraform apply</code>, <code>tofu apply</code>, or <code>pulumi up</code> on the runner)</td>
    </tr>
  </tbody>
</table>

The **`operations`** platform entitlement (Professional and Enterprise plans) gates Drift Detection APIs and the Operations UI.



<h2>Governance</h2>

<p>The <strong>Governance</strong> tab includes:</p>

<ul>
  <li><strong>Production check SLO</strong> — Target percentage of production stacks checked within a rolling window. Production stacks are identified from deployment context linked to environments with catalog type <strong>PRODUCTION</strong> (not name patterns).</li>
  <li><strong>Posture report</strong> — Markdown summary of drift health (downloadable); optional <strong>Email</strong> + <strong>ChatOps</strong> delivery</li>
  <li><strong>Operations drift auditor pack</strong> — ZIP export of posture and evidence artifacts</li>
  <li><strong>Check history retention</strong> — How long check records are kept (plus configurable prod SLO target and window)</li>
  <li><strong>MSP rollup</strong> — Parent organizations can view child-tenant SLO and open drift episodes</li>
</ul>


<div class="drift-warning">

<strong>Important</strong>

<p>A failed drift check does not necessarily mean infrastructure has drifted. The check itself may have failed because the IaC plan or preview could not complete on the runner. Only <strong>Drift detected</strong> status confirms a difference between declared and live state.</p>

</div>

</div>


<div class="page-navigation">

    <a class="nav-button previous"
        href="{{ '/axio/operations/approval/' | relative_url }}">
        ← Approval
    </a>

    <a class="nav-button next"
        href="{{ '/axio/operations/cost/' | relative_url }}">
        Cost Explorer → 
    </a>

</div>

