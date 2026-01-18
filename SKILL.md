---
name: InfrastructureComparison
description: |
  Systematic comparison and analysis of external AI infrastructure systems against [YOUR_SYSTEM].
  Identifies unique capabilities, improvements, gaps, risks, and integration opportunities.

  USE WHEN user says "compare infrastructure", "analyze system", "evaluate X infrastructure",
  "what can we learn from X", "assess X system", "compare X to [YOUR_SYSTEM]", "infrastructure comparison",
  "system analysis", or requests evaluation of external AI systems, repositories, or frameworks.
---

# InfrastructureComparison

Systematic methodology for evaluating external AI infrastructure systems against [YOUR_SYSTEM] to identify adoption opportunities, improvements, and risks.

**Core Philosophy:** As AI infrastructure projects proliferate, we need rigorous comparison methodology that goes beyond surface-level observation to provide actionable intelligence about what to adopt, adapt, or avoid.

## Workflow Routing

**When executing a workflow, output this notification:**

```
Running the **WorkflowName** workflow from the **InfrastructureComparison** skill...
```

| Workflow | Trigger | File |
|----------|---------|------|
| **CompareSystem** | "compare system", "analyze infrastructure", "evaluate X against [YOUR_SYSTEM]", "comprehensive analysis" | `workflows/CompareSystem.md` |
| **QuickAssess** | "quick look at X", "initial assessment", "high-level comparison", "worth investigating X" | `workflows/QuickAssess.md` |
| **ExtractPatterns** | "extract patterns from X", "what patterns does X use", "identify their approach" | `workflows/ExtractPatterns.md` |
| **SynthesizeReport** | "create comparison report", "synthesize findings", "generate comparison doc" | `workflows/SynthesizeReport.md` |

---

## When to Activate This Skill

Activate InfrastructureComparison when:

- User mentions comparing [YOUR_SYSTEM] to another AI infrastructure system
- User asks to evaluate external repositories (Claude Flow, Aider, OpenHands, etc.)
- User wants to understand what other systems do better
- User asks "what can we learn from X system"
- User requests gap analysis between [YOUR_SYSTEM] and external systems
- User wants to assess adoption risks before integrating external approaches
- User asks about trade-offs of adopting external methodologies
- User mentions reviewing GitHub repositories for infrastructure ideas

**Do NOT activate for:**
- General code reviews (use LLMWorkflow Review instead)
- Security audits (use security-focused skills)
- Simple "how does X work" questions without comparison intent

---

## Comparison Methodology

### The 7-Phase Analysis Framework

InfrastructureComparison uses a systematic 7-phase approach modeled after the Claude Flow evaluation process:

#### Phase 1: Discovery & Reconnaissance
- Clone/access target repository
- Read documentation (README, architecture docs, guides)
- Identify core components and structure
- Map technology stack and dependencies
- Assess community activity (stars, commits, issues, PRs)

#### Phase 2: Component Mapping
- Identify target system's major components
- Map each component to [YOUR_SYSTEM] equivalents
- Identify components [YOUR_SYSTEM] lacks
- Note components that overlap but differ in approach

**Example Mapping:**
```
Target System          [YOUR_SYSTEM] Equivalent           Gap/Difference
-------------          ----------------           ---------------
Agent orchestrator  →  Task tool + subagents   →  Different architecture
Memory system       →  MEMORY directories      →  Similar approach
Voice integration   →  VoiceRouter system      →  [YOUR_SYSTEM] has this
Workflow engine     →  Skills + routing        →  Different paradigm
```

#### Phase 3: Gap Analysis
- What capabilities does target have that [YOUR_SYSTEM] lacks?
- What problems do they solve that [YOUR_SYSTEM] doesn't address?
- What user needs do they fulfill that [YOUR_SYSTEM] ignores?

**Gap Categories:**
- **Functional gaps:** Features [YOUR_SYSTEM] doesn't have
- **Quality gaps:** Things [YOUR_SYSTEM] does worse
- **UX gaps:** Better user experience patterns
- **Integration gaps:** External services they support

#### Phase 4: Strength Analysis
- What does target system do BETTER than [YOUR_SYSTEM]?
- WHY is it better? (architecture, design, implementation)
- What makes their approach effective?
- What principles or patterns drive their success?

**Evaluation Criteria:**
- Code quality and maintainability
- Architecture elegance and scalability
- Documentation clarity
- User experience design
- Performance characteristics
- Reliability and error handling

#### Phase 5: Risk Assessment
- What are the stability risks of their approach?
- What maintenance burden would adoption introduce?
- How well does it align with [YOUR_SYSTEM]'s constitutional principles?
- What dependencies would we inherit?
- What's their community health and longevity outlook?

