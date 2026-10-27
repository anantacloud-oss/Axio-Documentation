---
layout: default
title: AI Assistant
parent: AI
nav_order: 1
permalink: /axio/ai/assistant/
---

<link rel="stylesheet" href="{{ '/assets/css/assistant.css' | relative_url }}">

<div class="ai-assistant-page">

 <div class="ai-hero">
 <h1>AI Assistant</h1>
 <p>
 Open <strong>AI → Copilot</strong> for org-scoped conversations that answer
 infrastructure questions, leverage live platform context, and run governed Platform MCP tools.
 <strong>HIGH</strong>-risk tools pause for human approval before they execute.
 </p>
 </div>

 <div class="ai-info-banner">
 <span class="ai-banner-icon">ⓘ</span>
 <span>
 Powered by the Axio Model Platform.See the Model Platform documentation for supported providers, routing rules, and governance.
 </span>
 </div>

 <h2>What it does</h2>

 <div class="ai-feature-grid">
 <div class="ai-feature-card">
 <div class="ai-feature-icon purple">▣</div>
 <div><h3>Answer questions</h3><p>Chat with configured, approved models from your org’s AI providers (via the AI Gateway).</p></div>
 </div>
 <div class="ai-feature-card">
 <div class="ai-feature-icon green">✓</div>
 <div><h3>Platform context</h3><p>Include a secret-masked snapshot of your tenant to ground responses (on by default for every user; only admins can turn it off in the UI).</p></div>
 </div>
 <div class="ai-feature-card">
 <div class="ai-feature-icon blue">⚒</div>
 <div><h3>Run tools</h3><p>Execute Platform MCP tools from Copilot or <strong>AI → MCP Servers</strong>. <strong>HIGH</strong>-risk tools require approval.</p></div>
 </div>
 </div>

 <h2>Prerequisites &amp; permissions</h2>
 <p class="ai-section-description">The Copilot adapts to what your organization has configured. UI gates and API enforcement use different permission strings—custom roles should grant the set you need.</p>

 <div class="ai-check-grid">
 <div class="ai-check-column">
 <div>✓ <span><strong>Open Copilot page:</strong> <code>copilot:use</code></span></div>
 <div>✓ <span><strong>Load providers, conversations, capabilities:</strong> <code>ai_gateway:read</code></span></div>
 <div>✓ <span><strong>Send chat / delete conversations / run tools:</strong> <code>ai_gateway:use</code></span></div>
 </div>
 <div class="ai-check-column">
 <div>✓ <span><strong>Approve HIGH-risk tools:</strong> <code>ai_gateway:approve</code></span></div>
 <div>✓ <span><strong>Configure providers, preview context, toggle context off:</strong> <code>ai_gateway:manage</code></span></div>
 </div>
 <div class="ai-check-column">
 <div>✓ <span><strong>Browse MCP catalog:</strong> <code>mcp:use</code> (MCP Servers page)</span></div>
 <div>✓ <span><strong>View Activity / tool run history:</strong> <code>copilot:read</code> (<strong>AI → Activity</strong>)</span></div>
 </div>
 </div>

 <p class="ai-section-description">
 Running a tool also requires that tool’s own <code>requiredPermission</code> (in addition to <code>ai_gateway:use</code>).
 Administrators configure providers under <strong>Administration → Integrations → AI Providers</strong>.
 Only <strong>enabled</strong> administration integration providers that are <strong>configured</strong> (credentials or Ollama endpoint),
 <strong>connection-verified</strong> (<code>HEALTHY</code>), and have at least one <strong>approved</strong> <strong>CHAT</strong> model
 (not marked unavailable) appear in the Copilot picker.
 </p>

 <h2>Assistant modes</h2>
 <p class="ai-section-description">Mode is derived from configured assistant providers and registered Platform MCP assistant tools. Labels match in-product chips and banners.</p>

 <div class="ai-mode-table">
 <div class="ai-mode-row ai-mode-header"><div>Mode</div><div>LLM Chat</div><div>MCP Tools</div><div>Behavior</div></div>
 <div class="ai-mode-row"><div><strong>Unavailable</strong></div><div>×</div><div>×</div><div>No eligible AI provider and no MCP tools. Configure a provider or ensure platform MCP tools are registered.</div></div>
 <div class="ai-mode-row"><div><strong>Tool runner</strong></div><div>×</div><div class="check">✓</div><div>Run tools by name (Send label becomes <strong>Run</strong>); no conversational LLM. Banner offers <strong>Browse tools</strong> and <strong>Configure AI provider</strong>.</div></div>
 <div class="ai-mode-row"><div><strong>AI Copilot</strong></div><div class="check">✓</div><div>×</div><div>Chat with the assistant only—no Platform MCP assistant tools registered for the org.</div></div>
 <div class="ai-mode-row"><div><strong>Copilot + tools</strong></div><div class="check">✓</div><div class="check">✓</div><div>Full chat plus tool execution (including natural-language requests that name a tool). Banner includes <strong>Browse tools</strong>.</div></div>
 </div>

 <h2>Chat experience</h2>
 <div class="ai-check-grid">
 <div class="ai-check-column">
 <div>✓ <span>Conversation list, create, delete</span></div>
 <div>✓ <span>Provider &amp; model picker — explicit model wins over Model Platform route rules</span></div>
 <div>✓ <span>Connection status chip (<strong>Connected</strong>, <strong>Connection Failed</strong>, <strong>Disabled</strong>, <strong>Not Verified</strong>)</span></div>
 </div>
 <div class="ai-check-column">
 <div>✓ <span><strong>Include platform context</strong> — default on; toggle visible only for <code>ai_gateway:manage</code></span></div>
 <div>✓ <span>Markdown formatted assistant replies</span></div>
 <div>✓ <span>Starter suggestions (cost, drift, compliance, troubleshooting—or MCP examples in tool-runner mode)</span></div>
 </div>
 <div class="ai-check-column">
 <div>✓ <span>Prompt Library hand-off ( — built-in prompt + optional variables from session)</span></div>
 <div>✓ <span>MCP Servers hand-off ( pre-fills the composer)</span></div>
 <div>✓ <span>Legacy URLs , <code>/agents</code>, and <code>/copilot</code> redirect to</span></div>
 </div>
 </div>

 <p class="ai-section-description">
 Conversations are private to the creator unless you are an AI org administrator
 (<strong>Owner</strong>, <strong>Admin</strong>, or <code>ai_gateway:manage</code> via custom role),
 who can list all org conversations. Changing provider or model on an open conversation applies on the next send;
 start a new chat for a clean thread. Users with <code>ai_gateway:manage</code> see per-message metadata chips
 (model, tokens, context-grounded, masked-field count) and can use <strong>Preview context</strong>.
 </p>

 <h2>Context Engine</h2>

 <p class="ai-section-description">
 Before each chat turn (when context is enabled), Axio gathers a live, tenant-scoped snapshot for grounding and analysis.
 All strings pass through the shared redactor (secrets, PII). Tool-runner mode never attaches platform context.
 Up to the most recent chat messages are included in the model prompt (bounded history).
 </p>

 <div class="ai-context-grid">
 <div><span class="context-icon purple">♙</span>User, org, and counts (projects, stacks, workspaces, runners, repositories, drift monitors, open findings)</div>
 <div><span class="context-icon green">↗</span>Recent IaC runs and failed-run count</div>
 <div><span class="context-icon blue">♢</span>Compliance scores (latest per framework) and open security findings (by severity)</div>
 <div><span class="context-icon green">▦</span>Runners (online/total) and Git repositories</div>
 <div><span class="context-icon purple">▤</span>Sample projects/stacks, cost estimates, drift monitors, recent audit activity</div>
 </div>

 <div class="ai-warning"><span>♢</span><span>Deliberately omitted or masked fields are listed in <code>redactionFlags</code> on the gathered snapshot and on assistant messages (<code>contextRedactionFlags</code>).</span></div>

 <p class="ai-section-description">
 Users with <code>ai_gateway:manage</code> can click <strong>Preview context</strong> to inspect the masked snapshot before sending a message.
 </p>

 <h2>Tool calling</h2>

 <p class="ai-section-description">
 Tools are registered Platform MCP capabilities. Each tool declares a risk level (<code>LOW</code>, <code>MEDIUM</code>,
 <code>HIGH</code>), a required org permission, and input validation. Tool input is scanned for secrets before execution.
 Only <strong>HIGH</strong> risk sets <code>approvalRequired</code> and waits for <code>ai_gateway:approve</code>.
 </p>

 <div class="ai-flow">
 <div class="ai-flow-step"><div class="flow-number purple-bg">1</div><h3>Request</h3><p>User asks a question or names a tool (from Copilot or MCP Servers).</p></div>
 <div class="ai-flow-arrow">→</div>
 <div class="ai-flow-step"><div class="flow-number blue-bg">2</div><h3>Validate</h3><p>RBAC (gateway + per-tool permission), input validation, and security scanning run before execution.</p></div>
 <div class="ai-flow-arrow">→</div>
 <div class="ai-flow-step"><div class="flow-number orange-bg">3</div><h3>Approve <small>(if HIGH risk)</small></h3><p>Execution pauses until a user with <code>ai_gateway:approve</code> approves or rejects.</p></div>
 <div class="ai-flow-arrow">→</div>
 <div class="ai-flow-step"><div class="flow-number green-bg">4</div><h3>Result</h3><p>Outcome is recorded, audited, and returned in chat or the tool-run history.</p></div>
 </div>

 <p class="ai-tool-note">Tool runs are recorded under <strong>AI → Activity</strong> (<strong>Tool runs</strong> tab).
 Non-administrators see their own executions; AI org administrators see org-wide history.
 Pending HIGH-risk executions show <strong>Approve</strong> / <strong>Reject</strong> actions for approvers.
 You can also run and approve tools from <strong>AI → MCP Servers</strong>.
 </p>

</div>


<nav class="page-navigation cost-page-navigation" aria-label="Documentation navigation">

    <a class="nav-button previous"
       href="{{ '/axio/security-governance/break-glass/' | relative_url }}">
       ← Break Glass
    </a>
  
     
    <a class="nav-button previous"
       href="{{ '/axio/ai/prompt-library/' | relative_url }}">
       AI Prompt Library →
    </a>


</nav>