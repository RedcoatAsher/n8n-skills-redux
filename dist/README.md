# n8n-mcp Skills - Distribution Packages

This folder contains distribution packages for different Claude platforms.

## 📦 Available Packages

All 8 skills are available as individual packages (v1.1.0):

| Package | Size | Description |
|---------|------|-------------|
| `n8n-expression-syntax-v1.1.0.zip` | 7 KB | n8n expression syntax and common patterns |
| `n8n-mcp-tools-expert-v1.1.0.zip` | 8 KB | Expert guide for using n8n-mcp tools |
| `n8n-workflow-patterns-v1.1.0.zip` | 8 KB | Proven workflow architectural patterns |
| `n8n-validation-expert-v1.1.0.zip` | 8 KB | Validation error interpretation and fixing |
| `n8n-node-configuration-v1.1.0.zip` | 8 KB | Operation-aware node configuration |
| `n8n-code-javascript-v1.1.0.zip` | 9 KB | JavaScript code in n8n Code nodes |
| `n8n-code-python-v1.1.0.zip` | 9 KB | Python code in n8n Code nodes |
| `n8n-production-readiness-v1.1.0.zip` | 10 KB | Dynamic tier system for right-sizing workflow hardening |

## 🎯 Installation

### For Claude.ai Users

Upload each skill via Settings → Capabilities → Skills (bottom of page):

1. Go to Settings → Capabilities → Skills (bottom of page)
2. Click "Upload Skill"
3. Select one of the skill zip files above
4. Repeat for each skill you want to install

**Recommended install order:**
1. `n8n-mcp-tools-expert` — Foundation for using n8n-mcp tools effectively
2. `n8n-production-readiness` — Tier system for right-sizing workflow hardening
3. Other skills as needed for your use case

### For Claude Code Users

```bash
# Plugin installation from GitHub
/plugin install czlonkowski/n8n-skills

# Or install from local file
/plugin install /path/to/skill.zip
```

### For Claude API Users

Extract the `skills/` folder from any package and include in your system prompt.

---

## 📁 Files in This Directory

```
dist/
├── n8n-expression-syntax-v1.1.0.zip      (7 KB)
├── n8n-mcp-tools-expert-v1.1.0.zip       (8 KB)
├── n8n-workflow-patterns-v1.1.0.zip      (8 KB)
├── n8n-validation-expert-v1.1.0.zip      (8 KB)
├── n8n-node-configuration-v1.1.0.zip     (8 KB)
├── n8n-code-javascript-v1.1.0.zip        (9 KB)
├── n8n-code-python-v1.1.0.zip            (9 KB)
├── n8n-production-readiness-v1.1.0.zip   (10 KB)
└── README.md                              (this file)
```

---


## 📋 What's Included in Each Package

Each zip contains:
```
SKILL.md              # Main skill instructions with YAML frontmatter
[Reference files]     # Additional documentation and guides
README.md             # Skill metadata and statistics
```


## ✅ Verification

After installation, test skills by asking:

```
"How do I write n8n expressions?"
→ Should activate: n8n Expression Syntax

"Find me a Slack node"
→ Should activate: n8n MCP Tools Expert

"Build a webhook workflow"
→ Should activate: n8n Workflow Patterns

"How do I access webhook data in a Code node?"
→ Should activate: n8n Code JavaScript

"Can I use pandas in Python Code node?"
→ Should activate: n8n Code Python

"Build me a production-ready workflow for handling customer orders"
→ Should activate: n8n Production Readiness
```


## 🔧 Requirements

- **n8n-mcp MCP server** installed and configured ([Installation Guide](https://github.com/czlonkowski/n8n-mcp))
- **Claude Pro, Max, Team, or Enterprise** plan (for Claude.ai skills)
- **.mcp.json** configured with n8n-mcp server


## 📖 Documentation

For detailed installation instructions, see:
- Main README: `../README.md`
- Installation Guide: `../docs/INSTALLATION.md`
- Usage Guide: `../docs/USAGE.md`


## 🐛 Troubleshooting

**Claude.ai Error: "Zip must contain exactly one SKILL.md file"**
- Use the individual skill zips
- Each skill must be uploaded separately

**Claude Code: Skills not activating**
- Verify skills are in `~/.claude/skills/` directory
- Check that n8n-mcp MCP server is running
- Reload Claude Code

**Skills not triggering**
- Skills activate based on keywords in your queries
- Try more specific questions matching skill descriptions
- Check that SKILL.md files have correct frontmatter


## 📝 License

MIT License - see `../LICENSE` file


## 🙏 Credits

Expanded by Asher Peruscini – https://rivit.studio/

Originally conceived by Romuald Członkowski - https://www.aiadvisors.pl/en

Part of the [n8n-mcp project](https://github.com/czlonkowski/n8n-mcp).
