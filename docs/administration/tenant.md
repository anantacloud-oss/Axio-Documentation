---
layout: default
title: Tenant
parent: Administration
nav_order: 2
permalink: /axio/administration/tenant/
---

<link rel="stylesheet" href="{{ '/assets/css/tenant.css' | relative_url }}">

<div class="tenant-page">

  <div class="tenant-hero">
    <h1>Administration — Tenant</h1>
    <p>Organization identity, sign-in credentials, editable tenant metadata, and high-level tenant insights.</p>
  </div>

  <div class="tenant-info-banner">
    <span class="tenant-info-icon">ⓘ</span>
    <span>
      Open <strong>Administration → Tenant</strong> from the Administration navigation.
      Resource hierarchy (projects, workspaces, environments, business units) lives under <strong>Organization</strong>, not on this page.
    </span>
  </div>

  <section class="tenant-section">
    <h2>What it does</h2>
    <p>Tenant administration covers the current organization’s identity and operational snapshot:</p>
    <div class="tenant-kpi-grid">
      <div class="tenant-kpi-card">
        <div class="tenant-kpi-icon purple">♙</div>
        <span>Identity</span>
        <strong>Current tenant</strong>
        <small>Name, provider vs customer chip, your role, created date</small>
      </div>
      <div class="tenant-kpi-card">
        <div class="tenant-kpi-icon green">◇</div>
        <span>Sign-in</span>
        <strong>Organization ID</strong>
        <small>8-character code members use at login (not the slug)</small>
      </div>
      <div class="tenant-kpi-card">
        <div class="tenant-kpi-icon blue">⌁</div>
        <span>Insights</span>
        <strong>Tenant metrics</strong>
        <small>Members, projects, groups, deployment activity, runner utilization</small>
      </div>
    </div>
  </section>

  <section class="tenant-section">
    <h2>Prerequisites &amp; permissions</h2>
    <div class="tenant-fields">
      <div class="tenant-field">
        <label>Page access</label>
        <p><code>org:update</code> — in the default role matrix this is <strong>OWNER only</strong> (ADMIN does not receive this permission).</p>
      </div>
      <div class="tenant-field">
        <label>Navigation</label>
        <p>Listed under <strong>Administration → Tenant</strong> when the signed-in user holds <code>org:update</code>.</p>
      </div>
      <div class="tenant-field">
        <label>Edit tenant details</label>
        <p>Same <code>org:update</code> permission is required to change organization name and description.</p>
      </div>
    </div>
    <p class="tenant-signin-note">
      Users without <code>org:update</code> cannot access this page.
    </p>
  </section>

  <section class="tenant-section">
    <h2>Current tenant banner</h2>

    <div class="tenant-identity-card">
      <div class="tenant-identity-top">
        <div class="tenant-org-brand">
          <div>
            <div class="tenant-org-name">
              (organization name)
              <span class="tenant-status">Platform provider / Customer tenant</span>
            </div>
            <p>Summary chips: <strong>Your role</strong> (e.g. OWNER), <strong>Created</strong> date.</p>
          </div>
        </div>
      </div>
      <p><small>Reloads organization details and the admin dashboard metrics used by KPI cards and charts.</small></p>
    </div>
  </section>

  <section class="tenant-section">
    <h2>Overview KPIs</h2>
    <p>Three clickable summary cards with counts and subtitles from the admin dashboard when available:</p>

    <div class="tenant-kpi-grid">
      <div class="tenant-kpi-card">
        <div class="tenant-kpi-icon purple">♙</div>
        <span>Members</span>
        <small>Subtitle: <em>N groups</em></small>
      </div>

      <div class="tenant-kpi-card">
        <div class="tenant-kpi-icon green">◇</div>
        <span>Projects</span>
        <small>Subtitle: <em>N workspaces</em></small>
      </div>

      <div class="tenant-kpi-card">
        <div class="tenant-kpi-icon blue">♧</div>
        <span>Groups</span>
        <small>Subtitle: <em>N% deploy success</em></small>
      </div>
    </div>
    <p><small>Team membership is labeled <strong>Groups</strong> on this page (backed by organization team counts).</small></p>
  </section>

  <section class="tenant-section">
    <h2>Related administration</h2>
    <p>Quick links to adjacent admin surfaces (not a full IAM catalog):</p>

    <div class="tenant-links-grid">
      <a class="tenant-link-card">
        <span class="link-icon">♢</span>
        <span><b>Roles &amp; Access</b><small>Manage members, groups, and permissions</small></span>
        <strong>→</strong>
      </a>
      <a class="tenant-link-card">
        <span class="link-icon">▣</span>
        <span><b>Subscription &amp; Billing</b><small>Plans, usage limits, and invoices</small></span>
        <strong>→</strong>
      </a>
      <a class="tenant-link-card">
        <span class="link-icon">⌁</span>
        <span><b>Organization overview</b><small>Operational dashboard and health metrics</small></span>
        <strong>→</strong>
      </a>
    </div>

  </section>

  <section class="tenant-section">
    <h2>Tenant insights</h2>
    <p>Analytics from the admin dashboard. Charts appear once the tenant has deployment and runner activity.</p>

    <div class="tenant-analytics-grid">
      <div class="tenant-chart-card">
        <div class="tenant-chart-header">
          <strong>Deployment activity</strong>
        </div>
        <p>14-day trend: <strong>Successful</strong> vs <strong>Failed</strong> deployment runs.</p>
      </div>

      <div class="tenant-chart-card tenant-donut-card">
        <strong>Tenant footprint</strong>
        <div class="tenant-donut-content">
          <p>Donut of <strong>Members</strong>, <strong>Projects</strong>, and <strong>Groups</strong> counts — people and structure in this organization.</p>
        </div>
      </div>

      <div class="tenant-chart-card">
        <strong>Deployment status</strong>
        <p>Distribution of current deployment outcomes.</p>
      </div>

      <div class="tenant-chart-card">
        <strong>Runner utilization / Runner fleet</strong>
        <p>When dashboard analytics exist: utilization % over time. Otherwise: online runner capacity breakdown.</p>
      </div>
    </div>
    <p><small>Header subtitle includes overall deployment success rate (e.g. “success rate (98.6%)”). There is no “Projects by status” chart on this page.</small></p>
  </section>

  <section class="tenant-section">
    <h2>Organization details</h2>

    <div class="tenant-identity-card">
      <div class="tenant-identity-top">
        <div class="tenant-org-brand">
          <div>
            <div class="tenant-org-name">Editable fields</div>
            <p>Organization name and optional description shown to organization admins.</p>
          </div>
        </div>
        <button class="tenant-outline-button">✎ &nbsp; Edit</button>
      </div>

      <div class="tenant-fields">
        <div class="tenant-field">
          <label>Organization name</label>
          <div class="tenant-copy-field">
            <code>lowercaselettersonly</code>
          </div>
          <small>Lowercase letters only — no spaces, numbers, or special characters. Validated on save.</small>
        </div>

        <div class="tenant-field">
          <label>Description</label>
          <p>Optional multiline summary. Visible to organization admins; <strong>not</strong> shown at sign-in.</p>
        </div>
      </div>

      <div class="tenant-description">
        <p><strong>Save changes</strong> / <strong>Cancel</strong> appear only while editing. Changes are saved when the user confirms the edit.</p>
      </div>
    </div>
  </section>

  <section class="tenant-section">
    <h2>Sign-in credentials</h2>

    <div class="tenant-fields">
      <div class="tenant-field">
        <label>Organization ID (8-character code)</label>
        <div class="tenant-copy-field">
          <code>ABCDEFGH</code>
          <button>▣ &nbsp; Copy</button>
        </div>
        <small>Members enter this ID on the sign-in page together with email and password. Use <strong>Copy</strong> to share with your team.</small>
      </div>

      <div class="tenant-field">
        <label>Internal slug</label>
        <div class="tenant-copy-field">
          <code>abcd-corp</code>
        </div>
        <small>Read-only display. Used internally and in invitations — <strong>not</strong> used at sign-in. No copy button on this field.</small>
      </div>

      <div class="tenant-field">
        <label>Last updated</label>
        <p>Organization record last-modified date.</p>
      </div>
    </div>
  </section>

  <div class="tenant-warning">
    <strong>♧ &nbsp; Safeguards</strong>
    <ul>
      <li>Only holders of <code>org:update</code> may open this page and PATCH organization name and description (OWNER in the default matrix).</li>
      <li>Organization delete requires <code>org:delete</code> (OWNER only) and is not offered on this page.</li>
      <li>Slug and organization ID are not editable here; the 8-character organization ID is allocated at org creation.</li>
      <li>An organization must always retain at least one OWNER.</li>
    </ul>
  </div>

  <div class="tenant-signin-note">
    <span>ⓘ</span>
    <span>Sign-in uses the <strong>Organization ID</strong> (8 characters) from this page or <strong>Organization → Overview</strong>, not the slug. See the repository <code>README.md</code> seed login instructions.</span>
  </div>

</div>


 <nav class="page-navigation cost-page-navigation" aria-label="Documentation navigation">

    <a class="nav-button previous"
       href="{{ '/axio/administration/profile/' | relative_url }}">
       ← Profile
    </a>

    <a class="nav-button next"
       href="{{ '/axio/administration/groups/' | relative_url }}">
       Groups →
    </a>

  </nav>
