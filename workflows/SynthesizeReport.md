# SynthesizeReport Workflow

**Purpose:** Generate comprehensive comparison report from analysis data

**When to use:** After completing CompareSystem or ExtractPatterns workflow, user requests formal report

---

## Workflow Overview

This workflow takes analysis findings and structures them into polished, actionable comparison reports.

**Expected Duration:** 10-15 minutes
**Output:** Professional markdown report with executive summary and recommendations

---

## Report Types

### Type 1: Comprehensive Comparison Report
**Source:** CompareSystem workflow output
**Use:** Full infrastructure comparison with all 7 phases
**Audience:** Decision-makers, architects, implementers

### Type 2: Pattern Extraction Report
**Source:** ExtractPatterns workflow output
**Use:** Pattern-focused analysis
**Audience:** Developers, architects

### Type 3: Quick Assessment Report
**Source:** QuickAssess workflow output
**Use:** Go/No-Go decision support
**Audience:** Stakeholders, decision-makers

---

## Execution Steps

### Step 1: Gather Analysis Data (2 min)

**Collect all analysis artifacts:**
- Component mapping tables
- Gap analysis findings
- Strength assessments
- Risk evaluations
- Trade-off analyses
- Scoring matrices
- Code examples
- Pattern documentation

**Verify completeness:**
- [ ] All 7 phases completed (for comprehensive report)
- [ ] Scores calculated
- [ ] Examples collected
- [ ] Recommendations formulated

---

### Step 2: Structure Executive Summary (3 min)

**Executive summary components:**

1. **One-sentence bottom line:**
   - Clear recommendation (Adopt/Pilot/Skip)
   - Key value proposition

   Example: "Adopt Claude Flow's semantic search approach (HNSW indexing) for 100x performance improvement with manageable risk."

2. **Key findings (3-5 bullets):**
   - Most important discoveries
   - Critical gaps or strengths
   - Major risks or concerns

3. **Top recommendations (1-3):**
   - Highest-value opportunities
   - Most urgent actions
   - Strategic priorities

**Template:**
```markdown
## Executive Summary

**Bottom Line:** [One sentence recommendation and rationale]

**Key Findings:**
- [Finding 1]: [Impact]
- [Finding 2]: [Impact]
- [Finding 3]: [Impact]

**Top Recommendations:**
1. **[Recommendation 1]** (Impact: X/10, Risk: X/10)
   - [Brief description and rationale]
2. **[Recommendation 2]** (Impact: X/10, Risk: X/10)
   - [Brief description and rationale]
```

---

### Step 3: Organize Detailed Findings (5 min)

**For comprehensive comparison:**

**Section A: System Overview**
```markdown
## System Overview

**Name:** [System Name]
**Purpose:** [What it does]
**Repository:** [GitHub URL]
**License:** [License type]
**Language:** [Primary language]
**Community:**
- Stars: [count]
- Forks: [count]
- Contributors: [count]
- Last commit: [date]
- Activity: [Active/Moderate/Inactive]

**Tech Stack:**
- [Key dependency 1]
- [Key dependency 2]
- [Runtime/framework]
```

**Section B: Component Mapping**
```markdown
## Component Mapping

| Their Component | Purpose | [YOUR_SYSTEM] Equivalent | Status |
|----------------|---------|------------------|--------|
| [Component 1] | [Purpose] | [Equivalent or "None"] | [Gap/Match/Better] |
| [Component 2] | [Purpose] | [Equivalent or "None"] | [Gap/Match/Better] |

**Key Insights:**
- [Insight about component architecture]
- [Observation about design patterns]
```

**Section C: Gap Analysis**
```markdown
## Critical Gaps in [YOUR_SYSTEM]

### High Severity
1. **[Gap Name]** (Severity: 9/10)
   - **Problem:** [What problem this gap causes]
   - **User Impact:** [How it affects users]
   - **Workaround:** [Current workaround status]

### Medium Severity
2. **[Gap Name]** (Severity: 6/10)
   - [Details]

### Low Severity
3. **[Gap Name]** (Severity: 3/10)
   - [Details]
```

**Section D: Strengths**
```markdown
## What They Do Better

### 1. [Feature/Approach] (Impact: 9/10)
**What:** [Clear description]

**Why Better:** [Architectural or design reason]

**Evidence:**
```[language]
[Code example showing the approach]
```

**[YOUR_SYSTEM] Impact:** [How much [YOUR_SYSTEM] would improve]

### 2. [Feature/Approach] (Impact: 7/10)
[Same structure]
```

