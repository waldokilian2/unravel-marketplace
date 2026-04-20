# Unravel Marketplace

Claude Code plugins for productivity — business analysis, prompt quality coaching, and more.

## Installation

Add this marketplace to Claude Code:

```bash
/plugin marketplace add waldokilian2/unravel-marketplace
```

## Available Plugins

### Unravel v2.4.0

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

**Synthesis Outputs:**

| Document | Combines | Output |
|----------|----------|--------|
| REQUIREMENTS.md | business-rules, user-stories, security-nfrs, process-flows | Functional and non-functional requirements |
| ARCHITECTURE.md | dependency-map, integrations, process-flows, data-specs | System architecture overview |
| DATA-DICTIONARY.md | data-specs, domain-vocabulary | Unified data reference |
| SECURITY-AUDIT.md | security-nfrs, integrations, api-contracts | Security and compliance review |
| TEST-PLAN.md | test-coverage, business-rules, user-stories | Prioritized test plan |
| **BUSINESS-SPEC.md** | **ALL 11 extraction types** | **Complete business specification** |

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
| synthesize-requirements | Combine business-rules, user-stories, security-nfrs, process-flows into requirements document |
| synthesize-architecture | Combine dependency-map, integrations, process-flows, data-specs into architecture overview |
| synthesize-data-dictionary | Combine data-specs and domain-vocabulary into unified data dictionary |
| synthesize-security-audit | Combine security, integrations, and API contracts into security audit |
| synthesize-test-plan | Combine test coverage, rules, and stories into prioritized test plan |
| synthesize-business-spec | **NEW:** Combine ALL 11 extraction types into comprehensive business specification |

---

### Qwack v1.0.0

**Description:** Your sassy duck prompt quality coach. Automatically evaluates your first message of each session and roasts you (lovingly) when your prompt is garbage — then fixes it for you.

**Categories:** Productivity, Education, Prompt Engineering

**Install:**
```bash
/plugin install qwack@unravel-marketplace
```

**Repository:** https://github.com/waldokilian2/qwack

**What Qwack Detects:**

| Issue | Example |
|-------|---------|
| Vague requests | "fix everything", "make it better" |
| Missing context | No file paths, no background info |
| Contradictions | "make it fast but also add every feature" |
| Redundancy | Repeating the same thing multiple ways |
| Unnecessary info | Long stories, tangential details |

**How It Works:**
1. Automatic evaluation of first message per session
2. Sassy duck feedback with specific complaints
3. Copyable, optimized prompt provided
4. One-click acceptance to proceed with improved version
5. Bypass with "quack: off" anywhere in message

**Example Output:**
```
🦆 *QUACK!* Excuse me?! What even IS this?! 🦆
============================================================

Oh sweet mother of mallard, you want me to "fix the code" but you
can't even be bothered to tell me WHICH file? WHAT's broken?

============================================================

📝 IMPROVED PROMPT:
I need help debugging src/auth/login.js - getting 401 errors...

🦆 Want to proceed with improved prompt? (yes/no)
```

---

## Support

- **Issues**: https://github.com/waldokilian2/unravel-marketplace/issues

## License

Marketplace metadata: MIT License

Individual plugins: See respective plugin licenses