**Risk Categories:**
- **Architectural risk:** Conflicts with [YOUR_SYSTEM] principles
- **Dependency risk:** External dependencies, breaking changes
- **Maintenance risk:** Complexity, technical debt
- **Community risk:** Project abandonment, poor support
- **Security risk:** Vulnerabilities, trust boundaries

#### Phase 6: Trade-off Analysis
- What would [YOUR_SYSTEM] LOSE by adopting this approach?
- What existing capabilities would be complicated?
- What migrations or rewrites would be required?
- What's the adoption cost vs. benefit ratio?

**Trade-off Framework:**
```
Feature to Adopt: [Name]
Benefits:
  - [Specific improvement 1]
  - [Specific improvement 2]
Costs:
  - [What we lose or complicate 1]
  - [What we lose or complicate 2]
Migration Complexity: [Low/Medium/High]
Net Value: [High/Medium/Low/Negative]
```

#### Phase 7: Synthesis & Recommendations
- Consolidate findings into actionable recommendations
- Score opportunities by value and risk
- Provide implementation roadmap for adoptable features
- Identify quick wins vs. long-term improvements

**Output Format:**
```markdown
# [System Name] vs [YOUR_SYSTEM] - Comparison Report

## Executive Summary
[3-5 sentences: key findings and recommendation]

## What They Do Better
1. [Feature/approach 1] - WHY it's better, impact score
2. [Feature/approach 2] - WHY it's better, impact score

## Critical Gaps in [YOUR_SYSTEM]
1. [Gap 1] - Problem it causes, severity
2. [Gap 2] - Problem it causes, severity

## Adoption Recommendations
### High Value, Low Risk (Adopt)
- [Recommendation with implementation approach]

### High Value, Medium Risk (Pilot)
- [Recommendation with risk mitigation]

### Low Value or High Risk (Skip)
- [What to avoid and why]

## Implementation Roadmap
[Phased approach for adopting recommendations]
```

---

## Constitutional Alignment Check

Before recommending adoption, evaluate alignment with [YOUR_SYSTEM]'s core principles:

**[YOUR_SYSTEM] Constitutional Principles:**
1. ✅ **CLI-First Architecture** - Tools wrap prompts, not vice versa
2. ✅ **Deterministic Code First** - Prefer deterministic code over prompts
3. ✅ **Prompts Wrap Code** - AI orchestrates deterministic tools
4. ✅ **Markdown Zealotry** - Never use HTML for basic content
5. ✅ **TypeScript > Python** - Prefer TS unless explicitly approved
6. ✅ **Security by Design** - Never expose credentials, prompt injection defense
7. ✅ **Human-in-Loop** - AI augments, doesn't replace human judgment

**Alignment Questions:**
- Does this approach violate any constitutional principles?
- Can it be adapted to align with [YOUR_SYSTEM]'s architecture?
- What compromises would be required for integration?

---

## Scoring Framework

Use numerical scores (1-10) for objective comparison:

### Impact Score (How much better would [YOUR_SYSTEM] be?)
- **10:** Transformative improvement, game-changer
- **7-9:** Significant improvement, clear benefits
- **4-6:** Moderate improvement, nice to have
- **1-3:** Marginal improvement, questionable value

### Risk Score (How risky is adoption?)
- **10:** Critical risk, likely to break [YOUR_SYSTEM]
- **7-9:** High risk, major architectural changes
- **4-6:** Medium risk, manageable with care
- **1-3:** Low risk, safe to adopt

### Complexity Score (How hard to implement?)
- **10:** Massive rewrite, months of work
- **7-9:** Significant effort, weeks of work
- **4-6:** Moderate effort, days of work
- **1-3:** Trivial, hours of work

### Net Value Calculation
```
Net Value = (Impact Score) - (Risk Score × 0.5) - (Complexity Score × 0.3)

Interpretation:
  >7.0  = Must adopt (high value, manageable risk/complexity)
  5-7   = Should pilot (good value, needs validation)
  3-5   = Consider carefully (unclear value proposition)
  <3.0  = Skip (low value or prohibitive risk/complexity)
```

---

## Integration with LLMWorkflow

For complex comparisons, use LLMWorkflow Plan workflow:

**When to use LLMWorkflow:**
- Target system is large/complex (>100 files)
- Requires deep code analysis
- Multiple decision points with trade-offs
- Needs architectural planning for integration

**Integration Pattern:**
```
1. InfrastructureComparison CompareSystem workflow
   → Generates initial analysis

2. If adoption recommended:
   → LLMWorkflow Plan workflow
   → Create detailed implementation plan

3. LLMWorkflow Implement workflow
   → Execute phased integration
```

---

## Examples

