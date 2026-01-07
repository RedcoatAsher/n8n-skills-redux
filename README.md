# n8n-skills-redux

**Expert Claude Code skills for building flawless n8n workflows with automatic workflow hardening using the `n8n-mcp` MCP server**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![n8n-mcp](https://img.shields.io/badge/n8n--mcp-compatible-green.svg)](https://github.com/czlonkowski/n8n-mcp)

---

## 🎯 What is this?

This repository contains 5 complementary **Claude Code skills** that teach AI assistants how to build production-ready n8n workflows using the [n8n-mcp](https://github.com/czlonkowski/n8n-mcp) MCP server.

### Why These Skills Exist

Building n8n workflows programmatically can be challenging. Common issues include:
- Using MCP tools incorrectly or inefficiently
- Getting stuck in validation error loops
- Not knowing which workflow patterns to use
- Misconfiguring nodes and their dependencies

These skills solve these problems by teaching Claude:
- ✅ Correct n8n expression syntax ({{}} patterns)
- ✅ How to use n8n-mcp tools effectively
- ✅ Proven workflow patterns from real-world usage
- ✅ Validation error interpretation and fixing
- ✅ Operation-aware node configuration

---

## 📚 The 8 Skills

### 1. **n8n Expression Syntax**
Teaches correct n8n expression syntax and common patterns.

**Activates when**: Writing expressions, using {{}} syntax, accessing $json/$node variables, troubleshooting expression errors.

**Key Features**:
- Core variables ($json, $node, $now, $env)
- **Critical gotcha**: Webhook data is under `$json.body`
- Common mistakes catalog with fixes
- When NOT to use expressions (Code nodes!)

### 2. **n8n MCP Tools Expert** (HIGHEST PRIORITY)
Expert guide for using n8n-mcp MCP tools effectively.

**Activates when**: Searching for nodes, validating configurations, accessing templates, managing workflows.

**Key Features**:
- Tool selection guide (which tool for which task)
- nodeType format differences (nodes-base.* vs n8n-nodes-base.*)
- Validation profiles (minimal/runtime/ai-friendly/strict)
- Smart parameters (branch="true" for IF nodes)
- Auto-sanitization system explained

**Most Important**: Teaches correct MCP tool usage patterns and parameter formats

### 3. **n8n Workflow Patterns**
Build workflows using 5 proven architectural patterns.

**Activates when**: Creating workflows, connecting nodes, designing automation.

**Key Features**:
- 5 proven patterns (webhook processing, HTTP API, database, AI, scheduled)
- Workflow creation checklist
- Real examples from 2,653+ n8n templates
- Connection best practices
- Pattern selection guide

### 4. **n8n Validation Expert**
Interpret validation errors and guide fixing.

**Activates when**: Validation fails, debugging workflow errors, handling false positives.

**Key Features**:
- Validation loop workflow
- Real error catalog
- Auto-sanitization behavior explained
- False positives guide
- Profile selection for different stages

### 5. **n8n Node Configuration**
Operation-aware node configuration guidance.

**Activates when**: Configuring nodes, understanding property dependencies, setting up AI workflows.

**Key Features**:
- Property dependency rules (e.g., sendBody → contentType)
- Operation-specific requirements
- AI connection types (8 types for AI Agent workflows)
- Common configuration patterns

### 6. **n8n Code JavaScript**
Write effective JavaScript code in n8n Code nodes.

**Activates when**: Writing JavaScript in Code nodes, troubleshooting Code node errors, making HTTP requests with $helpers, working with dates.

**Key Features**:
- Data access patterns ($input.all(), $input.first(), $input.item)
- **Critical gotcha**: Webhook data under `$json.body`
- Correct return format: `[{json: {...}}]`
- Built-in functions ($helpers.httpRequest(), DateTime, $jmespath())
- Top 5 error patterns with solutions (covering 62%+ of failures)
- 10 production-tested patterns

### 7. **n8n Code Python**
Write Python code in n8n Code nodes with proper limitations awareness.

**Activates when**: Writing Python in Code nodes, need to know Python limitations, working with standard library.

**Key Features**:
- **Important**: Use JavaScript for 95% of use cases
- Python data access (_input, _json, _node)
- **Critical limitation**: No external libraries (requests, pandas, numpy)
- Standard library reference (json, datetime, re, etc.)
- Workarounds for missing libraries
- Common Python patterns for n8n

### 8. **n8n Production Readiness** (NEW)
Dynamic tier system for right-sizing n8n workflow hardening.

**Activates when**: Building any n8n workflow, deploying to production, debugging silent failures, handling client projects.

**Key Features**:
- **Tier system**: Match hardening to actual risk (Tier 1-3)
- **Smart detection**: Infers appropriate tier from context
- **Autopilot mode**: Adapts silently as you build
- **The 80/20 rule**: Core logic is 20%, hardening is 80% for production
- Entry-point validation patterns
- External logging (Supabase/Postgres)
- HTTP status codes (400, 401, 404, 500)
- Pre-deployment checklists by tier
- Example workflows for each tier

---

## 🚀 Installation

### Prerequisites

1. **n8n-mcp MCP server** installed and configured ([Installation Guide](https://github.com/czlonkowski/n8n-mcp))
2. **Claude Code**, Claude.ai, or Claude API access
3. `.mcp.json` configured with n8n-mcp server

### Claude Code

**Manual Installation**
```bash
# 1. Clone this repository
git clone https://github.com/RedcoatAsher/n8n-skills-redux.git

# 2. Copy skills to your Claude Code skills directory
cp -r n8n-skills/skills/* ~/.claude/skills/

# 3. Reload Claude Code
# Skills will activate automatically
```

### Claude.ai

1. Download individual skill folders from `skills/`
2. Zip each skill folder
3. Upload via Settings → Capabilities → Skills

### API / SDK

See [docs/INSTALLATION.md](docs/INSTALLATION.md) for detailed instructions.

---

## 💡 Usage

Skills activate **automatically** when relevant queries are detected:

```
"How do I write n8n expressions?"
→ Activates: n8n Expression Syntax

"Find me a Slack node"
→ Activates: n8n MCP Tools Expert

"Build a webhook workflow"
→ Activates: n8n Workflow Patterns

"Why is validation failing?"
→ Activates: n8n Validation Expert

"How do I configure the HTTP Request node?"
→ Activates: n8n Node Configuration

"How do I access webhook data in a Code node?"
→ Activates: n8n Code JavaScript

"Can I use pandas in Python Code node?"
→ Activates: n8n Code Python

"I need to deploy this workflow for a client"
→ Activates: n8n Production Readiness
```

### Skills Work Together

When you ask: **"Build and validate a webhook to Slack workflow for my client"**

1. **n8n Production Readiness** asks about tier (detects "client" → suggests Tier 2)
2. **n8n Workflow Patterns** identifies webhook processing pattern
3. **n8n MCP Tools Expert** searches for webhook and Slack nodes
4. **n8n Node Configuration** guides node setup
5. **n8n Code JavaScript** helps process webhook data with proper .body access
6. **n8n Expression Syntax** helps with data mapping in other nodes
7. **n8n Validation Expert** validates the final workflow
8. **n8n Production Readiness** provides pre-deployment checklist

All skills compose seamlessly!

---

## 📖 Documentation

- [Installation Guide](docs/INSTALLATION.md) - Detailed installation for all platforms
- [Usage Guide](docs/USAGE.md) - How to use skills effectively
- [Development Guide](docs/DEVELOPMENT.md) - Contributing and testing
- [MCP Testing Log](docs/MCP_TESTING_LOG.md) - Real tool responses used in skills

---


## 🧪 Testing

Each skill includes 3+ evaluations for quality assurance:

```bash
# Run evaluations (if testing framework available)
npm test

# Or manually test with Claude
claude-code --skill n8n-expression-syntax "Test webhook data access"
```

---


### Development Approach

1. **Evaluation-First**: Write test scenarios before implementation
2. **MCP-Informed**: Test tools, document real responses
3. **Iterative**: Test against evaluations, iterate until 100% pass
4. **Concise**: Keep SKILL.md under 500 lines
5. **Real Examples**: All examples from real templates/tools

---

## 📝 License

MIT License - see [LICENSE](LICENSE) file for details.

---

## 🙏 Credits

**Expanded by Asher Peruscini**
- Website: [www.rivit.studio](https://www.rivit.studio/)

**Originally conceived by Romuald Członkowski**
- Website: [www.aiadvisors.pl/en](https://www.aiadvisors.pl/en)
- Part of the [n8n-mcp project](https://github.com/czlonkowski/n8n-mcp)

---

## 🔗 Related Projects

- [n8n-mcp](https://github.com/czlonkowski/n8n-mcp) - MCP server for n8n
- [n8n](https://n8n.io/) - Workflow automation platform

---

## 📊 What's Included

- **8** complementary skills that work together
- **525+** n8n nodes supported
- **2,653+** workflow templates for examples
- **14** production-tested Code node patterns (including validation & logging)
- **3-tier** production readiness system
- **Comprehensive** error catalogs and troubleshooting guides

---

**Ready to build flawless, hardened n8n workflows? Get started now!** 🚀
