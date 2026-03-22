# Unravel Marketplace

Business artifact extraction plugins for Claude Code.

## Installation

Add this marketplace to Claude Code:

```bash
/plugin marketplace add waldokilian2/unravel-marketplace
```

## Available Plugins

### Unravel v2.2.0

**Description:** Unravel the mysteries in your code - automatic extraction of business rules, processes, data specs, user stories, security, and integrations. User selects categories from 4 options, then Unravel handles the rest. All agent spawning is handled sequentially by the main agent - no nested spawning.

**Categories:** Business Analysis, Documentation, Reverse Engineering

**Install:**
```bash
/plugin install unravel@unravel-marketplace
```

**Repository:** https://github.com/waldokilian2/unravel

**What's New in v2.2.0:**
- **Flattened architecture:** Removed 2-level agent spawning - main agent now spawns extractors, verifiers, and merger directly
- **4-option category selection:** New UX within Claude's 4-option limit for artifact type selection
  - Business Logic (rules, processes, user stories)
  - Data Specifications (schemas, ORMs, DTOs)
  - Technical Details (security, integrations)
  - Everything (all 6 types)
- **New /unravel command:** Quick invocation for starting Unravel
- **Orchestrator converted to skill:** orchestrating-extraction skill coordinates workflow
- **Improved /verify command:** Better documentation and usage examples
- **Output format clarification:** All extraction skills now document per-module vs merged output

**Architecture:**
- Main Agent follows orchestrating-extraction skill
- Spawns extractors sequentially (one at a time)
- Spawns verifiers sequentially (one at a time)
- Spawns merger after all verifications pass
- Optional: Summarizer creates EXECUTIVE-SUMMARY.md

**Commands:**
- `/unravel` - Start Unravel extraction with category selection
- `/verify <file>` - Verify an extraction output

**Agents:**
- unravel-extractor: Extract patterns from assigned files (per module)
- unravel-verifier: Independently verify extraction outputs
- unravel-merger: Combine verified outputs into final file
- unravel-summarizer: Create executive summary from all outputs

---

## Support

- **Issues**: https://github.com/waldokilian2/unravel-marketplace/issues

## License

Marketplace metadata: MIT License

Individual plugins: See respective plugin licenses
