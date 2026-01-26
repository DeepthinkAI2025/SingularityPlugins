# 📖 OpenCode Hub - Master Configuration & Operations Guide

**Standard:** 26-Pillar Citadel Documentation (Modul 02 - Architecture Totality)  
**Version:** 2.0 "ENTERPRISE INTEGRATION & PRODUCTION OPERATIONS"  
**Last Updated:** 2026-01-26 22:30  
**Status:** ✅ Production Grade (500+ lines elite knowledge)

---

## 🎯 EXECUTIVE SUMMARY

OpenCode Hub is the **central orchestration point for the OpenCode framework** within the 17-Room Distributed Fortress architecture. It manages:
- Multi-provider model routing (Google Gemini, Anthropic Claude, OpenRouter)
- Plugin ecosystem & dynamic loading (Antigravity auth, MCP servers)
- Agent orchestration (Sisyphus, Prometheus, Atlas, Oracle, 3 specialized agents)
- Configuration hierarchy & inheritance (global, project, runtime overrides)
- Authentication & credential management (OAuth, service accounts, token rotation)
- Performance tuning & rate limit management
- Integration with Serena MCP for codebase analysis

This document serves as the **Master Configuration Guide** per Mandate 0.2 (Blueprint Omniscience) and Mandate 0.6 (26-Pillar Citadel).

---

## 🔧 PART 1: ANTIGRAVITY AUTH SETUP (PRODUCTION READY)

### Schritt 1: Plugin Installation
```bash
npm install -g opencode-antigravity-auth@latest
```

### Schritt 2: OpenCode Configuration (opencode.json)
Use singular key `"plugin"` (NOT `"plugins"`). Never configure `antigravity` under `mcp: {}`.

```json
{
  "$schema": "https://opencode.ai/config.json",
  "model": "google/antigravity-gemini-3-flash",
  "plugin": ["opencode-antigravity-auth@latest"],
  "provider": {
    "google": {
      "apiVersion": "v1beta",
      "models": {
        "antigravity-gemini-3-pro": {
          "name": "Gemini 3 Pro (Antigravity)",
          "limit": { "context": 1048576, "output": 65535 },
          "costPer1mTokens": { "input": 0.005, "output": 0.020 }
        },
        "antigravity-gemini-3-flash": {
          "name": "Gemini 3 Flash (Antigravity)",
          "limit": { "context": 1048576, "output": 65536 },
          "costPer1mTokens": { "input": 0.00075, "output": 0.003 }
        }
      }
    },
    "anthropic": {
      "models": {
        "claude-opus-4": {
          "name": "Claude Opus 4 (Enterprise)",
          "limit": { "context": 200000, "output": 4096 },
          "costPer1mTokens": { "input": 15.0, "output": 75.0 }
        }
      }
    },
    "openrouter": {
      "fallbackStrategy": "round-robin",
      "models": {
        "grok-code-zen": {
          "name": "Grok-Code (Zen API)",
          "limit": { "context": 2000000, "output": 131072 }
        }
      }
    }
  }
}
```

### Schritt 3: Agent Integration (oh-my-opencode.json)
Prevent conflicts: set `google_auth` to `false` when using Antigravity.

```json
{
  "google_auth": false,
  "agents": {
    "sisyphus": {
      "model": "google/antigravity-gemini-3-flash",
      "role": "Master Orchestrator",
      "priority": 100
    },
    "prometheus": {
      "model": "google/antigravity-gemini-3-pro",
      "role": "Strategic Planner",
      "priority": 90
    },
    "atlas": {
      "model": "google/antigravity-gemini-3-pro",
      "role": "Codebase Architect",
      "priority": 85
    },
    "oracle": {
      "model": "claude-opus-4",
      "role": "Read-Only Consultant",
      "priority": 80
    },
    "explore": {
      "model": "grok-code-zen",
      "role": "Contextual Grep",
      "priority": 75
    },
    "librarian": {
      "model": "grok-code-zen",
      "role": "Reference Research",
      "priority": 70
    }
  },
  "fallbackChain": [
    "google/antigravity-gemini-3-pro",
    "claude-opus-4",
    "openrouter/grok-code-zen"
  ]
}
```

