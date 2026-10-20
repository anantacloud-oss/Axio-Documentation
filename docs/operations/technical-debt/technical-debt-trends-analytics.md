---
title: Technical Debt — Trends & Historical Analytics
layout: default
parent: Technical Debt
nav_order: 3
permalink: /axio/operations/technical-debt/technical-debt-trends/
---


<link rel="stylesheet" href="{{ '/assets/css/technical-debt-trends.css' | relative_url }}">


<div class="td-trends-page">

  <header class="td-trends-header">
    <h1>Technical Debt — Trends &amp; Historical Analytics</h1>
    <p class="td-trends-subtitle">Track trends, measure impact and understand historical patterns</p>
    <p>Phase 4 introduces historical tracking and trend analytics for technical debt. Observations are recorded from successful reconciliations and provide time-series visibility, lifecycle activity, and financial history.</p>
  </header>

  <section class="td-trends-metrics" aria-label="Technical debt trend metrics">
    <article class="td-trends-metric td-trends-blue">
      <span class="td-trends-metric-icon">▤</span>
      <div><p>Total Items</p><strong>248</strong><span class="td-trends-change td-trends-good">↓ 12%</span><small>vs previous period</small></div>
    </article>
    <article class="td-trends-metric td-trends-red">
      <span class="td-trends-metric-icon">⚠</span>
      <div><p>Critical &amp; High</p><strong>76</strong><span class="td-trends-change td-trends-bad">↑ 8%</span><small>vs previous period</small></div>
    </article>
    <article class="td-trends-metric td-trends-purple">
      <span class="td-trends-metric-icon">▥</span>
      <div><p>New Items</p><strong>32</strong><span class="td-trends-change td-trends-good">↓ 14%</span><small>vs previous period</small></div>
    </article>
    <article class="td-trends-metric td-trends-green">
      <span class="td-trends-metric-icon">✓</span>
      <div><p>Resolved</p><strong>54</strong><span class="td-trends-change td-trends-good">↑ 24%</span><small>vs previous period</small></div>
    </article>
  </section>

  <section class="td-trends-chart-grid">
    <article class="td-trends-panel">
      <div class="td-trends-panel-heading">
        <h2>Technical debt trends</h2>
        <span class="td-trends-select">Last 6 months⌄</span>
      </div>
      <div class="td-trends-line-chart" role="img" aria-label="Illustrative trend chart for critical, medium, and low technical debt items">
        <div class="td-trends-y-labels"><span>200</span><span>150</span><span>100</span><span>50</span><span>0</span></div>
        <div class="td-trends-plot">
          <div class="td-trends-gridlines"><i></i><i></i><i></i><i></i><i></i></div>
          <svg viewBox="0 0 600 150" preserveAspectRatio="none" aria-hidden="true">
            <polygon points="0,40 100,27 200,44 300,60 400,61 500,65 600,72 600,150 0,150" fill="#ff4d4f" opacity=".08"/>
            <polygon points="0,73 100,69 200,78 300,84 400,86 500,91 600,97 600,150 0,150" fill="#1684ff" opacity=".08"/>
            <polygon points="0,109 100,107 200,110 300,113 400,115 500,117 600,121 600,150 0,150" fill="#10b981" opacity=".08"/>
            <polyline points="0,40 100,27 200,44 300,60 400,61 500,65 600,72" fill="none" stroke="#ff4d4f" stroke-width="2"/>
            <polyline points="0,73 100,69 200,78 300,84 400,86 500,91 600,97" fill="none" stroke="#1684ff" stroke-width="2"/>
            <polyline points="0,109 100,107 200,110 300,113 400,115 500,117 600,121" fill="none" stroke="#10b981" stroke-width="2"/>
            <g fill="#ff4d4f"><circle cx="0" cy="40" r="3.5"/><circle cx="100" cy="27" r="3.5"/><circle cx="200" cy="44" r="3.5"/><circle cx="300" cy="60" r="3.5"/><circle cx="400" cy="61" r="3.5"/><circle cx="500" cy="65" r="3.5"/><circle cx="600" cy="72" r="3.5"/></g>
            <g fill="#1684ff"><circle cx="0" cy="73" r="3.5"/><circle cx="100" cy="69" r="3.5"/><circle cx="200" cy="78" r="3.5"/><circle cx="300" cy="84" r="3.5"/><circle cx="400" cy="86" r="3.5"/><circle cx="500" cy="91" r="3.5"/><circle cx="600" cy="97" r="3.5"/></g>
            <g fill="#10b981"><circle cx="0" cy="109" r="3.5"/><circle cx="100" cy="107" r="3.5"/><circle cx="200" cy="110" r="3.5"/><circle cx="300" cy="113" r="3.5"/><circle cx="400" cy="115" r="3.5"/><circle cx="500" cy="117" r="3.5"/><circle cx="600" cy="121" r="3.5"/></g>
          </svg>
          <div class="td-trends-x-labels"><span>Apr</span><span>May</span><span>Jun</span><span>Jun</span><span>Jul</span><span>Aug</span><span>Sep</span></div>
        </div>
      </div>
      <div class="td-trends-legend"><span><i class="td-dot-red"></i>Critical &amp; High</span><span><i class="td-dot-blue"></i>Medium</span><span><i class="td-dot-green"></i>Low</span></div>
    </article>

    <article class="td-trends-panel">
      <h2>Items by lifecycle state</h2>
      <div class="td-trends-donut-layout">
        <div class="td-trends-donut" role="img" aria-label="Lifecycle state distribution totaling 248 items"><div><strong>248</strong><small>Total Items</small></div></div>
        <ul class="td-trends-state-list">
          <li><i class="td-state-gray"></i><span>NOT_APPLICABLE</span><b>12 (5%)</b></li>
          <li><i class="td-state-blue"></i><span>PENDING_EVALUATION</span><b>48 (19%)</b></li>
          <li><i class="td-state-teal"></i><span>WITHIN_SLA</span><b>76 (31%)</b></li>
          <li><i class="td-state-amber"></i><span>DUE_SOON</span><b>32 (13%)</b></li>
          <li><i class="td-state-red"></i><span>OVERDUE</span><b>28 (11%)</b></li>
          <li><i class="td-state-pink"></i><span>BREACHED</span><b>18 (7%)</b></li>
          <li><i class="td-state-purple"></i><span>RESOLVED</span><b>54 (22%)</b></li>
        </ul>
      </div>
    </article>
  </section>

  <div class="td-trends-lower-grid">
    <div>
      <section class="td-trends-section">
        <h2>Historical model</h2>
        <p>Technical debt trends are backed by the following persistence model.</p>
        <div class="td-trends-table-wrap">
          <table>
            <thead><tr><th>Table</th><th>Description</th></tr></thead>
            <tbody>
              <tr><td><code>technical_debt_observation_runs</code></td><td>One row per organization per UTC bucketDate.</td></tr>
              <tr><td><code>technical_debt_item_observations</code></td><td>Immutable upsert per (organization, item, day).</td></tr>
              <tr><td><code>technical_debt_inventory_snapshots</code></td><td>Aggregated inventory/financial totals per run.</td></tr>
              <tr><td><code>technical_debt_lifecycle_events</code></td><td>Append-only lifecycle state changes.</td></tr>
              <tr><td><code>technical_debt_financial_history</code></td><td>Daily cost and rightsizing estimates.</td></tr>
            </tbody>
          </table>
        </div>
      </section>

	    </div>

    <div>
      <section class="td-trends-panel td-trends-captured">
        <h2>Data captured</h2>
        <ul>
          <li>Inventory time series (items count by lifecycle state)</li>
          <li>Lifecycle activity counts (created, resolved, reopened)</li>
          <li>Financial history (USD estimates)</li>
          <li>Source collection coverage (cloud, GitHub, policy, etc.)</li>
          <li>Backlog drilldown and trends</li>
        </ul>
      </section>

      <section class="td-trends-scheduler">
        <h2><span>◷</span> Scheduler</h2>
        <div class="td-trends-panel td-trends-scheduler-card">
          <span class="td-trends-scheduler-icon">♙</span>
          <div><strong>TechnicalDebtHistoryScheduler</strong>
            <p>Runs on <code>TECHNICAL_DEBT_HISTORY_INTERVAL_MS</code> (default 24h) and reconciles organizations that have debt items, refreshing observations.</p>
          </div>
        </div>
      </section>
    </div>
  </div>
</div>
