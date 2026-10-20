---
title: AWS Account Assessment
layout: default
parent: Technical Debt
nav_order: 2
permalink: /axio/operations/technical-debt/technical-debt-aws-phase/
---

<link rel="stylesheet" href="{{ '/assets/css/technical-debt-aws-phase.css' | relative_url }}">


<div class="td-aws-page">

  <header class="td-aws-header">
    <h1>AWS account assessment</h1>
    <p class="td-aws-subtitle">Real AWS inventory, assessment run and lifecycle debt</p>
    <p>Phase A delivers real AWS inventory (no catalog placeholders for AWS sync), an assessment run record, and lifecycle technical debt reconciled into the backlog.</p>
  </header>

  <section class="td-aws-summary" aria-label="Assessment capabilities">
    <article class="td-aws-summary-card td-aws-green"><span class="td-aws-summary-icon">⬡</span><div><strong>Resource Discovery</strong><p>EC2, EBS, RDS, Lambda<br>across all regions</p></div></article>
    <article class="td-aws-summary-card td-aws-purple"><span class="td-aws-summary-icon">▤</span><div><strong>Assessment Run</strong><p>RUNNING → SUCCEEDED<br>/ PARTIAL / FAILED</p></div></article>
    <article class="td-aws-summary-card td-aws-amber"><span class="td-aws-summary-icon">▣</span><div><strong>Lifecycle Debt</strong><p>Deprecated runtimes,<br>previous-gen instances,<br>unsupported versions</p></div></article>
    <article class="td-aws-summary-card td-aws-blue"><span class="td-aws-summary-icon">⚒</span><div><strong>Backlog Integration</strong><p>Automatically reconciled<br>into Technical Debt</p></div></article>
  </section>

  <section class="td-aws-section">
    <h2>Prerequisites</h2>
    <p>Create an active AWS <code>CloudConnection</code> with the required IAM permissions.</p>
    <div class="td-aws-two-col">
      <div class="td-aws-panel td-aws-iam"><div class="td-aws-wordmark">aws<span>⌣</span></div><ul><li><code>ec2:DescribeInstances</code></li><li><code>ec2:DescribeVolumes</code></li><li><code>rds:DescribeDBInstances</code></li><li><code>lambda:ListFunctions</code></li></ul></div>
      <aside class="td-aws-panel td-aws-warning"><div class="td-aws-warning-icon">!</div><div><strong>Important</strong><ul><li>Connection must not be simulated/demo (<code>isSimulatedCloudConnection = false</code>).</li><li>Ensure credentials have read access for all target regions.</li></ul></div></aside>
    </div>
  </section>


  <div class="td-aws-detail-grid">
    <div>
      <section class="td-aws-section"><h2>Assess request body</h2>
        <div class="td-aws-code"><span class="td-aws-code-label">json</span><pre><code>{
  "syncCloudBilling": false
}</code></pre></div>
        <div class="td-aws-info"><span>i</span><p>When <code>syncCloudBilling</code> is true, FinOps billing sync runs before technical debt reconciliation.</p></div>
      </section>
      <section class="td-aws-section"><h2>Technical debt source</h2>
        <div class="td-aws-panel td-aws-source-panel"><span class="td-aws-source-icon">▤</span><div><strong><code>AWS_LIFECYCLE</code></strong><p>Items keyed as <code>aws-lifecycle:{connectionId}:...</code>.</p><p>Requires discovery data; run assess or sync on AWS before expecting backlog rows.</p></div></div>
      </section>
    </div>
    <div>
      <section class="td-aws-section td-aws-assess-list"><h2>What assess does</h2>
        <ol>
          <li><span>1</span><p>Creates <code>AwsAccountAssessmentRun</code> (RUNNING → SUCCEEDED / PARTIAL / FAILED).</p></li>
          <li><span>2</span><p><strong>Discovery</strong> — multi-region EC2, EBS, RDS, Lambda → <code>cloud_discovered_resources</code> with metadata (runtime, engine version, instance type, etc.).</p></li>
          <li><span>3</span><p><strong>Technical debt reconcile</strong> — includes new source <code>AWS_LIFECYCLE</code> (deprecated Lambda runtimes, previous-gen EC2 families, MySQL 5.7 RDS, unattached EBS).</p></li>
          <li><span>4</span><p>Persists run summary + reconciliation JSON on the assessment row.</p></li>
        </ol>
      </section>
      <section class="td-aws-section td-aws-limits"><h2><span class="td-aws-limits-icon">▤</span> Limits</h2><div class="td-aws-panel"><ul><li>Up to 250 resources per type per region (pagination where supported).</li><li>Partial status when a region API fails (other regions still stored).</li></ul></div></section>
    </div>
  </div>
</div>
