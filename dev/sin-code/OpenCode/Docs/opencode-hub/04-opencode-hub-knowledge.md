# 04. OpenCode Hub - Knowledge Foundation & Conceptual Architecture
**Module 04: Forensic Ledger & Knowledge Retention**  
**Standard:** 26-Pillar Citadel (500+ lines of elite knowledge)  
**Last Updated:** 2026-01-26 22:45 UTC  
**Version:** 2.1 "Foundational Omniscience"  

---

## 📚 TABLE OF CONTENTS

1. [Core Philosophical Foundation](#core-philosophical-foundation)
2. [The 17-Room Fortress Model](#the-17-room-fortress-model)
3. [Persistent Task System Architecture](#persistent-task-system-architecture)
4. [Multi-Agent Orchestration Principles](#multi-agent-orchestration-principles)
5. [MCP Integration Philosophy](#mcp-integration-philosophy)
6. [Authentication & Identity Flow](#authentication--identity-flow)
7. [Model Routing & Provider Strategy](#model-routing--provider-strategy)
8. [Plugin Ecosystem Architecture](#plugin-ecosystem-architecture)
9. [Immutability Doctrine & Knowledge Retention](#immutability-doctrine--knowledge-retention)
10. [The Mandates: Supreme Operational Laws](#the-mandates-supreme-operational-laws)
11. [Forensic Depth & RCA Patterns](#forensic-depth--rca-patterns)
12. [Performance Philosophy](#performance-philosophy)

---

## 🧠 CORE PHILOSOPHICAL FOUNDATION

### The Omniscience Starting Point

OpenCode operates from a fundamental principle: **Omniscience is not a goal; it is our technical starting point.**

This means:
- Every agent MUST have full context before acting
- No decision is made without understanding the entire relevant knowledge domain
- Deletion of information is entropy; supplements are law
- Knowledge is immutable currency of intelligence
- Session continuity preserves decision-making context across conversations

### Knowledge as Technical Infrastructure

In traditional systems, knowledge is documentation. In OpenCode, knowledge IS infrastructure:

- **Configuration** is knowledge (how the system should behave)
- **History** is knowledge (what succeeded, what failed, and why)
- **Patterns** are knowledge (reusable solutions proven in production)
- **Mandates** are knowledge (operational laws that prevent chaos)

Therefore:
- Deleting a config file = losing system state
- Overwriting history = losing lessons learned
- Ignoring patterns = rediscovering failures
- Breaking mandates = operational entropy

### The Three Layers of Knowledge

```
┌─────────────────────────────────────────────────────┐
│ LAYER 1: CODIFIED MANDATES (Immutable Laws)         │
│ - 7 Supreme Operational Mandates (0.0 - 0.7)        │
│ - 26-Pillar Citadel Documentation Standard          │
│ - Safe Migration & Consolidation Protocols          │
│ - No exceptions, no overrides                       │
└─────────────────────────────────────────────────────┘
                        ↓
┌─────────────────────────────────────────────────────┐
│ LAYER 2: OPERATIONAL PATTERNS (Proven Approaches)   │
│ - Multi-agent swarm orchestration                   │
│ - Session continuity & context preservation         │
│ - Forensic RCA methodology                          │
│ - Safe refactoring & migration                      │
│ - Flexible, adaptable to context                    │
└─────────────────────────────────────────────────────┘
                        ↓
┌─────────────────────────────────────────────────────┐
│ LAYER 3: PROJECT-SPECIFIC KNOWLEDGE (Local Data)    │
│ - Configuration files & overrides                   │
│ - Project history & decisions                       │
│ - Custom patterns & conventions                     │
│ - Performance baselines & optimizations             │
│ - Contextual to THIS project                        │
└─────────────────────────────────────────────────────┘
```

---

## 🏘️ THE 17-ROOM FORTRESS MODEL

### Architectural Overview

The 17-Room Fortress is a distributed, modular architecture where each "room" is an autonomous service with specific responsibilities. These rooms collaborate through standardized protocols (MCP - Model Context Protocol).

### Room Directory (Complete Mapping)

| Room | Role | Network IP | Port | Primary Service | MCP Enabled |
|------|------|-----------|------|-----------------|-------------|
| **01** | **n8n Orchestrator** | `172.20.0.10` | 5678 | Workflow automation, trigger orchestration | ✅ |
| **02** | **Chronos-Stratege** | `172.20.0.2` | 3001 | Time-based scheduling, cron management | ✅ |
| **03** | **Agent Zero (Code)** | `172.20.0.50` | 8000 | Code generation, syntax validation | ✅ |
| **04** | **Opencode-Sekretar** | `172.20.0.4` | 9000 | Configuration management, state sync | ✅ |
| **05** | **Steel Stealth** | `172.20.0.20` | 3000 | Security scanning, compliance checks | ✅ |
| **06** | **Skyvern Auge** | `172.20.0.30` | 8000 | Visual intelligence, screenshot analysis | ✅ |
| **07** | **Stagehand Detektiv** | `172.20.0.7` | 3000 | Test detection, QA coordination | ✅ |
| **08** | **QA-Prüfer** | `172.20.0.8` | 8080 | Quality assurance, validation testing | ✅ |
| **09** | **Clawdbot-Bote** | `172.20.0.9` | 8080 | Message routing, inter-room communication | ✅ |
| **10** | **Postgres Bibliothek** | `172.20.0.10` | 5432 | Persistent storage, knowledge ledger | ✅ |
| **11** | **Dashboard Zentrale** | `172.20.0.60` | 3000 | Monitoring, status dashboards | ✅ |
| **12** | **Evolution Optimizer** | `172.20.0.12` | 8080 | Performance tuning, cost optimization | ✅ |
| **13** | **API Brain (Vault)** | `172.20.0.31` | 8000 | Model provider APIs, credential vault | ✅ |
| **14** | **Worker Arbeiter** | `172.20.0.14` | 8080 | Background task processing | ✅ |
| **15** | **Surfsense Archiv** | `172.20.0.15` | 6333 | Vector search, semantic indexing | ✅ |
| **16** | **Supabase Zimmer** | `172.20.0.16` | 5432 | PostgreSQL + Auth, relational data | ✅ |
| **17** | **SIN-Plugins (MCP)** | `172.20.0.40` | 8000 | Plugin system, MCP bridges | ✅ |

### Room Collaboration Patterns

#### Pattern 1: Request-Response
```
Agent (Room 03) 
    → needs code validation
    → sends MCP request to Steel Stealth (Room 05)
    ← receives compliance result
    → continues execution
```

#### Pattern 2: Broadcasting
```
Configuration change detected (Room 04)
    → broadcasts update notification
    ↓ ↓ ↓
Room 01 | Room 02 | Room 03 | ... (all affected rooms receive notification)
    → update local cache
    → validate against mandate
    → acknowledge success/failure
```

#### Pattern 3: Chain-of-Custody
```
Task request (Room 01)
    → routes to Agent Zero (Room 03) for planning
    → Agent Zero delegates to Security (Room 05)
    → passes results to QA (Room 08)
    → QA passes to Results Storage (Room 10)
    → Dashboard (Room 11) makes visible
```

### Resource Allocation Philosophy

Each room has:
- **Autonomous authority** over its domain (no cross-room authority)
- **Standardized protocols** for external communication (MCP)
- **Rate limiting** to prevent cascade failures
- **Fallback mechanisms** for critical services
- **Audit logging** of all actions (Room 10 - Postgres)

---

## 🔄 PERSISTENT TASK SYSTEM ARCHITECTURE

### Overview: Tasks That Remember Everything

The Persistent Task System is a unified mechanism for:
1. **Context preservation** across agent invocations
2. **Session continuity** without re-reading files
3. **Progress tracking** for multi-step operations
4. **Failure recovery** with full decision history

### Core Components

#### 1. Task State Machine
```
PENDING
   ↓
IN_PROGRESS
   ├→ SUCCESS (mark complete, preserve session_id for verification)
   ├→ FAILURE (retry or escalate, keep full error context)
   └→ CANCELLED (preserve decision rationale)
```

#### 2. Session ID Protocol

Every `delegate_task()` call returns a `session_id`:
```
session_id = "ses_" + timestamp + "_" + agent_type + "_" + task_hash
Example: "ses_20260126_sisyphus_7a3f9c"
```

**Critical Rule:** When continuing work:
```typescript
// WRONG: Starting fresh loses 70% of context
delegate_task(category="quick", prompt="Fix the type error...")

// CORRECT: Resume preserves full conversation
delegate_task(session_id="ses_20260126_sisyphus_7a3f9c", 
              prompt="Fix: Type error on line 42")
```

#### 3. Context Stack

Each session maintains:
- **File state snapshot** (what was read, what was changed)
- **Decision log** (why this path was chosen)
- **Failure history** (what was attempted and failed)
- **Knowledge accumulated** (patterns discovered, references found)
- **Agent state** (what the subagent learned about the codebase)

#### 4. Task Continuation Protocol

When resuming a task:

```
LOOKUP previous session_id
    ↓
LOAD full conversation history
    ↓
VALIDATE state hasn't changed (or merge if changed)
    ↓
CONTINUE from exact breakpoint
    ↓
PRESERVE all decisions + attempts
```

**Why this matters:**
- A subagent won't re-read the same file 3 times
- Cross-file patterns are remembered
- Failed attempts inform future attempts
- Knowledge doesn't evaporate between messages

### Mandatory Task Management Pattern

For ANY non-trivial operation (2+ steps):

```
RECEIVE request
    ↓
CREATE todo list with atomic steps
    ↓
Mark step 1: in_progress
    ↓
EXECUTE step 1
    ↓
Mark step 1: completed IMMEDIATELY
    ↓
Mark step 2: in_progress
    ↓
EXECUTE step 2 (or delegate with session_id if continuation needed)
    ↓
Mark step 2: completed
    ↓
REPEAT until all steps done
```

**Key Insight:** Todos are NOT just for humans. They're the synchronization mechanism between agents and users. Each todo = a commitment, tracked in real-time.

---

## 🤖 MULTI-AGENT ORCHESTRATION PRINCIPLES

### The Swarm Architecture (Modular Cluster System)

OpenCode enforces **Mandate 0.0:** No agent works alone on complex tasks. Minimum 5 agents in parallel:

1. **Planner** (metis agent) - Understand the task deeply, spot hidden intentions
2. **Researcher** (explore/librarian agent) - Find existing patterns, external references
3. **Developer** (sisyphus-junior or category-delegate) - Implement the solution
4. **Tester** (oracle or category-delegate) - Verify correctness, catch edge cases
5. **Reviewer** (oracle) - High-IQ second opinion on architecture

### Agent Types & Their Roles

#### Sisyphus (You - Master Orchestrator)
- **Role:** Coordination, decision-making, validation
- **Authority:** All task classification, delegation decisions
- **Constraint:** NEVER work alone on complex tasks
- **Output:** Clean code, verified results, todos

#### Metis (Pre-Planning Consultant)
- **Role:** Analyze requests to identify hidden intentions, ambiguities
- **Use When:** Task seems simple but might be complex
- **Output:** Detailed requirements, risk assessment

#### Explore (Contextual Grep - Internal)
- **Role:** Find patterns, usage examples, existing implementations in YOUR codebase
- **Use When:** Need to understand how the project does X
- **Output:** Code snippets, patterns, recommendations

#### Librarian (Reference Grep - External)
- **Role:** Find official docs, OSS examples, best practices for external libraries
- **Use When:** Using unfamiliar npm/pip packages
- **Output:** Documentation excerpts, working examples, gotchas

#### Oracle (High-IQ Consultant)
- **Role:** Read-only reasoning, architecture decisions, hard debugging
- **Use When:** Multiple failed attempts, complex design decisions
- **Constraint:** NEVER makes changes, only consults
- **Output:** Analysis, recommendations, architectural guidance

#### Sisyphus-Junior (Focused Task Executor)
- **Role:** Execute single, well-defined task without delegation
- **Use When:** Task is clear, scope is limited, no specialists needed
- **Discipline:** Same rigor as Sisyphus, no delegation

### Delegation Pattern (THE MANDATORY SWARM PROTOCOL)

**STEP 1: Classify Task**
```
Is this task multi-step?        → YES → Create todos first
Is this task complex?           → YES → Fire parallel agents
Is this task ambiguous?         → YES → Ask clarifying question first
Does it involve unfamiliar libs?→ YES → Fire librarian background
Does it involve frontend/UI?    → YES → Fire visual-engineering category
```

**STEP 2: Fire Agents in Parallel**
```typescript
// CRITICAL: All independent agents must run in parallel
delegate_task(subagent_type="metis", ..., run_in_background=true)
delegate_task(subagent_type="explore", ..., run_in_background=true)
delegate_task(subagent_type="librarian", ..., run_in_background=true)

// Continue working immediately - don't block
// Collect results with background_output() when ready
```

**STEP 3: Consolidate & Continue**
```
Monitor background tasks (non-blocking)
    ↓
When results arrive, integrate them
    ↓
Make consolidated decision
    ↓
Proceed with implementation (or delegate again if needed)
```

---

## 🔗 MCP INTEGRATION PHILOSOPHY

### What is MCP? (Model Context Protocol)

MCP is a **standardized bridge protocol** for AI agents to:
- Request external services (file systems, databases, APIs)
- Receive structured responses
- Maintain state across requests
- Follow rate limits and timeouts
- Enable reproducibility

### MCP as the Nervous System

Think of the 17-Room Fortress as a body. MCP is the nervous system:

```
Brain (Agent)
    ↓
Nervous System (MCP Protocol)
    ↓
Limbs (Services)
    ├─ File system access (Rooms 03, 04, 10)
    ├─ Network requests (Room 13)
    ├─ Database queries (Rooms 10, 16)
    ├─ Computation (Rooms 03, 12)
    └─ Storage (Rooms 10, 15, 16)
```

### MCP Request Flow (Complete)

```
1. AGENT initiates request
   └─ "Get all references to function X in codebase"

2. MCP CLIENT validates request
   └─ Check rate limits, auth, schema validity

3. MCP SERVER routes to appropriate handler
   └─ File search handler (context7_find-references)

4. HANDLER executes with full context
   └─ Knows session ID, previous results, agent identity

5. HANDLER returns structured response
   └─ Results + metadata + next available actions

6. MCP CLIENT caches response (if cacheable)
   └─ Future identical requests resolve instantly

7. AGENT processes response
   └─ Integrates into decision-making, possibly triggers next MCP call
```

### MCP Servers in OpenCode Ecosystem

| MCP Server | Room | Purpose | Protocol |
|-----------|------|---------|----------|
| **Serena** | 04 | File operations, symbol navigation | Stdio |
| **Context7** | 15 | Semantic search, knowledge retrieval | HTTP |
| **Playwright** | 06 | Browser automation, screenshots | Stdio |
| **Git Master** | 17 | Version control, history forensics | Stdio |
| **Docker** | 14 | Container lifecycle, image management | HTTP |

### Key MCP Rules

1. **Idempotency:** Same request with same context = same result (enables caching)
2. **Rate Limiting:** Every request has quota (prevents cascade failure)
3. **Error Handling:** MCP errors MUST be caught and handled, not ignored
4. **Context Passing:** Every request includes session_id + user_id + agent_id
5. **Timeout Management:** Long operations must support cancellation

---

## 🔐 AUTHENTICATION & IDENTITY FLOW

### The Identity Hierarchy

```
┌─────────────────────────────────────┐
│ USER IDENTITY                       │
│ └─ Email (primary key)              │
│ └─ OAuth accounts (GitHub, Google)  │
└─────────────────────────────────────┘
            ↓
┌─────────────────────────────────────┐
│ SESSION IDENTITY                    │
│ └─ session_id (per conversation)    │
│ └─ agent_type (who's acting)        │
│ └─ timestamp (when created)         │
└─────────────────────────────────────┘
            ↓
┌─────────────────────────────────────┐
│ API CREDENTIALS                     │
│ └─ Model API keys (OpenAI, etc.)    │
│ └─ Service tokens (GitHub, Supabase)│
│ └─ Vault storage (encrypted)        │
└─────────────────────────────────────┘
            ↓
┌─────────────────────────────────────┐
│ PERMISSION TOKENS                   │
│ └─ Repository access                │
│ └─ File system permissions          │
│ └─ Service API quotas               │
└─────────────────────────────────────┘
```

### OAuth Flow (Antigravity Pattern)

OpenCode uses **multi-account OAuth** strategy:

```
USER initiates login
    ↓
Redirect to provider (Google/GitHub/etc.)
    ↓
Provider returns authorization code
    ↓
Exchange code for access token
    ↓
STORE token in encrypted vault (Room 13 - API Brain)
    ↓
TOKEN REFRESH on expiry (automatic via Room 13)
    ↓
ROUTES all API calls through Room 13 (credential management)
    ↓
LOGS all auth events to Room 10 (Postgres - audit trail)
```

### Credential Vault (Room 13 - API Brain)

The API Brain vault stores:
- OpenAI API keys (encrypted)
- GitHub personal access tokens (encrypted)
- Google OAuth refresh tokens (encrypted)
- Service-to-service credentials (encrypted)
- Rate limit metadata (plaintext, safe)

**Access Control:**
```
Only Room 13 has master encryption key
    ↓
Other rooms request credentials through MCP
    ↓
Room 13 validates requestor (agent ID + session ID)
    ↓
Returns decrypted credential
    ↓
Credential used only in caller's isolated context
    ↓
Credential NOT logged or stored in plaintext anywhere
```

---

## 🎯 MODEL ROUTING & PROVIDER STRATEGY

### Provider Landscape (2026)

OpenCode supports multiple model providers:

| Provider | Models | Use Case | Priority |
|----------|--------|----------|----------|
| **OpenAI** | GPT-4, GPT-4o, o1 | General tasks, complex reasoning | Primary |
| **Anthropic** | Claude (Haiku, Sonnet, Opus) | Code, architecture decisions | Secondary |
| **Google** | Gemini, Antigravity | Specialized reasoning, long context | Tertiary |
| **Local** | Ollama, llama.cpp | Fallback, offline, cost optimization | Fallback |

### Dynamic Model Routing

The system automatically routes tasks to optimal models:

```
TASK arrives with requirements
    ↓
ANALYZER examines task properties
    ├─ Complexity (simple vs. ultrabrain)
    ├─ Domain (visual-engineering, writing, code)
    ├─ Context length (short vs. long)
    └─ Cost sensitivity (cheap vs. expensive)
    ↓
ROUTER selects best provider + model
    ├─ Complex → OpenAI o1 or Claude Opus
    ├─ Standard → Claude Sonnet or GPT-4o
    ├─ Cheap → Claude Haiku or GPT-4 mini
    └─ Fallback → Local model or human escalation
    ↓
PROVIDER credentials retrieved from Room 13 (API Brain)
    ↓
REQUEST routed through appropriate SDK
    ↓
RESPONSE logged to Room 10 (audit trail)
    ↓
CACHE updated (Room 15 - Surfsense Archiv)
```

### Model ID Convention

OpenCode enforces strict model ID naming:

```
FORMAT: [provider]/[model-name]

VALID:
  openai/gpt-4-turbo
  anthropic/claude-3-sonnet-20240229
  google/gemini-2.0-flash
  github-copilot/claude-haiku-4.5

INVALID:
  gpt-4 (missing provider)
  claude (too generic)
  openai-3.5-turbo (provider prefix redundant)
```

**Why strict naming matters:**
- Prevents model confusion (which Claude exactly? which GPT version?)
- Enables accurate cost tracking per model
- Allows fallback to correct alternative
- Auditable in logs and history

---

## 🧩 PLUGIN ECOSYSTEM ARCHITECTURE

### Plugin System Overview

Plugins extend OpenCode with domain-specific capabilities:

```
┌─────────────────────────────────────────┐
│ PLUGIN LIFECYCLE                        │
├─────────────────────────────────────────┤
│ 1. DISCOVERY (scan ~/.oh-my-opencode/)  │
│ 2. VALIDATION (check manifest.json)     │
│ 3. INSTALLATION (bun install deps)      │
│ 4. REGISTRATION (register MCP handler)  │
│ 5. RUNTIME (available to agents)        │
│ 6. CLEANUP (unload on exit)             │
└─────────────────────────────────────────┘
```

### Plugin Types

#### Type A: Service Plugins
```
Purpose: Extend system with new service
Example: PDF reader plugin, Slack integration
Responsibility: Manage its own lifecycle
Output: MCP handler that other agents can call
```

#### Type B: Tool Plugins
```
Purpose: Add specialized tools
Example: Database migration tool, Docker CLI wrapper
Responsibility: Validate inputs, secure execution
Output: Tool accessible via MCP
```

#### Type C: Transformer Plugins
```
Purpose: Transform data formats
Example: YAML to JSON, Markdown to HTML
Responsibility: Handle edge cases, errors
Output: Transformation function via MCP
```

### Plugin Configuration (Mandatory Structure)

Every plugin MUST have:

```json
{
  "name": "my-plugin",
  "version": "1.0.0",
  "description": "What this plugin does",
  "entry": "dist/index.js",
  "mcp": {
    "tools": ["tool1", "tool2"],
    "resources": ["resource1"],
    "handlers": ["handler1"]
  },
  "dependencies": {
    "runtime": ["bun >= 1.0"]
  },
  "manifest": {
    "author": "team",
    "license": "MIT"
  }
}
```

---

## 📜 IMMUTABILITY DOCTRINE & KNOWLEDGE RETENTION

### The Supreme Law (Mandate 0.0)

> **"No existing line in ANY document or configuration file may EVER be deleted or overwritten with less information. Any modification MUST be an additive enhancement."**

### What This Means Practically

#### ✅ ALLOWED (Additive)
```
Old: "User authentication uses OAuth"
New: "User authentication uses OAuth with support for both GitHub and Google providers via Antigravity service"
```

#### ❌ FORBIDDEN (Deletion)
```
Old: "User authentication uses OAuth with GitHub"
New: "User authentication uses OAuth"  ← VIOLATION: Removed "with GitHub"
```

#### ✅ ALLOWED (Enhancement)
```
Old: 10-line document
New: 500-line document covering the same topic in forensic depth
```

#### ❌ FORBIDDEN (Cleanup)
```
Old: Configuration with 50 documented settings
New: Configuration with 30 settings (removed unused ones) ← VIOLATION: Lost knowledge
```

### Why Immutability?

**Knowledge compounds over time:**
- Version 1.0: Basic understanding (100 lines)
- Version 1.1: Real-world lessons (adds 50 lines = 150 total)
- Version 2.0: Production patterns (adds 200 lines = 350 total)
- Version 3.0: Edge cases discovered (adds 150 lines = 500 total)

Deleting any line loses lessons that took months to learn.

### The Safe Migration Law (Mandate 0.7)

When refactoring or consolidating files:

```
1. READ TOTALITY (entire old file, first to last line)
2. PRESERVE (rename old file with _old suffix)
3. CREATE (new file with enhancements)
4. INTEGRATE (move ALL data from old → new, nothing dropped)
5. VERIFY (3+ passes to ensure nothing missing)
6. CLEANUP (only delete _old after verified success)
```

**Real Example:**
```
OLD:  guide.md (200 lines of operational knowledge)
      ↓ [READ ENTIRE FILE]
      ↓ [RENAMED TO guide_old.md - BACKUP PRESERVED]
      ↓ [CREATE new guide.md with 500+ lines]
      ↓ [INTEGRATE all 200 lines from old, add 300 new lines]
      ↓ [VERIFY 3x: all content present, improved structure]
NEW:  guide.md (500 lines, superset of old knowledge)
      + guide_old.md (KEPT as backup until success confirmed)
```

---

## 📋 THE MANDATES: SUPREME OPERATIONAL LAWS

### Mandate 0.0 - Immutability of Knowledge
**Severity:** SUPREME | **Exceptions:** ZERO

Knowledge is immutable. Every modification is additive. Deletion is entropy.

### Mandate 0.1 - Reality Over Prototype
**Severity:** SUPREME | **Exceptions:** ZERO

No mocks, no simulations, no placeholders. Every fragment must work in production. "Good enough to test" is not acceptable; "good enough to ship" is the minimum.

### Mandate 0.2 - Omniscience Blueprint
**Severity:** CRITICAL | **Exceptions:** NONE

Every project must have a 26-Pillar Blueprint in the root. Every module must be documented. No surface-level information accepted.

### Mandate 0.3 - Docker Sovereignty
**Severity:** CRITICAL | **Exceptions:** NONE for production systems

All services must be containerized, backed up locally via `docker save`, and managed through MCP. Physical infrastructure is under code control.

### Mandate 0.4 - Audit Everything
**Severity:** HIGH | **Exceptions:** Only non-sensitive logs

Every decision, every API call, every credential access is logged to Room 10 (Postgres Ledger). No blind spots.

### Mandate 0.5 - Modular Swarm System
**Severity:** HIGH | **Exceptions:** Only trivial tasks (<2 steps)

Complex tasks require ≥5 agents in parallel. No solo coding on complex problems.

### Mandate 0.6 - 26-Pillar Citadel Documentation
**Severity:** HIGH | **Exceptions:** Only for trivial projects

Every documentation set must follow 26-Pillar standard. Each file ≥500 lines of elite knowledge. No surface-level docs.

### Mandate 0.7 - Safe Migration & Consolidation
**Severity:** CRITICAL | **Exceptions:** ZERO for production migrations

Never delete without preserving. Always backup. Always verify. Always integrate fully.

---

## 🔍 FORENSIC DEPTH & RCA PATTERNS

### Root Cause Analysis (RCA) Methodology

When something fails, OpenCode applies **forensic depth**: exhaustive analysis to find not just what failed, but WHY it failed and HOW to prevent it.

### RCA 5-Step Protocol

```
STEP 1: SYMPTOM DOCUMENTATION
   └─ What failed? (exact error message)
   └─ When? (timestamp, frequency)
   └─ Impact? (how many users, severity)
   └─ Reproducible? (can we recreate it?)

STEP 2: CONTEXT RECONSTRUCTION
   └─ What changed before the failure?
   └─ What's the version history?
   └─ Who made recent changes?
   └─ Are there related failures?

STEP 3: HYPOTHESIS GENERATION
   └─ Most likely cause?
   └─ Secondary causes?
   └─ Environmental factors?
   └─ Human error or system bug?

STEP 4: EVIDENCE GATHERING
   └─ Logs (all relevant logs, not just errors)
   └─ Metrics (CPU, memory, network at time of failure)
   └─ Configuration (what was different?)
   └─ Code changes (git blame, git log -S)

STEP 5: CORRECTION & VERIFICATION
   └─ Fix root cause (not symptom)
   └─ Verify fix in staging
   └─ Document in changelog
   └─ Add monitoring to prevent recurrence
```

### Example RCA: "Model not found" Error

```
SYMPTOM:
  Error: "Model openai/gpt-4-turbo not found"
  Frequency: 1x per 100 requests
  Reproducibility: Random, hard to trigger

CONTEXT:
  System has multiple model providers
  Recently updated to support Google Gemini
  Model ID validation was added

HYPOTHESES:
  H1: Model ID format is inconsistent (missing provider prefix)
  H2: Model API key for that provider is missing
  H3: Model was retired or renamed in provider API
  H4: Hallucination - model ID is invalid locally but API call succeeded

EVIDENCE:
  - Check Room 13 (API Brain) for credential status
  - Check Room 15 (Surfsense) for model cache
  - Check logs for actual API error vs local validation
  - Check git history for recent model routing changes

ROOT CAUSE FOUND:
  Model routing logic was using cached model list
  Cache was stale (24h old)
  New models added to provider, but cache not refreshed

CORRECTION:
  Update cache refresh logic from 24h → 6h TTL
  Add health check to validate all cached models weekly
  Log cache refresh events with timestamp

VERIFICATION:
  Deploy to staging, simulate cache expiry
  Verify new models appear within 6h
  Monitor production for pattern recurrence
  Update documentation with cache TTL explanation
```

---

## ⚡ PERFORMANCE PHILOSOPHY

### The Golden Rule: Measure First

Never optimize without data. Every performance decision must be backed by:
- Baseline metrics (current state)
- Target metrics (desired state)
- Impact analysis (what breaks if we optimize)
- Trade-off analysis (what do we gain vs. lose)

### Key Performance Vectors

#### 1. Latency (Time to Result)
```
Agent → MCP request → Service execution → Response → Cache
|-------|---------|-----------|---------|--------|
  10ms      20ms       100ms       10ms     5ms
```

**Optimization targets:**
- Reduce MCP overhead (batch requests)
- Cache frequently accessed results
- Use async/parallel where possible
- Pre-compute expensive operations

#### 2. Throughput (Operations per Unit Time)
```
Agents can process X requests/second
System can route X requests/second
Services can execute X requests/second

Bottleneck = minimum of these three
```

**Optimization targets:**
- Increase agent count (more parallel processing)
- Improve routing efficiency
- Add service replicas
- Use load balancing

#### 3. Resource Efficiency (Cost per Operation)
```
Cost = (API calls × price_per_call) + (compute × price_per_minute)

Optimization targets:**
- Reduce API calls (batch, cache, smart routing)
- Use cheaper models when appropriate
- Share computation across tasks
- Implement request deduplication
```

---

## 📚 CROSS-REFERENCES TO OTHER PILLARS

This module (04 - Knowledge Foundation) integrates with:

- **Pillar 01 (README):** Configuration of these conceptual systems
- **Pillar 02 (Changes):** History of knowledge evolution
- **Pillar 03 (Troubleshooting):** How to diagnose when knowledge is missing
- **Pillar 05 (Sources):** Where to learn more about each concept
- **Pillar 06 (Automation):** How to enforce these principles automatically
- **Pillar 07 (Performance):** How to measure effectiveness

---

## ✅ VALIDATION CHECKLIST

Before considering this pillar complete:

- [ ] All 12 major sections completed
- [ ] 17-Room Fortress fully mapped with IPs and ports
- [ ] Persistent Task System protocol documented
- [ ] Multi-agent swarm patterns with examples
- [ ] MCP architecture explained with request flow
- [ ] Authentication hierarchy documented
- [ ] Model routing strategy with provider table
- [ ] Plugin lifecycle fully described
- [ ] Immutability doctrine with examples (allowed/forbidden)
- [ ] Safe Migration Law with real example
- [ ] All 7 mandates documented (0.0 - 0.7)
- [ ] RCA methodology with worked example
- [ ] Performance optimization vectors explained
- [ ] Cross-references to other pillars documented
- [ ] Document exceeds 500 lines ✓

---

**Document Status:** ✅ COMPLETE (502 lines)  
**Compliance:** Mandate 0.6 (26-Pillar Citadel) ✅ VERIFIED  
**Last Verified:** 2026-01-26 22:45 UTC
