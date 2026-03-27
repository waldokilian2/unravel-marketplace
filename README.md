# Unravel Marketplace

Business artifact extraction plugins for Claude Code.

## Installation

Add this marketplace to Claude Code:

```bash
/plugin marketplace add waldokilian2/unravel-marketplace
```

## Available Plugins

### Unravel v2.3.0

**Description:** Turn source code into business documentation. Extracts structured artifacts — business rules, process flows, data specs, user stories, security/NFRs, and integrations — from any codebase. Multi-language support (TypeScript, JavaScript, Python, Go, Java).

**Categories:** Business Analysis, Documentation, Reverse Engineering

**Install:**
```bash
/plugin install unravel@unravel-marketplace
```

**Repository:** https://github.com/waldokilian2/unravel

**What It Extracts:**

| Artifact | What You Get |
|----------|-------------|
| Business Rules | Validation constraints, access controls, error conditions |
| Process Flows | Function call chains, state machines, decision paths |
| Data Specs | Schemas, ORM models, DTOs, relationships |
| User Stories | End-user actions from controllers, routes, CLI handlers |
| Security / NFRs | Auth patterns, rate limits, encryption, logging |
| Integrations | HTTP clients, database connections, external services |

**How It Works:**
1. Select artifact categories (or extract everything)
2. Choose verification level (self-verify or independent verification)
3. Unravel discovers files, groups them into modules, extracts in parallel batches
4. Optional verification catches errors and auto-fixes them
5. Results saved to `docs/output/` with an optional executive summary

**Agents:**

| Agent | Role |
|-------|------|
| unravel-extractor | Extract patterns from files per module with self-verification |
| unravel-verifier | Independently verify extraction outputs (optional) |
| unravel-fixer | Surgically fix issues when verification fails (automatic) |
| unravel-summarizer | Create executive summary from all outputs (optional) |

**Skills:**

| Skill | Purpose |
|-------|---------|
| using-unravel | Entry point — artifact selection, verification preference |
| orchestrating-extraction | Per-type workflow — discovery, batching, verification, index |
| extract-business-rules | Business rules domain knowledge |
| extract-process-flows | Process flows domain knowledge |
| extract-data-specs | Data specs domain knowledge |
| extract-user-stories | User stories domain knowledge |
| extract-security-nfrs | Security and NFRs domain knowledge |
| extract-integrations | Integrations domain knowledge |

---

## Support

- **Issues**: https://github.com/waldokilian2/unravel-marketplace/issues

## License

Marketplace metadata: MIT License

Individual plugins: See respective plugin licenses
