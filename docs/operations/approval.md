---
layout: default
nav_order: 1
parent: Operations
title: Approvals
permalink: /axio/operations/approval/
---

<link rel="stylesheet" href="{{ '/assets/css/approvals.css' | relative_url }}">


<div class="approvals-page" markdown="1">

# Approvals

Open **Operations → Approvals** for your decision inbox. Axio routes pending items here when a **workflow gate** pauses a stack deployment, when a **Platform as Code** synchronization plan requires sign-off, or when a **policy**-driven approval is raised.

Access to this page requires **`governance:approve`** or **`approval:manage`**. (The API also uses **`approval:read`** for listing; the Operations nav is gated as above.)

<div class="operations-callout operations-callout-info">
  <div class="operations-callout-icon">ⓘ</div>
  <div>
    <strong>Why approvals?</strong>
    <p>
      They enforce change control, meet compliance requirements, and reduce the risk of unintended
      production changes — whether from a deployment workflow or a Git-driven platform sync.
    </p>
  </div>
</div>

## Request types

Pending items are grouped into three categories in the inbox:

<table class="approval-lifecycle-table">
  <thead>
    <tr>
      <th>Type</th>
      <th>When it appears</th>
      <th>Typical scope</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><strong>Platform as Code</strong></td>
      <td>
        A Git synchronization plan needs manual sign-off because the repository policy requires
        <strong>manual approval</strong>, and/or the plan includes
        <strong>updates</strong> or <strong>pending removals</strong> on resources marked sensitive
        (<code>metadata.sensitive: true</code> or label/annotation
        <code>platform.axio.io/sensitive</code>)
      </td>
      <td>Repository or resource name (often shown as Git synchronization)</td>
    </tr>
    <tr>
      <td><strong>Workflow</strong></td>
      <td>A stack deployment reaches an approval stage in its workflow</td>
      <td>Environment or project (e.g. Production)</td>
    </tr>
    <tr>
      <td><strong>Policy</strong></td>
      <td>Other governance or policy-driven approval requests</td>
      <td>Varies by policy</td>
    </tr>
  </tbody>
</table>

<div class="operations-callout operations-callout-info">
  <div class="operations-callout-icon">ⓘ</div>
  <div>
    <strong>Platform as Code note</strong>
    <p>
      Staged removals (<code>pending_removal</code>) alone do not always require approval — only when
      manual approval is configured for the repository or the removal affects a sensitive resource.
      New creates of sensitive resources follow the repository execution mode unless manual approval
      applies to the whole plan.
    </p>
  </div>
</div>

## Using the Approvals page

The subtitle on the page describes the main sources: **Platform as Code sync plans** and **workflow gates**. Policy-class items still appear with request type **Policy**.

The page has two tabs:

- **Inbox** — Pending requests. Use **Assigned to me** to list only items where you can decide and have not already approved at the current level.
- **History** — Completed requests (visible only with **`approval:manage`**). Users with that permission can **remove** entries from history.

Each row shows **Request type**, **Name**, **Scope**, **Status**, **Requested by**, **Approved by**, and **Waiting** (age, optional expiry, and a **Your decision** chip when applicable). An **Actions** column offers **Review** for pending items. Click a row or **Review** to open the detail dialog, add an optional comment, and **Approve** or **Reject**. The table supports **pagination**.

Search filters by title, environment, requester, policy, status, and related fields. Pending counts appear as category chips at the top of the inbox (**Platform as Code**, **Workflow gate**, **Other**).

Deep links: `?request=&lt;id&gt;` opens a request; `?tab=history` opens History (if permitted).

## How workflow approvals work

When a stack deployment workflow reaches an approval stage, execution pauses until an authorized approver decides.

<div class="approval-flow">
  <div class="approval-flow-step">
    <strong>Workflow reaches<br>approval stage</strong>
  </div>
  <span class="approval-flow-arrow">→</span>

  <div class="approval-flow-step approval-flow-step-yellow">
    <strong>Request created &amp;<br>notified</strong>
  </div>
  <span class="approval-flow-arrow">→</span>

  <div class="approval-flow-step approval-flow-step-purple">
    <strong>Approver reviews<br>the request</strong>
  </div>
  <span class="approval-flow-arrow">→</span>

  <div class="approval-flow-step approval-flow-step-green">
    <strong>Approved /<br>Rejected</strong>
  </div>
  <span class="approval-flow-arrow">→</span>

  <div class="approval-flow-step approval-flow-step-blue">
    <strong>Workflow<br>continues or stops</strong>
  </div>
</div>

If approved, the workflow resumes. If rejected, the deployment run does not proceed.

You can also approve or reject from the **stack deployment / workflow run detail** view when the run is paused at an approval stage — the same request appears under **Operations → Approvals**.

If **Break Glass** is active for the target environment, the workflow may **bypass** the approval gate and no inbox item is created.

Environment-level approval can be disabled when the environment policy is off or set to **none**; otherwise a missing per-environment policy still defaults to manual approval behavior for workflow gates.

## How Platform as Code approvals work