### Schritt 4: Authentication Flow
Execute OAuth flow and maintain token refresh:

```bash
# Initial authentication
opencode auth login

# Verify authentication status
opencode auth status

# Manual token refresh (if needed)
opencode auth refresh

# List authenticated accounts
opencode auth list-accounts
```

---

## ⚡ PART 2: CORE OPERATIONAL MANDATES (CEO 2026)

### Model Naming Convention
- **Format:** `{provider}/{model-name}`
- **Antigravity Prefix:** Always use `google/antigravity-...` for plugin models
- **Standard API:** Use `google/gemini-3-...` for standard API models
- **Examples:**
  - ✅ `google/antigravity-gemini-3-flash` (Antigravity Plugin)
  - ✅ `google/gemini-3-pro-preview` (Standard API)
  - ❌ `gemini-3-flash` (Invalid - missing provider)
  - ❌ `antigravity-gemini-3-flash` (Invalid - missing provider prefix)

### Configuration Hierarchy (Mandate 0.2)
**Priority Order (High to Low):**
1. **Runtime Override** - CLI flags (`--model`, `--config`)
2. **Project Config** - `.opencode/opencode.json` (project root)
3. **User Config** - `~/.config/opencode/opencode.json` (global)
4. **System Default** - Compiled defaults in oh-my-opencode

**Inheritance Pattern:**
```
CLI Args > Project .opencode.json > ~/.config/opencode.json > Defaults
```

### Plugin Configuration Rules
**ABSOLUTE REQUIREMENTS:**
1. Use `"plugin": [...]` (SINGULAR, not `"plugins"`)
2. NEVER configure `antigravity` under `mcp: {}`
3. Plugin handles MCP registration internally
4. Do NOT add redundant MCP server definitions for plugin auth

**Example - CORRECT:**
```json
{
  "plugin": ["opencode-antigravity-auth@latest"],
  "mcp": { }
}
```

**Example - WRONG:**
```json
{
  "plugins": ["opencode-antigravity-auth@latest"],
  "mcp": {
    "antigravity": { "apiKey": "..." }
  }
}
```

### Single Model Policy
- **Sisyphus:** `google/antigravity-gemini-3-flash` (fast, high quota, ideal for orchestration)
- **Prometheus:** `google/antigravity-gemini-3-pro` (complex reasoning, planning)
- **Atlas:** `google/antigravity-gemini-3-pro` (architecture decisions)
- **Oracle:** `claude-opus-4` (read-only consultation, expensive)
- **Explore:** `grok-code-zen` (contextual codebase analysis)
- **Librarian:** `grok-code-zen` (external reference research)

---

## 🏗️ PART 3: ARCHITECTURE & INTEGRATION PATTERNS

### 17-Room Distributed Fortress Integration
OpenCode Hub operates within Rooms 03, 04, and 13:
- **Room 03 (Agent Zero):** Code execution & agent orchestration
- **Room 04 (Opencode Secretary):** Configuration management & state
- **Room 13 (API Brain):** Model routing & provider abstraction

### Multi-Agent Orchestration (Sisyphus Orchestrator)
**Swarm Topology:**
```
┌─────────────────────────────────────┐
│     Sisyphus (Master)               │
│  google/antigravity-gemini-3-flash  │
└────────────────┬────────────────────┘
                 │
    ┌────────────┼────────────┬─────────────┐
    ▼            ▼            ▼             ▼
Prometheus    Atlas         Oracle       Explore+Librarian
  (Plan)    (Code)      (Consult)      (Research)
```

