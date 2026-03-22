# Unravel Marketplace

Business artifact extraction plugins for Claude Code.

## Installation

Add this marketplace to Claude Code:

```bash
/plugin marketplace add waldokilian2/unravel-marketplace
```

## Available Plugins

### Unravel v2.1.0

**Description:** Unravel the mysteries in your code - automatic extraction of business rules, processes, data specs, user stories, security, and integrations. User selects what to extract, then Unravel handles the rest. Orchestrators run sequential internally; multiple orchestrators can run in parallel (user choice).

**Categories:** Business Analysis, Documentation, Reverse Engineering

**Install:**
```bash
/plugin install unravel@unravel-marketplace
```

**Repository:** https://github.com/waldokilian2/Unravel

**What's New in v2.1.0:**
- **User selection:** Choose which artifact types to extract before starting
- **Executive summaries:** New unravel-summarizer creates high-level overview after extraction
- **Orchestrators run sequential internally:** Workers and verifiers one at a time (respects model limits)
- **Multiple orchestrators:** User chooses parallel or sequential when extracting multiple artifact types
- **Clarified architecture:** One orchestrator per artifact type
- **Improved README:** Step-by-step workflow documentation

**Architecture:**
- Simple tasks (< 10 files): Extractor → Output
- Large tasks (10+ files): Orchestrator → Workers (sequential) → Verifiers (sequential) → Merger → Output
- Multiple types: User chooses parallel or sequential orchestrators
- Optional: Summarizer creates EXECUTIVE-SUMMARY.md after all extractions complete

**Agents:**
- unravel-extractor: Extract patterns from files
- unravel-orchestrator: Coordinate workers, verifiers, and merger
- unravel-verifier: Independently verify extraction outputs
- unravel-merger: Combine verified outputs into final file
- unravel-summarizer: Create executive summary from all outputs

---

## Support

- **Issues**: https://github.com/waldokilian2/unravel-marketplace/issues

## License

Marketplace metadata: MIT License

Individual plugins: See respective plugin licenses
