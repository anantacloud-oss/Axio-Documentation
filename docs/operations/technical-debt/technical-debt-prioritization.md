---
title: Technical Debt — Prioritization & Dependency Intelligence
layout: default
parent: Technical Debt
nav_order: 6
permalink: /axio/operations/technical-debt/technical-debt-prioritization/
---

<link rel="stylesheet" href="{{ '/assets/css/technical-debt-prioritization.css' | relative_url }}">


<div class="td-prio-page">
  
  <header class="td-prio-header">
    <h1>Technical Debt — Prioritization &amp; Dependency Intelligence</h1>
    <p class="td-prio-subtitle">Explainable priority scores to focus on what matters most</p>
    <p>Phase 5 introduces intelligent prioritization for technical debt items using risk, financial impact, lifecycle urgency and dependency analysis. It helps you focus on high-impact items and understand the blast radius before remediation.</p>
  </header>

  <section class="td-prio-metrics" aria-label="Prioritization metrics">
    <article class="td-prio-metric td-prio-red">
      <span class="td-prio-metric-icon">▥</span>
      <div><p>High Priority Items</p><strong>76</strong><span class="td-prio-change td-prio-bad">↑ 18%</span><small>vs previous period</small></div>
    </article>
    <article class="td-prio-metric td-prio-green">
      <span class="td-prio-metric-icon">✓</span>
      <div><p>Medium Priority Items</p><strong>102</strong><span class="td-prio-change td-prio-good">↓ 12%</span><small>vs previous period</small></div>
    </article>
    <article class="td-prio-metric td-prio-blue">
      <span class="td-prio-metric-icon">◷</span>
      <div><p>Low Priority Items</p><strong>70</strong><span class="td-prio-change td-prio-good">↓ 8%</span><small>vs previous period</small></div>
    </article>
    <article class="td-prio-metric td-prio-purple">
      <span class="td-prio-metric-icon">▤</span>
      <div><p>Estimated Financial Impact</p><strong>$184K</strong><span class="td-prio-change td-prio-bad">↑ 22%</span><small>vs previous period</small></div>
    </article>
  </section>

  <div class="td-prio-main-grid">
    <div>
      <section class="td-prio-section">
        <h2>Priority scoring model</h2>
        <p>Each item is scored using multiple factors with explainable weights.</p>
        <div class="td-prio-factors">
          <article class="td-prio-factor td-prio-factor-red"><span>⬟</span><strong>Risk</strong><b>30%</b><p>Security, compliance, exposure</p></article>
          <article class="td-prio-factor td-prio-factor-blue"><span>$</span><strong>Financial Impact</strong><b>25%</b><p>Cost, rightsizing opportunity</p></article>
          <article class="td-prio-factor td-prio-factor-purple"><span>◷</span><strong>Lifecycle Urgency</strong><b>20%</b><p>End-of-life, deprecated versions</p></article>
          <article class="td-prio-factor td-prio-factor-green"><span>⑂</span><strong>Dependency Risk</strong><b>15%</b><p>Blast radius, critical services</p></article>
          <article class="td-prio-factor td-prio-factor-amber"><span>▤</span><strong>Occurrence</strong><b>10%</b><p>Frequency, scope and usage</p></article>
        </div>
      </section>

      <section class="td-prio-section td-prio-items-section">
        <h2>Example prioritized items</h2>
        <p>A unified view of technical debt items with priority scores and key factors.</p>
        <div class="td-prio-table-wrap">
          <table class="td-prio-table">
            <thead><tr><th>Resource / Item</th><th>Type</th><th>Priority</th><th>Score</th><th>Key factors</th><th>Estimated impact</th></tr></thead>
            <tbody>
              <tr><td>S3 public access</td><td>Security finding</td><td><span class="td-prio-pill td-prio-pill-high">High</span></td><td>92</td><td>Security risk, compliance</td><td>$20K</td></tr>
              <tr><td>Outdated Terraform</td><td>Code dependency</td><td><span class="td-prio-pill td-prio-pill-high">High</span></td><td>88</td><td>EOL in 3 months</td><td>$15K</td></tr>
              <tr><td>Unused EC2 instance</td><td>Cost optimization</td><td><span class="td-prio-pill td-prio-pill-medium">Medium</span></td><td>64</td><td>Low usage, high cost</td><td>$8K</td></tr>
              <tr><td>Deprecated Lambda runtime</td><td>Lifecycle</td><td><span class="td-prio-pill td-prio-pill-medium">Medium</span></td><td>58</td><td>EOL in 6 months</td><td>$12K</td></tr>
              <tr><td>Old Docker base image</td><td>Code dependency</td><td><span class="td-prio-pill td-prio-pill-low">Low</span></td><td>32</td><td>Minor version lag</td><td>$2K</td></tr>
            </tbody>
          </table>
        </div>
      </section>

    </div>

    <div>
      <section class="td-prio-section td-prio-chart-section">
        <h2>Items by priority</h2>
        <div class="td-prio-donut-layout">
          <div class="td-prio-donut" role="img" aria-label="248 total items: 76 high, 102 medium, 70 low">
            <div><strong>248</strong><span>Total Items</span></div>
          </div>
          <ul class="td-prio-legend">
            <li><span class="td-prio-dot td-prio-dot-high"></span><span>High</span><strong>76 (31%)</strong></li>
            <li><span class="td-prio-dot td-prio-dot-medium"></span><span>Medium</span><strong>102 (41%)</strong></li>
            <li><span class="td-prio-dot td-prio-dot-low"></span><span>Low</span><strong>70 (28%)</strong></li>
          </ul>
        </div>
      </section>

      <section class="td-prio-section td-prio-dependency-section">
        <h2>Dependency graph (blast radius)</h2>
        <p>Understand how a technical debt item impacts dependent resources.</p>
        <div class="td-prio-dependency">
          <div class="td-prio-resource td-prio-resource-ecs"><span>▦</span><div>ECS Cluster<small>(3 services)</small></div></div>
          <div class="td-prio-resource td-prio-resource-rds"><span>▤</span><div>RDS Database<small>(1 instance)</small></div></div>
          <div class="td-prio-resource td-prio-resource-s3"><span>▣</span><div>S3 Bucket<small>(2 buckets)</small></div></div>
          <div class="td-prio-dependency-arrows" aria-hidden="true">↘<br>→<br>↗</div>
          <div class="td-prio-central"><span>⚠</span><div><strong>Outdated<br>Application</strong><small>Priority: High</small></div></div>
          <div class="td-prio-dependency-arrows td-prio-arrows-right" aria-hidden="true">↗<br>→<br>↘</div>
          <div class="td-prio-resource td-prio-resource-lambda"><span>λ</span><div>Lambda Functions<small>(4 functions)</small></div></div>
          <div class="td-prio-resource td-prio-resource-api"><span>◇</span><div>API Gateway<small>(2 endpoints)</small></div></div>
          <div class="td-prio-resource td-prio-resource-cloudwatch"><span>▣</span><div>CloudWatch<small>(5 alarms)</small></div></div>
        </div>
      </section>

      <section class="td-prio-benefits">
        <h2><span>✓</span> Benefits</h2>
        <ul>
          <li>Focus on high-impact items that reduce risk and cost</li>
          <li>Explainable priority scores with clear factors</li>
          <li>Understand dependency blast radius before remediation</li>
          <li>Align remediation with business and compliance goals</li>
          <li>Better resource allocation and faster decision making</li>
        </ul>
      </section>
    </div>
  </div>
</div>
