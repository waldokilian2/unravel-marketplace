# Unravel Marketplace

Business artifact extraction plugins for Claude Code.

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

## Support

- **Issues**: https://github.com/waldokilian2/unravel-marketplace/issues

## License

Marketplace metadata: MIT License

Individual plugins: See respective plugin licenses
