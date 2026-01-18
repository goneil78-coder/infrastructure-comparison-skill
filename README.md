# Infrastructure Comparison Skill

A systematic methodology for evaluating external AI infrastructure systems against your own AI infrastructure.

## Overview

As AI infrastructure projects proliferate (Claude Flow, Aider, OpenHands, etc.), this skill provides a structured framework to evaluate them against your current system to identify:

1. What makes their system unique and effective
2. What they're doing better than your system
3. What gaps their system fills that yours doesn't
4. What would be genuine improvements (and WHY)
5. What might be unstable or risky to adopt
6. Potential losses or trade-offs if you integrate their approach

## Methodology

The skill uses a systematic **7-phase analysis framework**:

1. **Discovery & Reconnaissance** - Clone repo, read docs, collect metrics
2. **Component Mapping** - Map their components to your system equivalents
3. **Gap Analysis** - Identify what your system lacks
4. **Strength Analysis** - Understand what they do better and WHY
5. **Risk Assessment** - Evaluate adoption risks
6. **Trade-off Analysis** - What would your system lose
7. **Synthesis & Recommendations** - Actionable recommendations with roadmap

## Workflows

The skill includes 4 complementary workflows:

### 1. CompareSystem (20-60 minutes)
Comprehensive 7-phase analysis producing detailed comparison reports with scored recommendations.

**Use when:** You want deep analysis before making adoption decisions.

### 2. QuickAssess (10-15 minutes)
Rapid go/no-go assessment to determine if deeper analysis is warranted.

**Use when:** You need to quickly filter whether a system is worth investigating.

### 3. ExtractPatterns (15-30 minutes)
Pattern identification and extraction workflow focusing on reusable architectural patterns.

**Use when:** You want to understand specific patterns without full comparison.

### 4. SynthesizeReport (10-15 minutes)
Generate polished comparison reports from analysis data.

**Use when:** You need to document findings in a structured format.

## Installation

### 1. Copy the skill to your AI infrastructure

```bash
# Copy the entire directory to your skill directory
cp -r infrastructure-comparison-skill [YOUR_SKILL_DIRECTORY]/InfrastructureComparison
```

### 2. Customize for your system

Replace the following placeholders throughout all files:

| Placeholder | Replace With | Example |
|-------------|--------------|---------|
| `[YOUR_SYSTEM]` | Your AI infrastructure name | `CPain`, `MyAI`, `Jarvis` |
| `[SKILL_DIR]` | Your skill directory path | `~/.claude/`, `~/.ai/` |
| `[YOUR_NAME]` | Your name | `Alice`, `Bob` |
| `[AGENT_NAME]` | Your agent/voice name | `kai`, `assistant` |

**Quick replacement:**
```bash
cd [YOUR_SKILL_DIRECTORY]/InfrastructureComparison

# Replace system name
find . -type f -name "*.md" -exec sed -i 's/\[YOUR_SYSTEM\]/YourSystemName/g' {} +

# Replace skill directory
find . -type f -name "*.md" -exec sed -i 's|\[SKILL_DIR\]|~/.your-path|g' {} +

# Replace your name
find . -type f -name "*.md" -exec sed -i 's/\[YOUR_NAME\]/YourName/g' {} +

# Replace agent name
find . -type f -name "*.md" -exec sed -i 's/\[AGENT_NAME\]/your-agent/g' {} +
```

### 3. Customize Constitutional Principles

Edit the Constitutional Alignment section in `SKILL.md` to match your system's principles:

```markdown
**[YOUR_SYSTEM] Constitutional Principles:**
1. ✅ **Your Principle 1** - Description
2. ✅ **Your Principle 2** - Description
...
```

### 4. Adjust Scoring Framework (Optional)

The default Net Value calculation is:
```
Net Value = Impact - (Risk × 0.5) - (Complexity × 0.3)
```

You can adjust the weights in the scoring sections to match your priorities.

## Usage

Once installed and customized, activate workflows using trigger phrases:

```
# Comprehensive analysis
"Compare Claude Flow infrastructure to my system"
"Analyze Aider vs [YOUR_SYSTEM]"

# Quick assessment
"Quick look at OpenHands"
"Is Cursor worth investigating?"

# Pattern extraction
"Extract patterns from Agentic.js"
"What patterns does LangChain use?"

# Report generation
"Create comparison report for Claude Flow"
"Synthesize findings for Aider"
```

