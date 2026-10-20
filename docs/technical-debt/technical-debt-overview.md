\---

layout: default

nav\_order: 4

parent: Operations

title: Technical Debt

permalink: /axio/operations/technical-debt/

\---





@import url("./technical-debt-overview.css");



<div class="td-page">

&#x20; <nav class="td-breadcrumb" aria-label="Breadcrumb">

&#x20;   <span>⌂</span><span>/</span><span>Docs</span><span>/</span><span>Features</span><span>/</span><strong>Technical Debt</strong><span>/</span><span>Overview</span>

&#x20; </nav>



&#x20; <header class="td-page-header">

&#x20;   <h1>Technical Debt</h1>

&#x20;   <p class="td-subtitle">Foundation, operating model \&amp; backlog</p>

&#x20;   <p class="td-intro">Technical Debt helps you identify, prioritize and remediate infrastructure and code issues across your environment. It consolidates findings from multiple sources such as cloud, security, policy, drift, cost and compliance into a single backlog with clear ownership and lifecycle.</p>

&#x20; </header>



&#x20; <section class="td-metrics" aria-label="Technical debt summary">

&#x20;   <article class="td-metric td-blue">

&#x20;     <div class="td-metric-icon">▤</div><div><p>Total Debt Items</p><strong>248</strong><span class="td-change td-good">↓ 12%</span><small>vs previous period</small></div>

&#x20;   </article>

&#x20;   <article class="td-metric td-red">

&#x20;     <div class="td-metric-icon">⚠</div><div><p>Critical \&amp; High</p><strong>76</strong><span class="td-change td-bad">↑ 8%</span><small>vs previous period</small></div>

&#x20;   </article>

&#x20;   <article class="td-metric td-purple">

&#x20;     <div class="td-metric-icon">◷</div><div><p>Overdue (SLA)</p><strong>32</strong><span class="td-change td-bad">↑ 6%</span><small>vs previous period</small></div>

&#x20;   </article>

&#x20;   <article class="td-metric td-green">

&#x20;     <div class="td-metric-icon">✓</div><div><p>Resolved (last 30 days)</p><strong>54</strong><span class="td-change td-good">↑ 24%</span><small>vs previous period</small></div>

&#x20;   </article>

&#x20; </section>



&#x20; <div class="td-main-grid">

&#x20;   <div class="td-column">

&#x20;     <section class="td-section">

&#x20;       <h2>What is Technical Debt?</h2>

&#x20;       <p>Technical Debt refers to known issues, risks or improvement opportunities in your infrastructure and code that can lead to higher cost, security risks, operational issues or reduced reliability over time. Axio automatically collects, normalizes and tracks these items from multiple sources and provides tools to prioritize, remediate and govern them.</p>

&#x20;     </section>



&#x20;     <section class="td-panel td-capabilities">

&#x20;       <h2>Key capabilities</h2>

&#x20;       <div class="td-capability"><span class="td-small-icon">☷</span><div><strong>Multi-source ingestion</strong><p>Security, policy, drift, cost, compliance and cloud lifecycle</p></div></div>

&#x20;       <div class="td-capability"><span class="td-small-icon">▣</span><div><strong>Unified backlog</strong><p>Consolidated view with filtering, ownership and SLA</p></div></div>

&#x20;       <div class="td-capability"><span class="td-small-icon">♟</span><div><strong>Prioritization</strong><p>Explainable scoring with financial and technical impact</p></div></div>

&#x20;       <div class="td-capability"><span class="td-small-icon">⚒</span><div><strong>Remediation workflows</strong><p>Automated and manual remediation with verification</p></div></div>

&#x20;       <div class="td-capability"><span class="td-small-icon">⬟</span><div><strong>Governance</strong><p>SLA, ownership, escalation and exceptions</p></div></div>

&#x20;       <div class="td-capability"><span class="td-small-icon">▥</span><div><strong>Trends \&amp; executive insights</strong><p>Historical analytics and reports for different audiences</p></div></div>

&#x20;     </section>

&#x20;   </div>



&#x20;   <div class="td-column">

&#x20;     <section class="td-panel td-architecture" aria-label="Technical debt data flow">

&#x20;       <div class="td-source-grid">

