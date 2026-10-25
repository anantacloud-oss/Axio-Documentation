---
layout: default
nav_order: 1
parent: Operations
title: Approvals
permalink: /axio/operations/approval/
---

<link rel="stylesheet" href="{{ '/assets/css/approvals.css' | relative_url }}">


# Approvals

<div class="approval-intro">
  <p>
    Open <strong>Operations → Approvals</strong> for your decision inbox.
    Axio routes pending items here when a
    <strong>workflow gate</strong> pauses a stack deployment,
    when a <strong>Platform as Code</strong> synchronization plan
    requires sign-off, or when a <strong>policy</strong>-driven
    approval is raised.
  </p>
</div>



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

<section class="approval-section approval-section-request-types" markdown="1">

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
      <td><strong>
           Platform as Code</strong></td>
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
      <td><strong>
            Workflow</strong></td>
      <td>A stack deployment reaches an approval stage in its workflow</td>
      <td>Environment or project (e.g. Production)</td>
    </tr>
    <tr>
      <td><strong>
           Policy</strong></td>
      <td>Other governance or policy-driven approval requests</td>
      <td>Varies by policy</td>
    </tr>
  </tbody>
</table>

</section>



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


<div class="approvals-page">

  
  <section class="approval-section" id="using-approvals">

    <div class="approval-section-heading">
      <span class="approval-section-number">01</span>
      <div>
        <h2>Using the Approvals page</h2>
        <p>Manage pending decisions and review completed requests.</p>
      </div>
    </div>

    <p>
      The Approvals page brings together requests from
      <strong>Platform as Code sync plans</strong> and
      <strong>workflow gates</strong>. Policy-class items also appear
      with the request type <strong>Policy</strong>.
    </p>

    <div class="approval-feature-grid">

      <article class="approval-feature-card">
        <div class="approval-feature-icon approval-icon-purple">
          <span aria-hidden="true">▤</span>
        </div>
        <h3>Inbox</h3>
        <p>
          Review pending requests that require an approval decision.
          Use <strong>Assigned to me</strong> to list only requests
          where you can decide and have not already approved at the
          current level.
        </p>
      </article>

      <article class="approval-feature-card">
        <div class="approval-feature-icon approval-icon-blue">
          <span aria-hidden="true">◷</span>
        </div>
        <h3>History</h3>
        <p>
          View completed requests. This tab is visible only to users
          with <code>approval:manage</code>. Authorized users can
          remove entries from history.
        </p>
      </article>

      <article class="approval-feature-card">
        <div class="approval-feature-icon approval-icon-green">
          <span aria-hidden="true">⌕</span>
        </div>
        <h3>Search and filters</h3>
        <p>
          Search by title, environment, requester, policy, status,
          and related fields. Category chips at the top show pending
          counts for Platform as Code, Workflow gate, and Other.
        </p>
      </article>

    </div>

    <h3 class="approval-subheading">Understanding the request table</h3>

    <p>Each row provides the following information:</p>

    <div class="approval-field-grid">
      <div><strong>Request type</strong><span>Platform as Code, Workflow, or Policy.</span></div>
      <div><strong>Name</strong><span>The request or associated resource name.</span></div>
      <div><strong>Scope</strong><span>The applicable environment, project, or resource.</span></div>
      <div><strong>Status</strong><span>The current request state.</span></div>
      <div><strong>Requested by</strong><span>The person who initiated the request.</span></div>
      <div><strong>Approved by</strong><span>The approver or approvers recorded for the request.</span></div>
      <div><strong>Waiting</strong><span>Request age, optional expiry, and a Your decision chip when applicable.</span></div>
      <div><strong>Actions</strong><span>Use Review to open a pending request.</span></div>
    </div>

    <div class="approval-callout approval-callout-info">
      <span class="approval-callout-symbol" aria-hidden="true">i</span>
      <div>
        <strong>Reviewing a request</strong>
        <p>
          Click a row or select <strong>Review</strong> to open the
          detail dialog. Add an optional comment, then select
          <strong>Approve</strong> or <strong>Reject</strong>.
          The table supports pagination.
        </p>
      </div>
    </div>

  </section>

  <section class="approval-section" id="request-types">

    <div class="approval-section-heading">
      <span class="approval-section-number">02</span>
      <div>
        <h2>Request types</h2>
        <p>Identify why an approval request appears in the inbox.</p>
      </div>
    </div>

    <div class="approval-table-wrap">
      <table class="approval-lifecycle-table">
        <thead>
          <tr>
            <th scope="col">Type</th>
            <th scope="col">When it appears</th>
            <th scope="col">Typical scope</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td>
              <span class="approval-type-label">
                <span class="approval-type-icon approval-type-platform" aria-hidden="true">▤</span>
                Platform as Code
              </span>
            </td>
            <td>
              A Git synchronization plan needs manual sign-off because
              repository policy requires <strong>manual approval</strong>,
              and/or the plan includes <strong>updates or pending removals</strong>
              on sensitive resources marked with
              <code>metadata.sensitive: true</code> or the label/annotation
              <code>platform.axio.io/sensitive</code>.
            </td>
            <td>Repository or resource name, often shown as Git synchronization.</td>
          </tr>
          <tr>
            <td>
              <span class="approval-type-label">
                <span class="approval-type-icon approval-type-workflow" aria-hidden="true">⚙</span>
                Workflow
              </span>
            </td>
            <td>A stack deployment reaches an approval stage in its workflow.</td>
            <td>Environment or project, such as Production.</td>
          </tr>
          <tr>
            <td>
              <span class="approval-type-label">
                <span class="approval-type-icon approval-type-policy" aria-hidden="true">▤</span>
                Policy
              </span>
            </td>
            <td>Other governance or policy-driven approval requests.</td>
            <td>Varies by policy.</td>
          </tr>
        </tbody>
      </table>
    </div>

  </section>

  <section class="approval-section" id="workflow-approvals">

    <div class="approval-section-heading">
      <span class="approval-section-number">03</span>
      <div>
        <h2>How workflow approvals work</h2>
        <p>Deployment execution pauses until an authorized approver decides.</p>
      </div>
    </div>

    <div class="approval-flow" aria-label="Workflow approval process">

      <div class="approval-flow-step">
        <span class="approval-flow-index">01</span>
        <strong>Workflow reaches an approval stage</strong>
        <span class="approval-flow-caption">Deployment pauses</span>
      </div>

      <span class="approval-flow-arrow" aria-hidden="true">→</span>

      <div class="approval-flow-step approval-flow-step-yellow">
        <span class="approval-flow-index">02</span>
        <strong>Request created and notified</strong>
        <span class="approval-flow-caption">Approvers are notified</span>
      </div>

      <span class="approval-flow-arrow" aria-hidden="true">→</span>

      <div class="approval-flow-step approval-flow-step-purple">
        <span class="approval-flow-index">03</span>
        <strong>Approver reviews the request</strong>
        <span class="approval-flow-caption">Review details and comment</span>
      </div>

      <span class="approval-flow-arrow" aria-hidden="true">→</span>

      <div class="approval-flow-step approval-flow-step-green">
        <span class="approval-flow-index">04</span>
        <strong>Approved or rejected</strong>
        <span class="approval-flow-caption">Decision is recorded</span>
      </div>

      <span class="approval-flow-arrow" aria-hidden="true">→</span>

      <div class="approval-flow-step approval-flow-step-blue">
        <span class="approval-flow-index">05</span>
        <strong>Workflow continues or stops</strong>
        <span class="approval-flow-caption">Outcome is applied</span>
      </div>

    </div>

    <div class="approval-outcome-grid">
      <div class="approval-outcome-card approval-outcome-success">
        <strong>✓ Approved</strong>
        <p>The workflow resumes.</p>
      </div>
      <div class="approval-outcome-card approval-outcome-danger">
        <strong>✕ Rejected</strong>
        <p>The deployment run does not proceed.</p>
      </div>
    </div>

    <p>
      You can also approve or reject a request from the
      <strong>stack deployment / workflow run detail</strong> view
      when the run is paused at an approval stage. The same request
      appears under <strong>Operations → Approvals</strong>.
    </p>

    <div class="approval-callout approval-callout-warning">
      <span class="approval-callout-symbol" aria-hidden="true">!</span>
      <div>
        <strong>Break Glass can bypass the gate</strong>
        <p>
          If Break Glass is active for the target environment, the
          workflow may bypass the approval gate and no inbox item
          is created.
        </p>
      </div>
    </div>

    <h3 class="approval-subheading">Environment approval settings</h3>

    <p>
      Environment-level approval can be disabled when the environment
      policy is off or set to <code>none</code>. Otherwise, if an
      environment-specific policy is missing, workflow gates default
      to manual approval behavior.
    </p>

  </section>

  <section class="approval-section" id="pac-approvals">

    <div class="approval-section-heading">
      <span class="approval-section-number">04</span>
      <div>
        <h2>How Platform as Code approvals work</h2>
        <p>Control when Git reconciliation plans can be applied.</p>
      </div>
    </div>

    <div class="approval-pac-panel">
      <div class="approval-pac-panel-header">
        <span class="approval-pac-icon" aria-hidden="true">↻</span>
        <div>
          <h3>Synchronization approval</h3>
          <span class="approval-mini-label">PLAN REVIEW</span>
        </div>
      </div>

      <p>
        When a synchronization plan requires approval, the sync run
        stays in <strong>awaiting approval</strong> (plan
        <strong>pending</strong>) until a decision is made.
      </p>

      <div class="approval-outcome-grid">
        <div class="approval-outcome-card approval-outcome-success">
          <strong>✓ Approve</strong>
          <p>Applies the Git reconciliation plan.</p>
        </div>
        <div class="approval-outcome-card approval-outcome-danger">
          <strong>✕ Reject</strong>
          <p>Leaves platform resources unchanged.</p>
        </div>
      </div>
    </div>

    <p>
      You can approve or reject requests from
      <strong>Platform as Code → Synchronizations</strong> in the
      <strong>Recent runs</strong> section. This uses the same approval
      requests as <strong>Operations → Approvals</strong>.
    </p>

    <div class="approval-callout approval-callout-info">
      <span class="approval-callout-symbol" aria-hidden="true">↗</span>
      <div>
        <strong>Request details</strong>
        <p>
          The Platform as Code request detail dialog summarizes the
          plan and provides a link to <strong>Open synchronizations</strong>.
        </p>
        <a class="approval-inline-link"
           href="{{ '/axio/platform-as-code/syncs/' | relative_url }}">
          Go to Synchronizations →
        </a>
      </div>
    </div>

  </section>

  <section class="approval-section" id="request-lifecycle">

    <div class="approval-section-heading">
      <span class="approval-section-number">05</span>
      <div>
        <h2>Approval request lifecycle</h2>
        <p>Understand request outcomes and multi-level approval.</p>
      </div>
    </div>

    <p>Requests can be in one of the following states.</p>

    <div class="approval-table-wrap">
      <table class="approval-lifecycle-table approval-status-table">
        <thead>
          <tr>
            <th scope="col">State</th>
            <th scope="col">Description</th>
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
            <td><span class="approval-status approval-status-auto">Auto approved</span></td>
            <td>Approved automatically by policy; no manual action is required.</td>
          </tr>
          <tr>
            <td><span class="approval-status approval-status-emergency">Emergency approved</span></td>
            <td>Approved through emergency break-glass on the approval policy when enabled (API); this is not a separate button in the Operations Approvals dialog today.</td>
          </tr>
          <tr>
            <td><span class="approval-status approval-status-expired">Expired</span></td>
            <td>The approval window elapsed; the outcome depends on the policy expiry action.</td>
          </tr>
          <tr>
            <td><span class="approval-status approval-status-canceled">Canceled</span></td>
            <td>The underlying run or request was canceled before a decision.</td>
          </tr>
        </tbody>
      </table>
    </div>

    <div class="approval-callout approval-callout-info">
      <span class="approval-callout-symbol" aria-hidden="true">↗</span>
      <div>
        <strong>Multi-level approval policies</strong>
        <p>
          When more than one level is configured, the request detail
          dialog displays a stepper. Each level may require one or
          more approvers before the request advances.
        </p>
      </div>
    </div>

  </section>

  <section class="approval-section" id="who-can-approve">

    <div class="approval-section-heading">
      <span class="approval-section-number">06</span>
      <div>
        <h2>Who can approve?</h2>
        <p>Permissions and assignment rules depend on the request type.</p>
      </div>
    </div>

    <h3 class="approval-subheading">Organization permissions</h3>

    <div class="approval-permission-grid">

      <article class="approval-permission-card">
        <code>governance:approve</code>
        <p>
          Allows eligible users to open Operations → Approvals and
          decide most requests, subject to scope and request-specific rules.
        </p>
      </article>

      <article class="approval-permission-card">
        <code>approval:manage</code>
        <p>
          Allows eligible users to decide requests, view the History
          tab, and remove completed history entries.
        </p>
      </article>

    </div>

    <p>
      Organization <strong>Owner</strong> and <strong>Admin</strong>
      roles include these capabilities by default and can see
      organization-wide requests when scope rules allow.
    </p>

    <div class="approval-permission-section">
      <h3>Workflow deployment gates</h3>
      <p>For <strong>Workflow</strong> requests involving stack deployments:</p>
      <ul class="approval-detail-list">
        <li>
          Users with <code>governance:approve</code> or
          <code>approval:manage</code> can decide, subject to
          environment scope rules.
        </li>
        <li>
          <strong>Environment owners</strong> — users or groups
          configured under <strong>Organization → Environments → Assign owner</strong>
          — receive deployment and approval assignments. They can approve
          when eligible for that environment and permitted by self-approval rules.
        </li>
        <li>
          <strong>Multi-level policies</strong> may require sequential
          or parallel sign-off across configured approver lists.
        </li>
      </ul>

      <div class="approval-callout approval-callout-warning">
        <span class="approval-callout-symbol" aria-hidden="true">!</span>
        <div>
          <strong>Self-approval restriction</strong>
          <p>
            If the user who triggered a deployment tries to approve it
            while self-approval is disabled for that environment,
            approval is blocked with a clear message. Rejection remains
            available.
          </p>
        </div>
      </div>
    </div>

    <div class="approval-permission-section">
      <h3>Platform as Code sync plans</h3>
      <p>For <strong>Platform as Code</strong> requests:</p>
      <ul class="approval-detail-list">
        <li>
          Users with <code>pac:manage</code>,
          <code>approval:manage</code>, or
          <code>governance:approve</code> can decide.
        </li>
        <li>
          Scoped members with <code>pac:read</code> and
          <code>iac:manage</code> may approve sync plans that affect
          only resources in their scope. The server re-checks
          authorization when a decision is submitted.
        </li>
      </ul>
    </div>

    <div class="approval-permission-section">
      <h3>Policy and other requests</h3>
      <p>
        When an approval policy defines explicit approver lists
        (users or groups), only assigned approvers or users with
        <code>approval:manage</code> or
        <code>governance:approve</code> can decide.
      </p>
    </div>

    <aside class="approval-tip-card">
      <div class="approval-tip-heading">
        <div>
          <span class="approval-tip-eyebrow">RECOMMENDED CONFIGURATION</span>
          <h3>Environment owners and skip self-approval</h3>
        </div>
      </div>

      <p>
        For workflow approvals, assign at least one user or group as
        an <strong>Environment owner</strong> on the target environment.
        Owners can run workflows there and approve deployment gates
        when they are eligible approvers.
      </p>

      <p>
        Enable <strong>Skip self-approval for workflows</strong>
        (on by default when assigning owners) so the user who triggered
        a deployment cannot approve their own run, even if they are
        listed as an owner. Another owner must approve those requests.
      </p>

      <p>
        Platform as Code sync approvals follow repository manual-approval
        settings and Git sensitivity markers, not environment-owner
        assignment. Use
        <a href="{{ '/axio/platform-as-code/syncs/' | relative_url }}">
          Synchronizations
        </a>
        to monitor runs after you decide.
      </p>
    </aside>

  </section>

  <section class="approval-section approval-section-last"
           id="approval-notifications">

    <div class="approval-section-heading">
      <span class="approval-section-number">07</span>
      <div>
        <h2>Notifications</h2>
        <p>Stay informed about approval requests and their outcomes.</p>
      </div>
    </div>

    <p>
      Approval <strong>policies</strong> can define notification
      channels, including in-app notifications, email, Slack, and
      Microsoft Teams. When configured and integrated, the platform
      sends notifications for relevant request lifecycle events.
    </p>

    <div class="approval-notification-grid">
      <div class="approval-notification-item">
        <span class="approval-notification-icon">◉</span>
        <div>
          <strong>In-app</strong>
          <p>Governance notifications and approval updates.</p>
        </div>
      </div>
      <div class="approval-notification-item">
        <span class="approval-notification-icon">✉</span>
        <div>
          <strong>Email</strong>
          <p>Policy-configured email notifications.</p>
        </div>
      </div>
      <div class="approval-notification-item">
        <span class="approval-notification-icon">↗</span>
        <div>
          <strong>Slack and Teams</strong>
          <p>External channels when configured and integrated.</p>
        </div>
      </div>
    </div>

    <p>
      Workflow gate requests also raise <strong>governance in-app
      notifications</strong> to organization administrators when a
      deployment approval is requested.
    </p>

    <div class="approval-callout approval-callout-info">
      <span class="approval-callout-symbol" aria-hidden="true">i</span>
      <div>
        <strong>Decision history and delivery tracking</strong>
        <p>
          The Operations request detail dialog shows previous decisions
          and optional comments. Notification delivery history is stored
          for the request but is not displayed in that dialog today.
        </p>
      </div>
    </div>

  </section>

  <footer class="approval-page-footer">
    <span class="approval-footer-mark" aria-hidden="true">✓</span>
    <div>
      <strong>Governance with clear accountability</strong>
      <p>
        Review each request, verify its scope, and record your decision
        before the associated workflow or synchronization proceeds.
      </p>
    </div>
  </footer>

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