### Example 1: Quick Assessment
```
User: "Worth looking at Aider's approach to code editing?"

→ Invokes QuickAssess workflow
→ Clones aider repository
→ Reads README and architecture docs
→ Identifies: specialized code editing UI, git integration, prompt patterns
→ Quick assessment:
  - Impact: 6/10 (better UX for code edits)
  - Risk: 4/10 (Python dependency, different paradigm)
  - Complexity: 7/10 (requires new UI layer)
  - Net Value: 3.8 (marginal - investigate specific patterns only)
→ Recommendation: Extract prompt patterns, skip full adoption
```

### Example 2: Comprehensive System Comparison
```
User: "Do a full analysis of Claude Flow vs [YOUR_SYSTEM] - what should we adopt?"

→ Invokes CompareSystem workflow
→ 7-phase analysis:
  1. Discovery: Clone repo, read all docs, map structure
  2. Component Mapping: MEMORY system, hooks, voice, agents
  3. Gap Analysis: Advanced semantic search, HNSW indexing
  4. Strength Analysis: O(log n) search vs linear, better scalability
  5. Risk Assessment: Complex setup, Qdrant dependency
  6. Trade-offs: Performance gain vs complexity cost
  7. Synthesis: Adopt semantic search, adapt MEMORY structure
→ Generates comprehensive markdown report
→ Provides scored recommendations with roadmap
```

### Example 3: Pattern Extraction
```
User: "What patterns does OpenHands use that we don't?"

→ Invokes ExtractPatterns workflow
→ Identifies:
  - Sandboxed execution environment
  - Web browsing agent capabilities
  - Multi-agent collaboration patterns
  - Structured planning/execution separation
→ Compares to [YOUR_SYSTEM] patterns
→ Highlights novel approaches worth investigating
→ Scores each pattern for adoption potential
```

### Example 4: Trade-off Analysis
```
User: "If we adopt their agent orchestration, what do we lose?"

→ Invokes CompareSystem workflow with trade-off focus
→ Analyzes:
  - Current [YOUR_SYSTEM]: Task tool + subagent types (simple, direct)
  - Their approach: Complex orchestrator with dependency graphs
→ Trade-off assessment:
  Benefits:
    - Better handling of agent dependencies
    - More sophisticated parallelization
  Costs:
    - Loss of simplicity (core [YOUR_SYSTEM] value)
    - Breaking change for existing skills
    - Increased cognitive overhead
→ Recommendation: Skip (conflicts with simplicity principle)
```

---

## Output Artifacts

All comparison workflows save comprehensive reports to:
`[SKILL_DIR]/MEMORY/comparisons/YYYY-MM-DD_[system-name]-comparison.md`

**Report Structure:**
```markdown
# [System Name] Infrastructure Comparison

**Date:** YYYY-MM-DD
**Target:** [GitHub URL / Documentation Links]
**Analyst:** [YOUR_SYSTEM] InfrastructureComparison Skill
**Comparison Type:** [Quick / Comprehensive / Pattern Extraction]

---

## Executive Summary
[3-5 sentences with bottom-line recommendation]

## System Overview
- **Purpose:** What they do
- **Architecture:** How they do it
- **Community:** Stars, contributors, activity
- **Tech Stack:** Dependencies, languages, tools

## Component Mapping
[Detailed mapping table]

## Gap Analysis
### Functional Gaps
- [List with severity scores]

### Quality Gaps
- [List with severity scores]

## What They Do Better
[Ranked list with WHY and Impact scores]

## Risk Assessment
[Categorized risks with mitigation approaches]

## Trade-off Analysis
[Feature-by-feature trade-offs]

## Recommendations

### Adopt (High Value, Low Risk)
- [Specific recommendations with implementation notes]

### Pilot (High Value, Medium Risk)
- [Specific recommendations with validation approach]

### Skip (Low Value or High Risk)
- [What to avoid and why]

## Implementation Roadmap

### Phase 1: Quick Wins (Days)
- [Immediate improvements]

### Phase 2: Medium Complexity (Weeks)
- [Significant enhancements]

### Phase 3: Long-term (Months)
- [Architectural improvements]

---

## Appendices

### Scoring Matrix
[All scores with calculations]

### Code Samples
[Relevant code examples from target system]

### Constitutional Alignment Analysis
[Principle-by-principle assessment]
```

---

## Voice Capabilities

This skill has voice notification capabilities. When comparison workflows complete, your configured voice will announce completion.

**Voice format in completions:**
```
🎯 COMPLETED: [AGENT:[AGENT_NAME]] analyzed [system-name] infrastructure with [N] recommendations
```

**Quick test:**
```bash
voice-router-cli test [AGENT_NAME] "Testing infrastructure comparison voice"
```

**Full documentation:** `[SKILL_DIR]/CORE/SYSTEM/AGENT-VOICE-GUIDE.md`

---

**Version:** 1.0
**Created:** 2026-01-18
**Status:** Production Ready
**Methodology:** Based on Claude Flow comparison process, formalized for reuse
