# Unravel Marketplace

Business artifact extraction plugins for Claude Code.

## Installation

Add this marketplace to Claude Code:

```bash
/plugin marketplace add waldokilian2/unravel-marketplace
```

## Available Plugins

### Unravel v2.2.0

**Description:** Unravel the mysteries in your code - automatic extraction of business rules, processes, data specs, user stories, security, and integrations. User selects categories, chooses verification level, then Unravel handles the rest with batched parallel execution.

**Categories:** Business Analysis, Documentation, Reverse Engineering

**Install:**
```bash
/plugin install unravel@unravel-marketplace
```

**Repository:** https://github.com/waldokilian2/unravel

**What's New in v2.2.0:**
- **Batched parallel execution:** Extractors run in batches of 2 (max 3 concurrent agents total)
- **User-controlled verification:** Choose independent verification (thorough) or self-verify only (fast)
- **Automatic surgical fixes:** When verification fails with fixable issues, automatically apply targeted fixes and re-verify
- **4-option category selection:** UX within Claude's limits for artifact type selection
  - Business Logic (rules, processes, user stories)
  - Data Specifications (schemas, ORMs, DTOs)
  - Technical Details (security, integrations)
  - Everything (all 6 types)
- **Orchestrator as skill:** orchestrating-extraction skill coordinates the entire workflow
- **New /unravel command:** Quick invocation for starting Unravel

**Architecture:**
- Main Agent follows orchestrating-extraction skill
- Spawns extractors in batches of 2 (parallel within batch, sequential between batches)
- User chooses: independent verifiers in batches of 2, OR skip to merge
- Spawns fixer + re-verifies if verification fails with fixable issues
- Spawns merger after all modules ready
- Optional: Summarizer creates EXECUTIVE-SUMMARY.md

**Workflow:**
```
User → Select type(s) → Choose verification → Main Agent
  → Batch 1: Extract 2 modules (parallel)
  → Batch 2: Extract remaining modules (parallel)
  → [If verification enabled] Batch 1: Verify 2 modules (parallel)
  → [If verification enabled] Batch 2: Verify remaining modules (parallel)
  → [If fixable issues] Spawn fixer → Re-verify
  → Merge all outputs
  → [Optional] Create executive summary
```

**Commands:**
- `/unravel` - Start Unravel extraction with category selection

**Agents:**
- unravel-extractor: Extract patterns from assigned files (per module) with self-verification
- unravel-verifier: Independently verify extraction outputs (optional, user-controlled)
- unravel-fixer: Surgically fix specific issues in extraction output (automatic)
- unravel-merger: Combine verified outputs into final file
- unravel-summarizer: Create executive summary from all outputs (optional)

**Skills:**
- orchestrating-extraction: Main orchestration logic
- using-unravel: User guide and documentation
- extract-business-rules: Business rules domain knowledge
- extract-process-flows: Process flows domain knowledge
- extract-data-specs: Data specs domain knowledge
- extract-user-stories: User stories domain knowledge
- extract-security-nfrs: Security/NFRs domain knowledge
- extract-integrations: Integrations domain knowledge

---

## Support

- **Issues**: https://github.com/waldokilian2/unravel-marketplace/issues

## License

Marketplace metadata: MIT License

Individual plugins: See respective plugin licenses
