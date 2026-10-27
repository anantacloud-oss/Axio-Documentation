---
layout: default
title: AI MCP Servers
parent: AI
nav_order: 4
permalink: /axio/ai/mcp-servers/
---

<link rel="stylesheet" href="{{ '/assets/css/ai-mcp-servers.css' | relative_url }}">

<div class="mcp-page">

<h1 class="mcp-title">AI MCP Servers</h1>

<div class="mcp-info-banner">
<span class="mcp-banner-icon">ⓘ</span>
<span>
Open <strong>AI → MCP Servers</strong>.
See also the AI Assistant and Model Platform.
</span>
</div>

<h2>Permissions</h2>
<p class="mcp-description">
Browse the catalog with <code>mcp:use</code>.
Run tools from the UI or Assistant with <code>ai_gateway:use</code> plus each tool’s
<code>requiredPermission</code>.
Approve or reject HIGH-risk executions with <code>ai_gateway:approve</code> on
<strong>AI → Activity → Tool runs</strong>.
</p>

<h2>What it is</h2>

<p class="mcp-description">
Axio exposes Model Context Protocol–style <strong>servers</strong> (domains)
and <strong>tools</strong> over HTTP in two layers:
</p>

<div class="mcp-numbered-list">

<div class="mcp-numbered-item">
<span class="mcp-number">1</span>
<p>
<strong>Platform MCP</strong> — <strong>22</strong> org-scoped domain servers
bound to real platform services. Each tool declares
<code>requiredPermission</code>, parameter validation, audit logging, and a risk level
(<code>LOW</code>, <code>MEDIUM</code>, <code>HIGH</code>). HIGH-risk tools pause for
human approval before execution completes.
</p>
</div>

<div class="mcp-numbered-item">
<span class="mcp-number">2</span>
<p>
<strong>Classic MCP</strong> — JSON-RPC 2.0 Streamable HTTP, plus a human-readable
manifest. Protocol version <code>2025-06-18</code>,
server name <code>axio-mcp</code>. The manifest merges classic tools with all Platform MCP
tools (qualified names such as <code>projects.list_projects</code>).
</p>
</div>

</div>

<div class="mcp-warning-banner">
<span class="mcp-banner-icon">♢</span>
<span>
The MCP Servers page loads Platform MCP discovery and the Copilot tool-calling API — the same execution
records as the Assistant. The UI lists <strong>all</strong> Platform MCP tools; the Assistant
system prompt only recommends tools marked <code>copilotExpose</code>.
</span>
</div>

<h2>How to use</h2>

<div class="mcp-step-grid">

<div class="mcp-step-card">
<div class="mcp-step-top">
<span class="mcp-step-number">1</span>
<span class="mcp-step-icon">⌕</span>
</div>
<p>
Browse servers by domain; search and filter by risk. Inspect tool name, qualified name,
parameters, required permission, and risk badge.
</p>
</div>

<div class="mcp-step-card">
<div class="mcp-step-top">
<span class="mcp-step-number">2</span>
<span class="mcp-step-icon">▣</span>
</div>
<p>
<strong>Run</strong> from the catalog form, use <strong>Ask Copilot</strong> to open the
Assistant with a prefilled prompt, or name a tool in natural language in chat.
</p>
</div>

<div class="mcp-step-card">
<div class="mcp-step-top">
<span class="mcp-step-number">3</span>
<span class="mcp-step-icon">♢</span>
</div>
<p>
Review results in the run dialog. Approve or reject HIGH-risk runs on
<strong>AI → Activity → Tool runs</strong> or via
quick-action badges when pending approvals exist.
</p>
</div>

</div>

<h2>Catalog features</h2>
<div class="mcp-feature-list">
<div>✓ <span>Domain-grouped tool table with server metadata from discovery</span></div>
<div>✓ <span>Risk filter (ALL / LOW / MEDIUM / HIGH) and text search</span></div>
<div>✓ <span>Favorites, tool details drawer, and recent execution history on the page</span></div>
<div>✓ <span>Project/workspace pickers for tools that accept hierarchy refs</span></div>
<div>✓ <span>Quick actions: Open Assistant, Tool runs, Pending approvals</span></div>
</div>



<div class="mcp-success-banner">
<span class="mcp-success-icon">✓</span>
<span>
Every tool enforces <code>requiredPermission</code> at execution time.
HIGH <code>riskLevel</code> tools enter <code>AWAITING_APPROVAL</code> until a user with
<code>ai_gateway:approve</code> approves or rejects.
LOW and MEDIUM tools run immediately after RBAC and input validation (including secret scanning on string inputs).
</span>
</div>

<h2>Classic MCP tools</h2>

<p class="mcp-section-description">
Built-in JSON-RPC tools:
</p>

<div class="mcp-classic-grid">

<div class="mcp-classic-item">
<span class="classic-icon blue">▣</span>
<strong>plan</strong>
<span>Terraform/OpenTofu plan for a workspace</span>
</div>

<div class="mcp-classic-item">
<span class="classic-icon purple">▱</span>
<strong>chat</strong>
<span>Legacy copilot chat message</span>
</div>

<div class="mcp-classic-item">
<span class="classic-icon green">✓</span>
<strong>apply</strong>
<span>Apply workspace</span>
</div>

<div class="mcp-classic-item">
<span class="classic-icon blue">⟳</span>
<strong>rollback</strong>
<span>Previous Terraform state version</span>
</div>

<div class="mcp-classic-item">
<span class="classic-icon red">▱</span>
<strong>destroy</strong>
<span>Destroy workspace resources</span>
</div>

<div class="mcp-classic-item">
<span class="classic-icon purple">⌕</span>
<strong>search</strong>
<span>Search projects, stacks, workspaces, policies, variables</span>
</div>

<div class="mcp-classic-item">
<span class="classic-icon blue">⌁</span>
<strong>drift</strong>
<span>Run a drift monitor check</span>
</div>

<div class="mcp-classic-item">
<span class="classic-icon purple">✦</span>
<strong>generate</strong>
<span>Generate Terraform or Pulumi from a prompt</span>
</div>

<div class="mcp-classic-item">
<span class="classic-icon orange">♢</span>
<strong>approve / cancel</strong>
<span>Approval request decisions</span>
</div>

<div class="mcp-classic-item">
<span class="classic-icon purple">▥</span>
<strong>analyze</strong>
<span>Architecture / cost / security analysis for a workspace</span>
</div>

</div>

</div>


<nav class="page-navigation cost-page-navigation" aria-label="Documentation navigation">

    <a class="nav-button previous"
       href="{{ '/axio/ai/model-platform/' | relative_url }}">
       ← Model Platform
    </a>

    <a class="nav-button next"
       href="{{ '/axio/administration/profile/' | relative_url }}">
       Profile →
    </a>

  </nav>