When a synchronization plan requires approval, the sync run stays in **awaiting approval** (plan **pending**) until decided. Approving applies the Git reconciliation plan; rejecting leaves platform resources unchanged.

You can approve or reject from **Platform as Code → Synchronizations** (`/platform-as-code/syncs`) in the **Recent runs** section, which uses the same approval requests as **Operations → Approvals**.

The detail dialog for PaC requests summarizes the plan and links to **Open synchronizations**.

## Approval request lifecycle

Requests can be in one of the following states.

<table class="approval-lifecycle-table">
  <thead>
    <tr>
      <th>State</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><span class="approval-status approval-status-pending">Pending</span></td>
      <td>Waiting for an approver decision. May show time remaining until expiry.</td>
    </tr>
    <tr>
      <td><span class="approval-status approval-status-approved">Approved</span></td>
      <td>Approved manually; the workflow or sync plan can proceed.</td>
    </tr>
    <tr>
      <td><span class="approval-status approval-status-rejected">Rejected</span></td>
      <td>Rejected by an approver; the workflow stops or the sync plan is not applied.</td>
    </tr>
    <tr>
      <td><strong>Auto approved</strong></td>
      <td>Approved automatically by policy (no manual action required).</td>
    </tr>
    <tr>
      <td><strong>Emergency approved</strong></td>
      <td>Approved through emergency break-glass on the approval policy when enabled (API); not a separate button on the Operations Approvals dialog today.</td>
    </tr>
    <tr>
      <td><strong>Expired</strong></td>
      <td>The approval window elapsed; outcome depends on policy expiry action.</td>
    </tr>
    <tr>
      <td><strong>Canceled</strong></td>
      <td>The underlying run or request was canceled before a decision.</td>
    </tr>
  </tbody>
</table>

Multi-level policies show a stepper in the request detail dialog when more than one level is configured. Each level may require one or more approvers before the request advances.

## Who can approve?

Permissions and assignment depend on the request type.

### Permissions

Users with either of these organization permissions can open **Operations → Approvals** and decide most requests:

- <code>governance:approve</code>
- <code>approval:manage</code> (also required to view the **History** tab and remove completed entries)

Organization **Owner** and **Admin** roles include these capabilities by default and can see org-wide requests when scope rules allow.

### Workflow deployment gates

For **Workflow** requests (stack deployments):

- Users with <code>governance:approve</code> or <code>approval:manage</code> can decide (subject to environment scope rules).
- **Environment owners** — users or groups under **Organization → Environments → Assign owner** — receive deploy/approve assignments; they can approve when they are eligible approvers for that environment and pass self-approval rules.
- **Multi-level** policies may require sequential or parallel sign-off across configured approver lists.

Self-approval: if the user who **triggered** the deployment tries to approve and self-approval is disabled for that environment, approve is blocked with a clear message; reject remains available.

### Platform as Code sync plans

For **Platform as Code** requests:

- Users with <code>pac:manage</code>, <code>approval:manage</code>, or <code>governance:approve</code> can decide.
- Scoped members with <code>pac:read</code> and <code>iac:manage</code> may approve sync plans that affect only resources in their scope (server re-checks on decide).

### Policy and other requests

When an approval policy defines explicit approver lists (users or groups), only assigned approvers — or users with <code>approval:manage</code> / <code>governance:approve</code> — can decide.

<div class="tip-box">

    <div class="tip-header">

        <img src="{{ '/assets/icons/lightbulb.svg' | relative_url }}"
             alt="Tip">

        <h3>Tip — Environment owners &amp; skip self-approval</h3>

    </div>

    <p>
        For <strong>workflow</strong> approvals, assign at least one user or group as an
        <strong>Environment owner</strong> on the target environment. Owners can run workflows there
        and approve deployment gates when they are eligible approvers.
    </p>

    <p>
        Enable <strong>Skip self-approval for workflows</strong> (on by default when assigning owners) so the user who
        triggered a deployment cannot approve their own run — even if they are listed as an owner.
        Another owner must approve those requests.
    </p>

    <p>
        Platform as Code sync approvals follow repository manual-approval settings and Git sensitivity
        markers, not environment-owner assignment. Use
        <a href="{{ '/axio/platform-as-code/syncs/' | relative_url }}">Synchronizations</a>
        to monitor runs after you decide.
    </p>

</div>

## Notifications

Approval **policies** can define notification channels (**in-app**, **email**, **Slack**, **Microsoft Teams**) when configured; the platform sends notifications on request lifecycle events where integrated.

Workflow gate requests also raise **governance in-app notifications** to organization administrators when a deployment approval is requested.

The Operations request detail dialog shows **previous decisions** and optional **comments**. Notification delivery history is stored for the request but is **not** shown in that dialog today.

</div>


<div class="page-navigation">

    <a class="nav-button previous"
        href="{{ '/axio/platform-as-code/history/' | relative_url }}">
        ← History
    </a>

    <a class="nav-button next"
        href="{{ '/axio/operations/drift/' | relative_url }}">
        Drift Detection →
    </a>

</div>

