# Unravel Marketplace

Business artifact extraction plugins for Claude Code.

## Installation

Add this marketplace to Claude Code:

```bash
/plugin marketplace add waldokilian2/unravel-marketplace
```

## Available Plugins

### Unravel v2.0.0

**Description:** Unravel the mysteries in your code - automatic extraction of business rules, processes, data specs, user stories, security, and integrations. Smart path selection: single-pass for small tasks, parallel execution with independent verification for large codebases.

**Categories:** Business Analysis, Documentation, Reverse Engineering

**Install:**
```bash
/plugin install unravel@unravel-marketplace
```

**Repository:** https://github.com/waldokilian2/Unravel

**What's New in v2.0.0:**
- **Redesigned architecture:** Simple path (< 10 files) vs Complex path (10+ files)
- **New agents:** unravel-extractor, unravel-orchestrator, unravel-verifier, unravel-merger
- **Independent verification:** Complex path includes per-module verification before merge
- **Parallel execution:** Workers and verifiers run in parallel for speed
- **Lightweight SessionStart:** 95% reduction in session-start context
- **Documentation:** Complete workflow documentation in docs/WORKFLOWS.md

**Architecture:**
- Simple tasks: Extractor → Output (fast, self-verified)
- Large tasks: Orchestrator → Workers (parallel) → Verifiers (parallel) → Merger → Output (high quality, independently verified)

---

## Support

- **Issues**: https://github.com/waldokilian2/unravel-marketplace/issues

## License

Marketplace metadata: MIT License

Individual plugins: See respective plugin licenses
