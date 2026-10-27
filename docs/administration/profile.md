---
layout: default
title: My Profile
parent: Administration
nav_order: 1
permalink: /axio/administration/profile/
---

<link rel="stylesheet" href="{{ '/assets/css/profile.css' | relative_url }}">


<div class="profile-page">

<h1>Administration — My Profile</h1>

<p class="profile-subtitle">
  Personal account settings for the signed-in user — not organization administration (Users, Groups, Roles, or organization-wide MFA policy).
</p>

<div class="profile-banner">
  <span>ⓘ</span>
  <div>
    Open from the <strong>user account menu</strong> (avatar / name) → <strong>My profile</strong>.
    Organization-wide MFA policy is managed separately by administrators.
  </div>
</div>

<h2>What it does</h2>

<p>The signed-in user can manage their own account:</p>

<div class="profile-features">
  <div>
    <b>♙</b>
    <h3>Edit profile</h3>
    <p>Update first name, last name, and profile picture URL; email is read-only.</p>
  </div>

  <div>
    <b>✉</b>
    <h3>Email verification</h3>
    <p>See verification status and resend the verification email.</p>
  </div>

  <div>
    <b>♢</b>
    <h3>MFA enrollment</h3>
    <p>Enroll with Google or Microsoft Authenticator (TOTP), view status, and regenerate recovery codes.</p>
  </div>

  <div>
    <b>▣</b>
    <h3>Active sessions</h3>
    <p>Review signed-in devices; revoke one session, sign out other devices, or sign out everywhere.</p>
  </div>

  <div>
    <b>⌁</b>
    <h3>Activity &amp; insights</h3>
    <p>Charts for sign-in trends, security posture, sessions, and API-key activity, plus a recent sign-in list.</p>
  </div>

  <div>
    <b>⚿</b>
    <h3>Security recommendations</h3>
    <p>Personal recommendations, such as verifying email, enabling MFA, and regenerating recovery codes.</p>
  </div>
</div>

<h2>How to access</h2>

<p>
  <strong>My Profile</strong> is categorized as <strong>Account</strong> in navigation and is opened from the top-bar <strong>user account menu</strong>, not from the Administration sidebar.
  Any authenticated organization member can open the page.
</p>

<h2>Prerequisites &amp; permissions</h2>

<div class="profile-table">
  <div class="profile-head">
    <b>Requirement</b>
    <b>Detail</b>
  </div>

  <div>
    <strong>Sign-in</strong>
    <span>Must be authenticated. Unauthenticated users are redirected to login.</span>
  </div>

  <div>
    <strong>Organization context</strong>
    <span>MFA status and audit activity are scoped to the <strong>current organization</strong>.</span>
  </div>

  <div>
    <strong>Permissions</strong>
    <span>No special administrator permission is required to access this page, unlike pages for user management or organization-wide MFA policy.</span>
  </div>
</div>

<p class="profile-subtitle">
  Password changes are not performed on this page — use your identity provider or contact an organization administrator.
  <strong>Notification preferences</strong> are managed separately.
</p>

<h2>Sections</h2>

<div class="profile-table">
  <div class="profile-head">
    <b>Section</b>
    <b>Content</b>
  </div>

  <div>
    <strong>Overview</strong>
    <span>Signed-in account summary (name, email, organization role, and organization name), operational alerts, clickable KPIs, and Refresh.</span>
  </div>

  <div>
    <strong>Personal Information</strong>
    <span>First name, last name, and profile picture URL.</span>
  </div>

  <div>
    <strong>Account Security</strong>
    <span>Email verification status and the option to resend the verification email.</span>
  </div>

  <div>
    <strong>Multi-Factor Authentication</strong>
    <span>TOTP enrollment using Google or Microsoft Authenticator and recovery codes.</span>
  </div>

  <div>
    <strong>Active sessions</strong>
    <span>List sessions, revoke a session, sign out other devices, or sign out everywhere.</span>
  </div>

  <div>
    <strong>Activity &amp; insights</strong>
    <span>Account activity trends (7, 30, or 90 days), security posture, sessions and API activity, API key activity, top actions, and recent sign-ins from organization audit logs.</span>
  </div>

  <div>
    <strong>Security recommendations</strong>
    <span>Actionable personal security recommendations when applicable.</span>
  </div>
</div>

<div class="profile-panel">

  <div class="panel-title">
    <strong>Overview — Signed-in account</strong>
  </div>

  <p class="profile-subtitle">
    Shows the user's avatar, full name, email, organization role, organization name, email verification status, and MFA status.
  </p>

  <div class="profile-table">
    <div class="profile-head">
      <b>KPI</b>
      <b>Destination</b>
    </div>

    <div>
      <strong>Last Login</strong>
      <span>Activity &amp; insights / recent sign-ins.</span>
    </div>

    <div>
      <strong>MFA Status</strong>
      <span>Multi-Factor Authentication section.</span>
    </div>

    <div>
      <strong>Recovery Codes</strong>
      <span>Multi-Factor Authentication section.</span>
    </div>

    <div>
      <strong>Active Sessions</strong>
      <span>Active sessions table, with a brief highlight.</span>
    </div>
  </div>

  <p class="profile-subtitle">
    Operational alerts appear when email is unverified, MFA is disabled, or recovery codes are running low.
  </p>

