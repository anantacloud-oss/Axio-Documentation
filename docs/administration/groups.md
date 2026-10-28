---
layout: default
title: Groups
parent: Administration
nav_order: 4
permalink: /axio/administration/groups/
---

<link rel="stylesheet" href="{{ '/assets/css/groups.css' | relative_url }}">

<div class="admin-groups-page">

  <h1>Administration — Groups</h1>
  <p class="admin-groups-lead">
    Internal Axio groups for collaboration and access, plus read-only groups synchronized from your identity provider.
    These are <strong>not</strong> runner groups — runner fleet groups live under <strong>Runners → Setup</strong>.
  </p>

  <div class="admin-groups-info">
    <span class="info-dot">i</span>
    <span>Open <strong>Administration → Groups</strong> from the Administration navigation.</span>
    <span class="info-separator">•</span>
    <span>Groups are also available in the <strong>Groups</strong> section of <strong>Roles &amp; Access</strong>.</span>
    <span class="info-separator">•</span>
    <span>Assign custom roles to groups from <strong>Roles &amp; Access → Role Assignments</strong></span>
  </div>

  <section class="groups-panel about-groups">
    <h2><span class="panel-icon green-icon">✓</span> Overview banner</h2>
    <p>The page opens with a <strong>Group directory</strong> summary:</p>
    <ul>
      <li>Chips for internal and synced group counts</li>
      <li>Clickable KPIs: <strong>Internal groups</strong>, <strong>Synced groups</strong>, <strong>Total members</strong> (sum of internal group memberships)</li>
      <li><strong>Refresh</strong> reloads teams, synced groups, and permissions</li>
      <li><strong>Identity providers</strong> links to identity provider settings</li>
      <li><strong>Create internal group</strong> (when permitted) opens the create dialog</li>
    </ul>
  </section>

  <div class="groups-tabs">
    <button class="groups-tab active" type="button">
      <span class="tab-icon">♙</span>
      Internal groups
    </button>
    <button class="groups-tab" type="button">
      <span class="tab-icon cloud">☁</span>
      Synced groups
    </button>
  </div>

  <section class="groups-workspace">
    <div class="groups-toolbar">
      <p>Internal groups are stored as organization <strong>teams</strong> in the API. Synced groups come from directory sync.</p>
    </div>

    <h2>Internal groups tab</h2>
    <p>Table columns:</p>

    <div class="table-wrap">
      <table>
        <thead>
          <tr><th>Column</th><th>Content</th></tr>
        </thead>
        <tbody>
          <tr><td><strong>Name</strong></td><td>Clickable — opens a read-only <strong>Group details</strong> dialog with member list</td></tr>
          <tr><td><strong>Description</strong></td><td>Optional group description</td></tr>
          <tr><td><strong>Members</strong></td><td>Member count</td></tr>
          <tr><td><strong>Source</strong></td><td><em>Internal</em> chip</td></tr>
          <tr><td><strong>Actions</strong></td><td>Edit and delete (requires <code>team:manage</code>)</td></tr>
        </tbody>
      </table>
    </div>

    <h2>Synced groups tab</h2>
    <div class="callout callout-info">
      <div class="callout-icon">i</div>
      <p>Synced groups are provisioned from your authentication provider (for example Microsoft Entra ID or SCIM) and <strong>cannot be created, edited, or deleted</strong> in Axio. Manage membership in your IdP or SCIM settings.</p>
    </div>

    <div class="table-wrap">
      <table>
        <thead><tr><th>Column</th><th>Content</th></tr></thead>
        <tbody>
          <tr><td><strong>Name</strong></td><td>Clickable — opens read-only group details with resolved member names/emails</td></tr>
          <tr><td><strong>Source</strong></td><td>Provider label (defaults to <em>Identity Provider</em>)</td></tr>
          <tr><td><strong>External ID</strong></td><td>Directory external identifier</td></tr>
          <tr><td><strong>Members</strong></td><td>Synced member count</td></tr>
          <tr><td><strong>Status</strong></td><td><em>Synced</em> chip</td></tr>
        </tbody>
      </table>
    </div>

  </section>

  <section class="operation-grid">
    <div>
      <h2>Create internal group</h2>
      <ol class="steps">
        <li>Click <strong>Create internal group</strong> in the overview banner.</li>
        <li>Enter <strong>Name</strong> (required) and optional <strong>Description</strong>.</li>
        <li>Confirm to create the group through the organization teams API.</li>
      </ol>
      <p class="note">Requires <code>team:manage</code>.</p>
    </div>

    <div>
      <h2>Edit internal group</h2>
      <ol class="steps">
        <li>Use the pencil icon or <strong>Edit group</strong> from the details dialog.</li>
        <li>Update name and/or description.</li>
        <li>Add members with the <strong>Add internal user</strong> autocomplete (assigns team role <code>MEMBER</code>).</li>
        <li>Remove members with the row delete action.</li>
        <li>Save your changes. Member changes are handled through the group membership controls.</li>
      </ol>
      <p class="note">Only <strong>internal</strong> organization users can be added — not IdP-only synced accounts from this dialog.</p>
    </div>

    <div>
      <h2>Delete internal group</h2>
      <ol class="steps">
        <li>Use the delete icon on a group with <strong>zero members</strong>.</li>
        <li>If members remain, Axio shows <strong>Cannot delete group yet</strong> and offers <strong>Edit group</strong> to remove them first.</li>
        <li>When empty, type <code>DELETE</code> or the exact group name to confirm.</li>
      </ol>
      <p class="note">The API also rejects deletion while members exist.</p>
    </div>
  </section>

  <section>
    <h2>Permissions</h2>
    <div class="table-wrap">
      <table>
        <thead><tr><th>Action</th><th>Permission</th></tr></thead>
        <tbody>
          <tr><td>Open Groups page</td><td><code>team:manage</code></td></tr>
          <tr><td>Create / edit / delete internal groups; manage members</td><td><code>team:manage</code></td></tr>
          <tr><td>List teams / view synced groups (API)</td><td><code>org:read</code> (broader org read for API list endpoints)</td></tr>
          <tr><td>Assign roles to groups</td><td><code>role:manage</code> on <strong>Roles &amp; Access → Role Assignments</strong></td></tr>
        </tbody>
      </table>
    </div>
  </section>

  <section>
    <h2>Using groups for access</h2>
    <ul>
      <li>On <strong>Role Assignments</strong>, choose principal type <strong>Group</strong> and pick an internal team or synced SCIM group.</li>
      <li>Assignments can be scoped to organization, project, workspace, or environment (same as user assignments).</li>
      <li>When group membership changes, effective access updates for users who receive permissions through that group assignment.</li>
      <li>Internal group membership here is separate from organization membership role (Owner / Admin / Member / Viewer).</li>
    </ul>
  </section>

  <div class="groups-bottom">
    <section class="groups-panel about-groups">
      <h2><span class="panel-icon green-icon">✓</span> About groups</h2>
      <ul>
        <li>Groups organize users for collaboration and simplify RBAC assignments.</li>
        <li>Assign custom roles to internal or synced groups from <strong>Roles &amp; Access → Role Assignments</strong>.</li>
        <li>Changes to internal group membership affect access where that group is assigned a role.</li>
        <li>Legacy group and team pages redirect to the Administration Groups page.</li>
      </ul>
      <div class="panel-note green-note">
        <span class="panel-note-icon">ⓘ</span>
        <p>
            Groups are listed under <strong>Administration</strong>, not under
            Organization resource navigation. Do not confuse with
            <strong>runner groups</strong> on the Runners page.
        </p>
    </div>
    </section>

    <section class="groups-panel about-tabs">
      <h2><span class="panel-icon orange-icon">i</span> About the tabs</h2>
      <div class="tab-explanation">
        <div class="explain-icon internal-icon">♧</div>
        <div><strong>Internal groups:</strong> Created and managed in Axio — rename, delete (when empty), and add/remove internal user members.</div>
      </div>
      <div class="tab-explanation synced-explanation">
        <div class="explain-icon synced-icon">☁</div>
        <div><strong>Synced groups:</strong> Read-only directory groups from SSO / SCIM. View members in Axio; manage the group in your identity provider.</div>
      </div>
    </section>
  </div>

</div>



 <nav class="page-navigation cost-page-navigation" aria-label="Documentation navigation">

    <a class="nav-button previous"
       href="{{ '/axio/administration/tenant/' | relative_url }}">
       ← Tenant
    </a>

    <a class="nav-button next"
       href="{{ '/axio/administration/role-and-access/overview/' | relative_url }}">
       Role & Access Overview →
    </a>

  </nav>
