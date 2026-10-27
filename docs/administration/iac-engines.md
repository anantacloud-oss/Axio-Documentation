---
layout: default
title: IaC Engines
parent: Administration
nav_order: 10
permalink: /axio/administration/iac-engines/
---

<link rel="stylesheet" href="{{ '/assets/css/iac-engines.css' | relative_url }}">

<div class="iac-engines-page">

 <main class="iac-main">

 <header class="iac-hero">
 <h1>Administration — IaC Engines</h1>
 <p>Govern infrastructure-as-code engines, version lifecycles, runtime images, and deployment compatibility across your organization.</p>
 </header>

 <div class="iac-info">
 <span class="info-icon">i</span>
 <span>
 Open <strong>Administration → IaC Engines</strong>
 </span>
 </div>

 <section>
 <h2>Permissions</h2>
 <div class="table-wrap">
 <table>
 <thead>
 <tr><th>Action</th><th>Permission</th></tr>
 </thead>
 <tbody>
 <tr><td>View hub, engine directory, version inventory, runtime images, insights</td><td><code>iac:engine:admin</code></td></tr>
 <tr><td>Add/edit/deprecate/delete versions, set default, runtime image policy</td><td><code>iac:engine:admin</code></td></tr>
 </tbody>
 </table>
 </div>
 <p class="note">Members without <code>iac:engine:admin</code> cannot open this page. Version tables show <em>Read only</em> when manage permission is absent after load.</p>
 </section>

 <section class="iac-shell">

 <h2>Engine governance overview</h2>
 <p>Top summary shows live metrics from the org catalog and dashboard — not fixed counts. Includes platform default engine chip, operational alerts, and <strong>Refresh</strong>.</p>

 <div class="iac-stats">
 <div class="stat-card">
 <div class="stat-icon purple">◇</div>
 <div><span>Catalog engines</span><small>Engines in the organization catalog</small></div>
 </div>
 <div class="stat-card">
 <div class="stat-icon green">✓</div>
 <div><span>Engines in use</span><small>From org dashboard (<code>iacEnginesInUse</code>)</small></div>
 </div>
 <div class="stat-card">
 <div class="stat-icon blue">▱</div>
 <div><span>Managed stacks</span><small>Total stacks in the organization</small></div>
 </div>
 <div class="stat-card">
 <div class="stat-icon orange">!</div>
 <div><span>Needs attention</span><small>Missing versions, deprecated default, or no supported versions</small></div>
 </div>
 </div>

 <p class="note">Click a metric to filter or navigate (for example <em>Needs attention</em> opens Engine Directory with the <em>Needs attention</em> filter). An info banner links to the <strong>Runtime Images</strong> tab for image policy and registry setup.</p>


 <div class="iac-section-heading">
 <div>
 <h2>Engine Directory</h2>
 <p>Table view — search, filter, sort, and open engines. There is <strong>no Add engine</strong> action; the platform catalog includes six engine types. You add and manage <strong>versions</strong> per engine.</p>
 </div>
 <div class="iac-heading-actions">
 <p><strong>Search</strong> — engine name, slug, type, default version</p>
 <p><strong>Filter</strong> — All engines · Needs attention · Has deprecated versions · In use by stacks</p>
 <p><strong>Sort</strong> — Name · Configuration status · Stacks in use</p>
 </div>
 </div>

 <div class="table-wrap">
 <table>
 <thead>
 <tr>
 <th>Column</th><th>Description</th>
 </tr>
 </thead>
 <tbody>
 <tr><td>Engine</td><td>Name, slug, logo</td></tr>
 <tr><td>Configuration</td><td><em>Not Configured</em>, <em>Warning</em>, or <em>Configured</em></td></tr>
 <tr><td>Default version</td><td>Organization default for new stacks</td></tr>
 <tr><td>Supported</td><td>Count of <code>SUPPORTED</code> versions / total versions</td></tr>
 <tr><td>Deprecated</td><td>Count of deprecated, end-of-support, or archived versions</td></tr>
 <tr><td>Stacks in use</td><td>Active stacks on this engine</td></tr>
 <tr><td>Actions</td><td><strong>Open</strong> (engine detail) · <strong>Versions</strong></td></tr>
 </tbody>
 </table>
 </div>

 <h3>Supported catalog engines</h3>
 <p>Six engine types are seeded per organization. Slugs and versions are provided by the engine catalog.</p>

 <div class="engine-grid">

 <article class="engine-card">
 <div class="engine-head">
 <div class="engine-logo terraform">◆</div>
 <div><h3>Terraform <code>terraform</code></h3></div>
 </div>
 <p>HashiCorp Terraform — declarative infrastructure provisioning with plan/apply lifecycle.</p>
 </article>

 <article class="engine-card">
 <div class="engine-head">
 <div class="engine-logo opentofu">◆</div>
 <div><h3>OpenTofu <code>opentofu</code></h3></div>
 </div>
 <p>Open-source Terraform fork with community-driven governance.</p>
 </article>

 <article class="engine-card">
 <div class="engine-head">
 <div class="engine-logo pulumi">●</div>
 <div><h3>Pulumi <code>pulumi</code></h3></div>
 </div>
 <p>Modern infrastructure as code using familiar programming languages.</p>
 </article>

 <article class="engine-card">
 <div class="engine-head">
 <div class="engine-logo crossplane">☁</div>
 <div><h3>Crossplane <code>crossplane</code></h3></div>
 </div>
 <p>Kubernetes-native control plane for cloud infrastructure.</p>
 </article>

 <article class="engine-card">
 <div class="engine-head">
 <div class="engine-logo cloudformation">▣</div>
 <div><h3>CloudFormation <code>cloudformation</code></h3></div>
 </div>
 <p>AWS-native infrastructure provisioning with stack sets and change sets.</p>
 </article>

 <article class="engine-card">
 <div class="engine-head">
 <div class="engine-logo bicep">&lt;&gt;</div>
 <div><h3>Azure ARM / Bicep <code>arm-bicep</code></h3></div>
 </div>
 <p>Azure Resource Manager and Bicep templates for Azure infrastructure.</p>
 </article>

 </div>

 <h2>Version Inventory</h2>
 <p>Organization-wide table of all engine versions. Filter by engine, lifecycle status, and search. Columns: Engine, Version, Lifecycle, Default, Support ends, Stacks, Manage (opens engine versions tab).</p>
 <p><strong>Lifecycle statuses</strong>: <code>SUPPORTED</code>, <code>DEPRECATED</code>, <code>END_OF_SUPPORT</code>, <code>ARCHIVED</code>. Insights charts may also bucket versions as Default / LTS / Supported / Deprecated for analytics.</p>

 <h2>Runtime Images</h2>
 <p>Organization policy and per-engine mappings:</p>
 <ul>
 <li><strong>Runtime image policy</strong> — allow Public, Axio standard, and/or Custom images; set default source (<code>PUBLIC</code>, <code>AXIO</code>, or <code>CUSTOM</code>)</li>
 <li><strong>Per-engine table</strong> — version count and default version</li>
 <li><strong>Custom images</strong> — map overrides per version when custom images are enabled; requires container registries under Integrations</li>
 </ul>
 <p>Runners use catalog default images (public or Axio) unless custom policy overrides apply.</p>

 <h2>Insights</h2>
 <p>Adoption trends, deployment health, and lifecycle recommendations:</p>
 <ul>
 <li>Engine adoption, version distribution, deployment distribution charts</li>
 <li>Engine adoption trend (7d / 30d / 90d range toggle)</li>
 <li>Execution KPIs — executions, success rate, average runtime, failed runs</li>
 <li>Lifecycle recommendations (for example upgrade deprecated defaults)</li>
 </ul>

 <div class="iac-bottom-grid">
 <div class="lifecycle-card">
 <div class="bottom-icon">♢</div>
 <div>
 <h3>Version lifecycle</h3>
 <ul>
 <li><b>Supported:</b> Recommended for production; status <code>SUPPORTED</code></li>
 <li><b>Default:</b> Version used for newly created stacks (<code>isDefault</code> flag)</li>
 <li><b>Deprecated:</b> Available but not recommended; includes <code>DEPRECATED</code>, <code>END_OF_SUPPORT</code>, <code>ARCHIVED</code></li>
 <li><b>Deprecation flow:</b> Set replacement version, support end date, and message; banner shown when default is deprecated</li>
 </ul>
 <p class="note">Changing defaults affects <strong>new stacks only</strong> — existing stack executions keep their pinned version.</p>
 </div>
 </div>

 <div class="runtime-card">
 <div class="bottom-icon">◇</div>
 <div>
 <h3>Engine detail page</h3>
 <p>Open any engine at with tabs:</p>
 <ul>
 <li><strong>Overview</strong> — latest, default, installed counts, status summary</li>
 <li><strong>Versions</strong> — search/filter; <strong>Add Version</strong>, Edit, Set Default, Deprecate, Delete</li>
 <li><strong>Deprecation</strong> — deprecated version cards with replacement guidance</li>
 <li><strong>Runtime Images</strong> — public/Axio images per version; custom image overrides</li>
 <li><strong>Compatibility</strong> — platform, Kubernetes, plugin compatibility matrix</li>
 <li><strong>Settings</strong> — slug, type, description metadata</li>
 <li><strong>Audit History</strong> — engine-scoped audit events</li>
 </ul>
 </div>
 </div>
 </div>

 </section>

 </main>
</div>


<nav class="page-navigation cost-page-navigation" aria-label="Documentation navigation">

    <a class="nav-button previous"
       href="{{ '/axio/administration/audit-logs/' | relative_url }}">
       ← Audit Logs
    </a>

</nav>