</div>

<div class="profile-panel">

  <div class="panel-title">
    <strong>♙　Personal Information</strong>
  </div>

  <div class="profile-form">

    <label>
      Email address
      <div>
        <input value="(read-only — from sign-in account)" readonly>
      </div>
    </label>

    <label>
      First name
      <input placeholder="First name" readonly>
    </label>

    <label>
      Last name
      <input placeholder="Last name" readonly>
    </label>

    <label>
      Profile picture URL
      <div class="avatar-row">
        <i>—</i>
        <input placeholder="https://example.com/avatar.png" readonly>
      </div>
      <small>
        Optional image URL used for the user's avatar. A live preview appears above the form.
      </small>
    </label>

  </div>

  <div class="actions">
    <button class="primary" type="button">Save changes</button>
  </div>

</div>

<div class="profile-panel compact">
  <div class="panel-title">
    <strong>♢　Account Security</strong>
  </div>
</div>

<p class="profile-subtitle">
  When email is not verified, the page explains that the user can use the sign-up verification link or complete email verification through MFA enrollment.
  A note links to <strong>Notification preferences</strong> for alert settings — not API key management.
</p>

<div class="profile-panel compact">
  <div class="panel-title">
    <strong>▣　Multi-Factor Authentication</strong>
  </div>
</div>

<p class="profile-subtitle">
  Enrollment supports <strong>Google Authenticator</strong> and <strong>Microsoft Authenticator</strong> (TOTP): QR code or manual setup key, verification code, then one-time recovery codes.
  When MFA is enabled, users can regenerate recovery codes with their current MFA code.
  If the organization enforces MFA, an information banner explains that administrators manage the policy.
  When MFA is enabled without organization enforcement, users may see guidance to contact an administrator to disable MFA.
</p>

<div class="profile-panel">

  <div class="panel-title">
    <strong>▣　Active sessions</strong>
  </div>

  <div class="sessions">

    <div class="session-head">
      <b>Device</b>
      <b>Location</b>
      <b>IP address</b>
      <b>Last seen</b>
      <b>Signed in</b>
      <b>Actions</b>
    </div>

    <div>
      <strong>Browser on OS</strong>
      <small>This device</small>
      <span>City, Country</span>
      <span>—</span>
      <span>—</span>
      <span>—</span>
      <span>—</span>
    </div>

    <div>
      <strong>Other device</strong>
      <small>—</small>
      <span>City, Country</span>
      <span>—</span>
      <span>—</span>
      <span>—</span>
      <button class="revoke" type="button">Revoke</button>
    </div>

  </div>

  <div class="session-actions">
    <button class="revoke" type="button">Sign out other devices</button>
    <button class="revoke" type="button">Sign out everywhere</button>
  </div>

  <p class="profile-subtitle">
    <strong>Sign out other devices</strong> keeps the current browser signed in.
    <strong>Sign out everywhere</strong> revokes all sessions, including the current one, and returns the user to the sign-in page.
    The current session shows a <em>This device</em> chip instead of a Revoke button.
  </p>

</div>

<div class="profile-panel compact">
  <div class="panel-title">
    <strong>Activity &amp; insights</strong>
    <small>Personal sign-in trends, security posture, and platform activity</small>
  </div>
</div>

<div class="profile-table">

  <div class="profile-head">
    <b>Chart</b>
    <b>Description</b>
  </div>

  <div>
    <strong>Account activity</strong>
    <span>All events, sign-ins, and security events over 7, 30, or 90 days, based on organization audit logs for the current organization.</span>
  </div>

  <div>
    <strong>Security posture</strong>
    <span>Email, MFA, and recovery-code status distribution.</span>
  </div>

  <div>
    <strong>Sessions &amp; API activity</strong>
    <span>Authentication sessions and API token usage trends.</span>
  </div>

  <div>
    <strong>API key activity</strong>
    <span>Active, rotated, and expired keys (organization dashboard summary — keys are not created on this page).</span>
  </div>

  <div>
    <strong>Top actions</strong>
    <span>Most frequent account-related audit events.</span>
  </div>

  <div>
    <strong>Recent sign-ins</strong>
    <span>Latest authentication events derived from audit logs.</span>
  </div>

</div>

</div>


 <nav class="page-navigation cost-page-navigation" aria-label="Documentation navigation">

    <a class="nav-button previous"
       href="{{ '/axio/ai/mcp-servers/' | relative_url }}">
       ← AI MCP Servers
    </a>

    <a class="nav-button next"
       href="{{ '/axio/administration/tenant/' | relative_url }}">
       Tenant →
    </a>

  </nav>
