# Unravel Marketplace

Business artifact extraction plugins for Claude Code.

## Installation

Add this marketplace to Claude Code:

```bash
/plugin marketplace add waldokilian2/unravel-marketplace
```

## Available Plugins

### Unravel v1.1.0

**Description:** Unravel the mysteries in your code - automatic extraction of business rules, processes, data specs, user stories, security, and integrations. Now with subagent orchestration model - every extraction uses fresh subagents with two-stage review (spec compliance + quality).

**Categories:** Business Analysis, Documentation, Reverse Engineering

**Install:**
```bash
/plugin install unravel@unravel-marketplace
```

**Repository:** https://github.com/waldokilian2/Unravel

**What's New in v1.1.0:**
- Subagent orchestration model (always-on)
- 9 new agent templates (extractors + reviewers)
- 4 new orchestration skills (planning, dispatch, orchestration, verification)
- 3 new commands (/extract, /parallel-extract, /verify)
- Two-stage review: spec compliance → quality
- Parallel execution for independent files

---

## Support

- **Issues**: https://github.com/waldokilian2/unravel-marketplace/issues

## License

Marketplace metadata: MIT License

Individual plugins: See respective plugin licenses