**Section E: Risk Assessment**
```markdown
## Risk Assessment

| Risk Category | Score | Details | Mitigation |
|--------------|-------|---------|------------|
| Architectural | X/10 | [Concern] | [Strategy] |
| Dependency | X/10 | [Concern] | [Strategy] |
| Maintenance | X/10 | [Concern] | [Strategy] |
| Community | X/10 | [Concern] | [Strategy] |

**Overall Risk:** X/10 ([Low/Medium/High])

**Red Flags:**
- [Any critical concerns]

**Green Lights:**
- [Positive indicators]
```

---

### Step 4: Formulate Recommendations (3 min)

**Categorize all recommendations:**

**High Value, Low Risk → ADOPT**
```markdown
### Adopt (High Priority)

#### 1. [Recommendation Name]
**Net Value:** 8.2/10 (Impact: 9/10, Risk: 2/10, Complexity: 3/10)

**What:** [Clear description]

**Why:** [Rationale for adoption]

**Implementation Approach:**
1. [Step 1]
2. [Step 2]
3. [Step 3]

**Timeline:** [Days/Weeks]

**Success Metrics:** [How to measure success]
```

**Medium Value/Risk → PILOT**
```markdown
### Pilot (Medium Priority)

#### 1. [Recommendation Name]
**Net Value:** 5.8/10 (Impact: 8/10, Risk: 6/10, Complexity: 6/10)

**What:** [Description]

**Why Pilot First:** [Reason for caution]

**Pilot Approach:**
1. Small-scale test: [Scope]
2. Metrics to track: [What to measure]
3. Go/No-Go criteria: [Decision point]

**Timeline:** [Weeks]

**Full Rollout If:** [Conditions for scaling]
```

**Low Value or High Risk → SKIP**
```markdown
### Skip (Not Recommended)

#### 1. [Feature Name]
**Net Value:** 2.1/10 (Impact: 4/10, Risk: 8/10, Complexity: 9/10)

**What:** [Description]

**Why Skip:** [Clear rationale]

**Alternatives:** [Better approaches if any]

**Revisit If:** [Conditions that would change assessment]
```

---

### Step 5: Create Implementation Roadmap (2 min)

**Phase recommendations by timeline:**

```markdown
## Implementation Roadmap

### Phase 1: Quick Wins (Days)
**Timeline:** This week
**Effort:** 1-5 hours each

1. **[Recommendation 1]**
   - Action: [What to do]
   - Owner: [Who implements]
   - Deliverable: [Expected output]

2. **[Recommendation 2]**
   - Action: [What to do]
   - Deliverable: [Expected output]

### Phase 2: Strategic Improvements (Weeks)
**Timeline:** Next 2-4 weeks
**Effort:** 1-2 days each

1. **[Recommendation 3]**
   - Prerequisites: [What needs to be done first]
   - Action: [Implementation approach]
   - Validation: [How to verify success]

### Phase 3: Architectural Enhancements (Months)
**Timeline:** Next quarter
**Effort:** 1-2 weeks each

1. **[Recommendation 4]**
   - Planning required: [Design/architecture work]
   - Action: [Phased approach]
   - Milestones: [Key checkpoints]
```

---

### Step 6: Add Supporting Materials (2 min)

**Appendix A: Scoring Matrix**
```markdown
## Appendix A: Scoring Matrix

| Feature/Pattern | Impact | Risk | Complexity | Net Value | Category |
|----------------|--------|------|------------|-----------|----------|
| [Item 1] | 9/10 | 2/10 | 3/10 | 8.2 | Adopt |
| [Item 2] | 7/10 | 5/10 | 6/10 | 5.3 | Pilot |
| [Item 3] | 4/10 | 8/10 | 7/10 | 1.9 | Skip |

**Calculation:** Net Value = Impact - (Risk × 0.5) - (Complexity × 0.3)
```

**Appendix B: Code Samples**
```markdown
## Appendix B: Representative Code Samples

### Example 1: [Pattern Name]
**File:** [path in their repo]

```[language]
[Well-commented code example]
```

**Why This Matters:** [Explanation of significance]
```

