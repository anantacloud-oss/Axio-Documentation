---
title: Technical Debt — Lifecycle Intelligence
layout: default
parent: Technical Debt
nav_order: 8
permalink: /axio/operations/technical-debt/technical-debt-lifecycle/ 
---

<link rel="stylesheet" href="{{ '/assets/css/technical-debt-lifecycle-intelligence.css' | relative_url }}">


<div class="td-life-page">
  
  <header class="td-life-header">
    <h1>Technical Debt — Lifecycle Intelligence</h1>
    <p class="td-life-subtitle">Track end-of-life, version risks and upgrade opportunities</p>
    <p>Phase 5 provides lifecycle intelligence for cloud and code components. It helps you identify end-of-life (EOL) dates, unsupported versions and upgrade recommendations to reduce security and operational risk.</p>
  </header>

  <section class="td-life-metrics" aria-label="Lifecycle metrics">
    <article class="td-life-metric td-life-red">
      <span class="td-life-metric-icon">⚠</span>
      <div><p>EOL / End of Support</p><strong>28</strong><span class="td-life-change td-life-bad">↑ 24%</span><small>vs previous period</small></div>
    </article>
    <article class="td-life-metric td-life-blue">
      <span class="td-life-metric-icon">▤</span>
      <div><p>Outdated Versions</p><strong>96</strong><span class="td-life-change td-life-bad">↑ 12%</span><small>vs previous period</small></div>
    </article>
    <article class="td-life-metric td-life-purple">
      <span class="td-life-metric-icon">▦</span>
      <div><p>Upgrade Opportunities</p><strong>134</strong><span class="td-life-change td-life-good">↓ 18%</span><small>vs previous period</small></div>
    </article>
    <article class="td-life-metric td-life-green">
      <span class="td-life-metric-icon">✓</span>
      <div><p>Supported &amp; Up to Date</p><strong>312</strong><span class="td-life-change td-life-good">↓ 26%</span><small>vs previous period</small></div>
    </article>
  </section>

  <div class="td-life-layout">
    <div class="td-life-left">
      <section class="td-life-section">
        <h2>Component lifecycle overview</h2>
        <p>View lifecycle status for cloud services, runtimes, libraries and frameworks.</p>
        <div class="td-life-table-wrap">
          <table class="td-life-table">
            <thead><tr><th>Component</th><th>Type</th><th>Current Version</th><th>Latest Version</th><th>EOL Date</th><th>Status</th><th>Recommendation</th></tr></thead>
            <tbody>
              <tr><td>Amazon EKS</td><td>Cloud Service</td><td>1.27</td><td>1.29</td><td>Dec 31, 2025</td><td><span class="td-life-status td-life-soon">EOL Soon</span></td><td>Upgrade to 1.29</td></tr>
              <tr><td>Node.js</td><td>Runtime</td><td>16.x</td><td>20.x</td><td>Sep 11, 2023</td><td><span class="td-life-status td-life-eol">EOL</span></td><td>Upgrade to 20.x</td></tr>
              <tr><td>Python</td><td>Runtime</td><td>3.8</td><td>3.12</td><td>Oct 7, 2024</td><td><span class="td-life-status td-life-eol">EOL</span></td><td>Upgrade to 3.12</td></tr>
              <tr><td>OpenSSL</td><td>Library</td><td>1.1.1</td><td>3.0.12</td><td>Sep 11, 2023</td><td><span class="td-life-status td-life-eol">EOL</span></td><td>Upgrade to 3.0.x</td></tr>
              <tr><td>PostgreSQL</td><td>Database</td><td>12</td><td>16</td><td>Nov 9, 2023</td><td><span class="td-life-status td-life-eol">EOL</span></td><td>Upgrade to 16</td></tr>
              <tr><td>nginx</td><td>Application</td><td>1.20</td><td>1.26</td><td>Apr 11, 2024</td><td><span class="td-life-status td-life-soon">EOL Soon</span></td><td>Upgrade to 1.26</td></tr>
            </tbody>
          </table>
        </div>
      </section>

      <section class="td-life-section td-life-sources">
        <h2>Supported sources</h2>
        <p>We collect lifecycle data from multiple providers to give a unified view.</p>
        <div class="td-life-source-grid">
          <article class="td-life-source"><span>☁</span><strong>AWS</strong><p>Service lifecycle and version support dates</p></article>
          <article class="td-life-source"><span>◉</span><strong>GitHub</strong><p>Dependency and runtime versions</p></article>
          <article class="td-life-source"><span>▰</span><strong>Package Registries</strong><p>Library and framework EOL information</p></article>
          <article class="td-life-source"><span>▤</span><strong>Public Databases</strong><p>Community and vendor EOL data (e.g. endoflife.date)</p></article>
        </div>
      </section>

     </div>

    <div class="td-life-right">
      <section class="td-life-timeline-card">
        <h2>EOL timeline</h2>
        <p>Upcoming end-of-life dates for your components.</p>
        <div class="td-life-timeline">
          <div class="td-life-timeline-item td-life-timeline-red"><span class="td-life-timeline-dot"></span><strong>Sep 2023</strong><p>Node.js 16.x</p><b>EOL</b></div>
          <div class="td-life-timeline-item td-life-timeline-red"><span class="td-life-timeline-dot"></span><strong>Nov 2023</strong><p>PostgreSQL 12</p><b>EOL</b></div>
          <div class="td-life-timeline-item td-life-timeline-amber"><span class="td-life-timeline-dot"></span><strong>Apr 2024</strong><p>nginx 1.20</p><b>EOL Soon</b></div>
          <div class="td-life-timeline-item td-life-timeline-amber"><span class="td-life-timeline-dot"></span><strong>Oct 2024</strong><p>Python 3.8</p><b>EOL Soon</b></div>
          <div class="td-life-timeline-item td-life-timeline-blue"><span class="td-life-timeline-dot"></span><strong>Dec 2025</strong><p>EKS 1.27</p><b>EOL Soon</b></div>
        </div>
      </section>

      <section class="td-life-chart-card">
        <h2>Lifecycle status distribution</h2>
        <div class="td-life-chart-layout">
          <div class="td-life-donut" role="img" aria-label="570 total components: 28 EOL, 72 EOL soon, 96 outdated, 312 supported, 62 unknown">
            <div><strong>570</strong><span>Components</span></div>
          </div>
          <ul class="td-life-legend">
            <li><span class="td-life-dot td-life-dot-red"></span><span>EOL</span><strong>28 (5%)</strong></li>
            <li><span class="td-life-dot td-life-dot-amber"></span><span>EOL Soon</span><strong>72 (13%)</strong></li>
            <li><span class="td-life-dot td-life-dot-blue"></span><span>Outdated</span><strong>96 (17%)</strong></li>
            <li><span class="td-life-dot td-life-dot-green"></span><span>Supported</span><strong>312 (55%)</strong></li>
            <li><span class="td-life-dot td-life-dot-purple"></span><span>Unknown</span><strong>62 (11%)</strong></li>
          </ul>
        </div>
      </section>

      <section class="td-life-benefits">
        <h2><span>✓</span> Benefits</h2>
        <ul>
          <li>Proactive identification of end-of-life components</li>
          <li>Reduced security and operational risk</li>
          <li>Clear upgrade recommendations with timelines</li>
          <li>Unified view across cloud and code</li>
          <li>Better planning for maintenance and migration</li>
          <li>Improved compliance and audit readiness</li>
        </ul>
      </section>
    </div>
  </div>
</div>