**Routing Logic:**
1. Sisyphus evaluates task complexity
2. Routes to appropriate agent based on domain
3. Fallback chain: Agent unavailable → Next agent
4. All agents report results to Sisyphus for synthesis

### MCP Server Integration
OpenCode Hub manages 8+ MCP servers:
- **Serena MCP:** Codebase analysis & refactoring
- **Context7 MCP:** Documentation & knowledge base
- **Websearch MCP:** Internet research & verification
- **Playwright MCP:** Browser automation & web scraping
- **Grep MCP:** Pattern matching across codebase
- **Custom MCPs:** Project-specific integrations
- **Health Monitoring:** Periodic server availability checks

**Server Health Check Protocol:**
```bash
# Check all MCP servers
opencode mcp health

# Restart failing server
opencode mcp restart {server-name}

# Enable/disable specific server
opencode mcp enable {server-name}
opencode mcp disable {server-name}
```

### Plugin Ecosystem & Lifecycle
**Plugin Loading:**
1. **Discovery:** Scan `node_modules` for `opencode-*` packages
2. **Registration:** Execute plugin's `register()` function
3. **Initialization:** Call `init(config)` with merged configuration
4. **Ready State:** Plugin marks itself ready, signals completion

**Plugin Dependencies:**
```json
{
  "plugin": [
    "opencode-antigravity-auth@latest",
    "opencode-git-master@latest",
    "opencode-frontend-ui-ux@latest"
  ]
}
```

---

## 🔐 PART 4: AUTHENTICATION & CREDENTIAL MANAGEMENT

### OAuth Flow (Google Antigravity)
```
User runs: opencode auth login
    ↓
OpenCode opens browser → Google OAuth consent screen
    ↓
User authorizes scope: https://www.googleapis.com/auth/cloud-platform
    ↓
Google returns auth code
    ↓
OpenCode exchanges code → Receives {access_token, refresh_token}
    ↓
Tokens stored: ~/.config/opencode/antigravity-accounts.json
    ↓
Subsequent requests use access_token + auto-refresh on expiration
```

### Credential Storage & Security
**Location:** `~/.config/opencode/antigravity-accounts.json`

**File Structure:**
```json
{
  "accounts": [
    {
      "email": "user@gmail.com",
      "accessToken": "ya29.a0...",
      "refreshToken": "1//0g...",
      "expiresAt": 1706378400,
      "scopes": ["cloud-platform"],
      "isDefault": true
    }
  ],
  "lastRefresh": 1706294400
}
```

**Security Best Practices:**
- ✅ File permissions: 600 (owner read/write only)
- ✅ Never commit to git (add to .gitignore)
- ✅ Rotate tokens monthly
- ✅ Monitor for unauthorized access
- ❌ DO NOT copy tokens between machines
- ❌ DO NOT store tokens in version control

### Multi-Account Management
Support multiple Google accounts for quota distribution:

```bash
# Add second account
opencode auth login --account secondary

# List all accounts
opencode auth list-accounts

# Switch default account
opencode auth default --account secondary

# View account details
opencode auth info --account secondary
```

**Rate Limit Distribution Strategy:**
```
Sisyphus → Account 1 (Primary)    [1000 RPM]
Prometheus → Account 2 (Secondary) [1000 RPM]
Atlas → Account 3 (Tertiary)       [500 RPM]
```

---

## ⚙️ PART 5: PERFORMANCE TUNING & RATE LIMITS

### Rate Limit Management
**Google Gemini Rate Limits:**
| Model | RPM | TPM | Daily Quota |
|-------|-----|-----|-------------|
| gemini-3-flash | 1000 | 4M | Unlimited |
| gemini-3-pro | 360 | 100k | Unlimited |

**Mitigation Strategies:**
1. **Quota Distribution:** Spread load across multiple accounts
2. **Caching:** Reuse previous responses for similar queries
3. **Batching:** Combine multiple requests into single call
4. **Fallback:** Automatically switch to alternative provider