**Appendix C: Constitutional Alignment**
```markdown
## Appendix C: [YOUR_SYSTEM] Constitutional Alignment

| Principle | Aligned? | Notes |
|-----------|----------|-------|
| CLI-First Architecture | ✅ Yes | [Details] |
| Deterministic Code First | ⚠️ Partial | [Concerns and adaptations] |
| Prompts Wrap Code | ✅ Yes | [Details] |
| Markdown Zealotry | ✅ Yes | [Details] |
| TypeScript > Python | ❌ No | [Written in Python - requires port] |
| Security by Design | ✅ Yes | [Details] |
| Human-in-Loop | ✅ Yes | [Details] |

**Overall Alignment:** [Strong/Moderate/Weak]
**Adaptation Required:** [What needs to change]
```

---

### Step 7: Polish and Review (2 min)

**Quality checklist:**
- [ ] Executive summary is clear and actionable
- [ ] All sections complete and well-organized
- [ ] Recommendations have clear rationale
- [ ] Scores are consistent and justified
- [ ] Code examples are relevant and explained
- [ ] Implementation roadmap is realistic
- [ ] Report is free of jargon and clearly written
- [ ] Links and references are correct
- [ ] Constitutional alignment assessed

**Read through report:**
- Check flow and coherence
- Verify all claims are supported
- Ensure recommendations are actionable
- Confirm executive summary matches details

---

## Report Filename Convention

**Format:** `YYYY-MM-DD_[system-name]-[report-type].md`

**Examples:**
- `2026-01-18_claude-flow-comparison.md`
- `2026-01-18_aider-patterns.md`
- `2026-01-18_openhands-quick-assessment.md`

**Location:** `[SKILL_DIR]/MEMORY/comparisons/`

---

## Voice Notification Format

```
🎯 COMPLETED: [AGENT:[AGENT_NAME]] synthesized comparison report for [system-name]: [top recommendation]
```

Example:
```
🎯 COMPLETED: [AGENT:[AGENT_NAME]] synthesized comparison report for Claude Flow: adopt semantic search, 8 total recommendations
```

---

## Report Templates

### Template: Comprehensive Comparison

```markdown
# [System Name] Infrastructure Comparison

**Date:** YYYY-MM-DD
**Target:** [Repository URL]
**Analysis Duration:** [Time spent]
**Report Type:** Comprehensive Comparison

---

## Executive Summary
[3-5 sentences with bottom-line recommendation]

## System Overview
[Purpose, tech stack, community metrics]

## Component Mapping
[Detailed table with insights]

## Gap Analysis
[Categorized by severity]

## What They Do Better
[Ranked list with WHY and examples]

## Risk Assessment
[Table with mitigation strategies]

## Trade-off Analysis
[Feature-by-feature assessment]

## Recommendations

### Adopt (High Value, Low Risk)
[Detailed recommendations]

### Pilot (High Value, Medium Risk)
[Detailed recommendations]

### Skip (Low Value or High Risk)
[What to avoid and why]

## Implementation Roadmap
[Phased approach]

## Appendices
[Scoring, code samples, constitutional alignment]
```

---

## Checklist

- [ ] Analysis data collected
- [ ] Executive summary written
- [ ] All sections completed
- [ ] Recommendations categorized (Adopt/Pilot/Skip)
- [ ] Implementation roadmap created
- [ ] Scoring matrix included
- [ ] Code samples added (if relevant)
- [ ] Constitutional alignment assessed
- [ ] Report polished and reviewed
- [ ] Saved to correct location with proper filename

---

## Tips for Effective Reports

**Do:**
- ✅ Start with executive summary (busy readers)
- ✅ Use tables for structured data
- ✅ Include code examples
- ✅ Make recommendations actionable
- ✅ Justify all scores
- ✅ Be honest about risks

**Don't:**
- ❌ Bury the lead (key findings last)
- ❌ Use vague language ("might be good")
- ❌ Make unsupported claims
- ❌ Ignore constitutional alignment
- ❌ Forget implementation guidance
- ❌ Skip the "why" behind recommendations

**Remember:**
- Report should stand alone (reader doesn't need context)
- Recommendations should be implementable by someone else
- Evidence should support all claims
- Trade-offs should be explicitly stated

---

**Workflow Version:** 1.0
**Last Updated:** 2026-01-18
**Estimated Duration:** 10-15 minutes
**Output:** Polished comparison report with actionable recommendations