## Output

All workflows generate structured markdown reports saved to:
```
[SKILL_DIR]/MEMORY/comparisons/YYYY-MM-DD_[system-name]-comparison.md
```

Reports include:
- Executive Summary with bottom-line recommendation
- System Overview (tech stack, community metrics)
- Component Mapping (detailed table)
- Gap Analysis (categorized by severity)
- What They Do Better (ranked with WHY)
- Risk Assessment (with mitigation strategies)
- Recommendations (Adopt/Pilot/Skip)
- Implementation Roadmap (phased approach)
- Scoring Matrix and Code Samples

## Scoring Framework

### Impact Score (1-10)
- **10:** Transformative improvement, game-changer
- **7-9:** Significant improvement, clear benefits
- **4-6:** Moderate improvement, nice to have
- **1-3:** Marginal improvement, questionable value

### Risk Score (1-10)
- **10:** Critical risk, likely to break your system
- **7-9:** High risk, major architectural changes
- **4-6:** Medium risk, manageable with care
- **1-3:** Low risk, safe to adopt

### Complexity Score (1-10)
- **10:** Massive rewrite, months of work
- **7-9:** Significant effort, weeks of work
- **4-6:** Moderate effort, days of work
- **1-3:** Trivial, hours of work

### Net Value Interpretation
- **>7.0** = Must adopt (high value, manageable risk/complexity)
- **5-7** = Should pilot (good value, needs validation)
- **3-5** = Consider carefully (unclear value proposition)
- **<3.0** = Skip (low value or prohibitive risk/complexity)

## Examples

### Example 1: Comprehensive System Comparison
```
Input: "Do a full analysis of Claude Flow vs [YOUR_SYSTEM] - what should we adopt?"

Output:
→ 7-phase CompareSystem workflow executes
→ Generates comprehensive report with:
  - 12 scored recommendations
  - Component mapping table
  - Constitutional alignment assessment
  - Phased implementation roadmap
→ Top recommendation: Adopt semantic search (Net Value: 8.2/10)
```

### Example 2: Quick Assessment
```
Input: "Worth looking at Aider's approach to code editing?"

Output:
→ QuickAssess workflow executes (15 minutes)
→ Verdict: "Investigate Further"
→ Key insight: Novel code editing UI pattern
→ Impact: 6/10, Risk: 4/10, Complexity: 7/10
→ Next step: Run full CompareSystem workflow
```

### Example 3: Pattern Extraction
```
Input: "What patterns does OpenHands use that we don't?"

Output:
→ ExtractPatterns workflow executes
→ Identifies 8 patterns:
  - Sandboxed execution environment
  - Web browsing agent capabilities
  - Multi-agent collaboration patterns
  - Structured planning/execution separation
→ Scores each for adoption potential
→ Top pattern: Sandboxed execution (Adoption Score: 7.8/10)
```

## Integration Requirements

This skill is designed to work with:
- **CLI-based AI infrastructure** - Assumes command-line tooling
- **Skill/workflow system** - Requires skill routing capability
- **MEMORY system** - For storing comparison reports
- **Git access** - For cloning external repositories

## Customization Tips

1. **Adjust constitutional principles** to match your system's values
2. **Modify scoring weights** based on your priorities (risk-averse vs innovation-focused)
3. **Customize report templates** in SynthesizeReport.md for your preferred format
4. **Add domain-specific questions** to each phase based on your use case
5. **Configure voice notifications** if your system supports audio feedback

## Contributing

This skill is open for community improvements. Consider contributing:
- Additional workflow types (e.g., SecurityAssess, PerformanceCompare)
- Domain-specific assessment checklists
- Alternative scoring frameworks
- Integration guides for specific AI infrastructures

## License

MIT License - See LICENSE file for details

## Version

**Version:** 1.0
**Created:** 2026-01-18
**Status:** Production Ready
**Methodology:** Based on systematic infrastructure comparison process

---

**Note:** This skill actively searches, reads, analyzes, and synthesizes external repositories. Ensure you have proper Git access and understand licensing implications when analyzing external projects.