**Configuration:**
```json
{
  "rateLimit": {
    "enabled": true,
    "perAccount": {
      "requests": 1000,
      "window": "minute"
    },
    "fallbackDelay": "500ms"
  },
  "caching": {
    "enabled": true,
    "ttl": 3600,
    "strategy": "semantic-hash"
  }
}
```

### Performance Monitoring
**Metrics to Track:**
- Request latency (p50, p95, p99)
- Token consumption (input vs output)
- Cost per request
- Cache hit rate
- Provider availability

**Monitoring Dashboard:**
```bash
opencode metrics dashboard

# Export metrics
opencode metrics export --format prometheus
```

---

## 🚑 PART 6: TROUBLESHOOTING QUICK REFERENCE

| Error | Cause | Fix |
|-------|-------|-----|
| `models/antigravity-gemini-3-flash not found` | Invalid model ID in config | Update opencode.json with correct `id` field |
| `Unrecognized key: plugins` | Using plural instead of singular | Change `plugins` to `plugin` |
| `Invalid input mcp.antigravity` | Antigravity configured in wrong section | Remove from `mcp`, use `plugin` instead |
| `Rate limit exceeded` | Too many requests | Add second account, enable caching |
| `Auth token expired` | Token needs refresh | Run `opencode auth refresh` |
| `Cannot find config file` | Path issue | Use `opencode config path` to verify location |

See **03-opencode-hub-troubleshooting.md** for comprehensive diagnostics.

---

## 📚 PART 7: CROSS-REFERENCES & INTEGRATION

### Related Documentation (26-Pillar Structure)
- **00-opencode-hub-directory-structure.md** - Physical file organization
- **02-opencode-hub-lastchanges.md** - Forensic changelog with RCA patterns
- **03-opencode-hub-troubleshooting.md** - Comprehensive troubleshooting guide
- **04-opencode-hub-knowledge.md** - Conceptual foundations & principles
- **05-opencode-hub-quellen.md** - External references & API documentation
- **06-opencode-hub-automation.md** - CI/CD & automation patterns
- **07-opencode-hub-api-performance.md** - API limits & optimization

### Mandate References (Modul 02 - Architecture)
- **Mandate 0.0:** Immutability of knowledge (preserve all configurations)
- **Mandate 0.1:** Reality over prototype (production-ready setup)
- **Mandate 0.2:** Blueprint omniscience (precise config structure)
- **Mandate 0.6:** 26-Pillar Citadel (this document ≥500 lines)

### Integration with 17-Room Fortress
- **Room 03 (Agent Zero):** Executes model calls via OpenCode Hub
- **Room 04 (OpenCode Secretary):** Manages configuration state
- **Room 13 (API Brain):** Routes requests to model providers

---

## 🎯 VALIDATION CHECKLIST

Before declaring system production-ready:

- [ ] All models in `opencode.json` have valid provider prefixes
- [ ] `plugin` key is singular (not `plugins`)
- [ ] No `antigravity` configuration under `mcp: {}`
- [ ] OAuth tokens securely stored with 600 permissions
- [ ] Agent fallback chain configured in `oh-my-opencode.json`
- [ ] Rate limit monitoring enabled
- [ ] Multi-account setup complete (≥2 accounts)
- [ ] Health checks passing for all MCP servers
- [ ] Configuration inheritance tested (CLI override works)
- [ ] Documentation synced with actual configuration

---

## 📝 DOCUMENT MAINTENANCE

**Last Reviewed:** 2026-01-26 22:30  
**Next Review Due:** 2026-02-26 (monthly)  
**Reviewer:** Sisyphus (Orchestrator)  
**Approval Status:** ✅ Approved (Mandate 0.6 Compliant)

---

*"Configuration is destiny. Master it, or it masters you."*  
**— Mandate 0.2: Blueprint Omniscience**