&#x20;         <div class="td-source"><span>☁</span><strong>Cloud</strong><small>AWS, Azure,<br>GCP</small></div>

&#x20;         <div class="td-source"><span>⬟</span><strong>Security</strong><small>Findings \&amp;<br>vulnerabilities</small></div>

&#x20;         <div class="td-source"><span>▤</span><strong>Policy</strong><small>Violations</small></div>

&#x20;         <div class="td-source"><span>ϟ</span><strong>Drift</strong><small>Configuration<br>drift</small></div>

&#x20;         <div class="td-source"><span>▤</span><strong>Cost</strong><small>Billing<br>recommendations</small></div>

&#x20;         <div class="td-source"><span>✓</span><strong>Compliance</strong><small>Control failures</small></div>

&#x20;       </div>

&#x20;       <div class="td-flow-line">↓ \&nbsp; ↓ \&nbsp; ↓ \&nbsp; ↓ \&nbsp; ↓ \&nbsp; ↓</div>

&#x20;       <div class="td-axio-node"><span class="td-axio-mark">A</span><div><strong>Axio</strong><small>Technical Debt</small></div></div>

&#x20;       <div class="td-down-line">↓ \&nbsp;\&nbsp;\&nbsp;\&nbsp;\&nbsp;\&nbsp;\&nbsp;\&nbsp; ↓ \&nbsp;\&nbsp;\&nbsp;\&nbsp;\&nbsp;\&nbsp;\&nbsp;\&nbsp; ↓ \&nbsp;\&nbsp;\&nbsp;\&nbsp;\&nbsp;\&nbsp;\&nbsp;\&nbsp; ↓</div>

&#x20;       <div class="td-output-grid">

&#x20;         <div><span>☷</span><strong>Backlog</strong><small>Unified inventory</small></div>

&#x20;         <div><span>▥</span><strong>Prioritization</strong><small>Risk \&amp; impact</small></div>

&#x20;         <div><span>⚙</span><strong>Remediation</strong><small>Automated workflows</small></div>

&#x20;         <div><span>⬟</span><strong>Governance</strong><small>SLA \&amp; ownership</small></div>

&#x20;       </div>

&#x20;     </section>



&#x20;     <section class="td-section td-how">

&#x20;       <h2>How it works</h2>

&#x20;       <div class="td-steps">

&#x20;         <div><span>1</span><strong>Ingest findings</strong><small>Collect data from integrated sources.</small></div>

&#x20;         <div><span>2</span><strong>Reconcile \&amp; normalize</strong><small>Create canonical debt items with metadata.</small></div>

&#x20;         <div><span>3</span><strong>Prioritize</strong><small>Calculate priority score and SLA.</small></div>

&#x20;         <div><span>4</span><strong>Remediate</strong><small>Execute automated or manual actions.</small></div>

&#x20;         <div><span>5</span><strong>Verify \&amp; close</strong><small>Confirm resolution with source evidence.</small></div>

&#x20;       </div>

&#x20;     </section>



&#x20;     <section class="td-section td-source-types">

&#x20;       <h2>Supported source types (Phase 1)</h2>

&#x20;       <div class="td-table-wrap">

&#x20;         <table>

&#x20;           <thead><tr><th>Source type</th><th>Description</th></tr></thead>

&#x20;           <tbody>

&#x20;             <tr><td><code>SECURITY\_FINDING</code></td><td>Findings from security scanners (e.g. Security Hub, code scanning)</td></tr>

&#x20;             <tr><td><code>POLICY\_VIOLATION</code></td><td>Violations from policy as code and compliance checks</td></tr>

&#x20;             <tr><td><code>DRIFT\_CHECK</code></td><td>Infrastructure drift findings</td></tr>

&#x20;             <tr><td><code>CLOUD\_BILLING\_RECOMMENDATION</code></td><td>Cost and rightsizing recommendations</td></tr>

&#x20;             <tr><td><code>COMPLIANCE\_CONTROL</code></td><td>Failed compliance controls</td></tr>

&#x20;             <tr><td><code>COST\_ANOMALY</code></td><td>Detected cost anomalies</td></tr>

&#x20;           </tbody>

&#x20;         </table>

&#x20;       </div>

&#x20;     </section>

&#x20;   </div>

&#x20; </div>

</div>



