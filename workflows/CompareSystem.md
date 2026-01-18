# CompareSystem Workflow

**Purpose:** Comprehensive 7-phase analysis of external AI infrastructure system vs [YOUR_SYSTEM]

**When to use:** User requests full comparison, evaluation, or "what should we adopt from X"

---

## Workflow Overview

This workflow implements the complete 7-phase comparison methodology to produce actionable intelligence about external AI infrastructure systems.

**Expected Duration:** 20-60 minutes depending on system complexity
**Output:** Comprehensive comparison report with scored recommendations

---

## Execution Steps

### Pre-Flight Check

**Before starting, confirm:**
1. ✅ You have the target system's GitHub URL or documentation links
2. ✅ Target system is an AI infrastructure project (not just a library/tool)
3. ✅ User wants comprehensive analysis (not just quick look)

**If uncertain about scope, ask:**
- "Do you want a comprehensive analysis or a quick initial assessment?"
- "Are there specific aspects you want me to focus on (architecture, features, integration)?"

### Phase 1: Discovery & Reconnaissance (5-10 min)

**Objective:** Gather comprehensive information about the target system

**Actions:**

1. **Access the repository:**
   ```bash
   cd /tmp
   git clone [repository-url] [system-name]-analysis
   cd [system-name]-analysis
   ```

2. **Quick stats collection:**
   ```bash
   # Repository metrics
   git log --oneline | wc -l  # Total commits
   git log --since="1 month ago" --oneline | wc -l  # Recent activity
   find . -name "*.ts" -o -name "*.js" -o -name "*.py" | wc -l  # File count
   ```

3. **Read core documentation** (parallel reads):
   - README.md
   - ARCHITECTURE.md / docs/architecture.md
   - CONTRIBUTING.md
   - package.json / pyproject.toml (dependencies)
   - Any setup/installation guides

4. **Identify directory structure:**
   ```bash
   tree -L 2 -d  # Or ls -R for overview
   ```

5. **Search for key patterns:**
   ```bash
   # Look for key architectural concepts
   grep -r "agent" --include="*.md" | head -20
   grep -r "workflow" --include="*.md" | head -20
   grep -r "memory" --include="*.md" | head -20
   ```

**Deliverable:** Mental model of system architecture and purpose

---

### Phase 2: Component Mapping (10-15 min)

**Objective:** Map their components to [YOUR_SYSTEM] equivalents

**Actions:**

1. **Identify major components** by examining:
   - Directory structure (src/, lib/, agents/, tools/)
   - Package.json scripts
   - Documentation structure
   - Core class/module names

2. **Create mapping table:**

   For each identified component:
   - Component name in target system
   - Purpose/function
   - [YOUR_SYSTEM] equivalent (if exists)
   - Difference in approach
   - Gap status ([YOUR_SYSTEM] lacks / [YOUR_SYSTEM] has / Different implementation)

3. **Document the mapping:**
   ```markdown
   ## Component Mapping

   | Target Component | Purpose | [YOUR_SYSTEM] Equivalent | Status |
   |-----------------|---------|------------------|--------|
   | Agent Manager | Orchestrates agents | Task tool + subagents | Different architecture |
   | Memory Store | Persistent context | MEMORY directories | Similar approach |
   | CLI Interface | User interaction | Claude Code CLI | External vs integrated |
   ```

4. **Identify unique components** (what they have that [YOUR_SYSTEM] doesn't):
   - List each unique component
   - Note what problem it solves
   - Assess whether [YOUR_SYSTEM] needs it

**Deliverable:** Complete component mapping with gap identification

---

### Phase 3: Gap Analysis (5-10 min)

**Objective:** Identify what [YOUR_SYSTEM] lacks that target system provides

**Actions:**

1. **Functional Gaps:**
   - Features they have that [YOUR_SYSTEM] doesn't
   - User workflows they support that [YOUR_SYSTEM] can't handle
   - Integration points [YOUR_SYSTEM] lacks

2. **Quality Gaps:**
   - Things [YOUR_SYSTEM] does, but they do better
   - Performance improvements
   - UX enhancements
   - Reliability/error handling improvements

3. **For each gap, assess:**
   - **Severity:** Critical / Major / Minor / Nice-to-have
   - **User Impact:** How much does this gap hurt [YOUR_SYSTEM] users?
   - **Workaround Status:** Can users work around it? How painfully?

4. **Prioritize gaps:**
   ```markdown
   ### Critical Gaps (Must Address)
   - [Gap 1]: [Why it's critical]

   ### Major Gaps (Should Address)
   - [Gap 2]: [Why it matters]

   ### Minor Gaps (Consider)
   - [Gap 3]: [Low priority reasoning]
   ```

**Deliverable:** Prioritized gap list with severity assessment

---

### Phase 4: Strength Analysis (10-15 min)

**Objective:** Understand what they do BETTER and WHY

**Actions:**

1. **Identify strengths:**
   - Read through their best code examples
   - Look for elegant solutions
   - Find novel approaches
   - Identify well-designed patterns

2. **For each strength, ask WHY:**
   - What design decision enables this?
   - What architectural choice makes this possible?
   - What principle or pattern drives this success?

3. **Code quality analysis:**
   - Read 3-5 representative files
   - Assess: clarity, maintainability, test coverage
   - Note: patterns, idioms, conventions

4. **Document findings:**
   ```markdown
   ## What They Do Better

   ### 1. [Feature/Approach Name]
   - **What:** [Description]
   - **Why Better:** [Architectural/design reason]
   - **Impact Score:** 8/10
   - **Example:** [Code snippet or usage example]

   ### 2. [Feature/Approach Name]
   - **What:** [Description]
   - **Why Better:** [Reason]
   - **Impact Score:** 6/10
   ```

**Deliverable:** Ranked list of strengths with WHY analysis

---

### Phase 5: Risk Assessment (5-10 min)

**Objective:** Evaluate risks of adopting their approaches

**Actions:**

1. **Architectural Risk Analysis:**
   - Does it conflict with CLI-First principle?
   - Does it violate Deterministic Code First?
   - Does it break Prompts Wrap Code pattern?
   - Check against all [YOUR_SYSTEM] constitutional principles

2. **Dependency Risk Analysis:**
   ```bash
   # Check dependencies
   cat package.json | grep dependencies -A 50
   # Or for Python:
   cat pyproject.toml | grep dependencies -A 50
   ```
   - How many dependencies?
   - Are they well-maintained?
   - Any security concerns?
   - Breaking change history?

3. **Maintenance Risk Analysis:**
   - Code complexity assessment
   - Technical debt indicators
   - Test coverage
   - Documentation quality

4. **Community Risk Analysis:**
   - GitHub stars, forks, watchers
   - Commit frequency
   - Issue response time
   - Number of active contributors
   - Project age and stability
   - Funding/sponsorship status

5. **Score each risk category:**
   ```markdown
   ## Risk Assessment

   | Risk Category | Score (1-10) | Mitigation Strategy |
   |--------------|-------------|---------------------|
   | Architectural | 3/10 | Adapt to fit [YOUR_SYSTEM] patterns |
   | Dependency | 6/10 | Pin versions, audit updates |
   | Maintenance | 4/10 | Allocate ongoing maintenance time |
   | Community | 2/10 | Active project, low risk |
   | Overall Risk | 4/10 | Medium risk, manageable |
   ```

**Deliverable:** Comprehensive risk assessment with mitigation strategies

---

### Phase 6: Trade-off Analysis (5-10 min)

**Objective:** Understand what [YOUR_SYSTEM] would LOSE by adoption

**Actions:**

1. **For each adoption candidate, analyze:**

   **Benefits (what we gain):**
   - Specific improvements
   - New capabilities
   - Performance gains
   - UX enhancements

   **Costs (what we lose or complicate):**
   - Existing simplicity
   - Current capabilities that break
   - Migration effort required
   - New complexity introduced
   - Philosophical compromises

2. **Migration Complexity Assessment:**
   - What needs to change in [YOUR_SYSTEM]?
   - How many files affected?
   - Breaking changes to existing skills?
   - User-facing changes required?
   - Complexity: Low / Medium / High

3. **Net Value Calculation:**
   ```markdown
   ### Trade-off: [Feature Name]

   **Benefits:**
   - [Benefit 1] (Impact: 8/10)
   - [Benefit 2] (Impact: 6/10)

   **Costs:**
   - [Cost 1] (Severity: 5/10)
   - [Cost 2] (Severity: 3/10)

   **Migration Complexity:** Medium (20-30 files affected)

   **Net Value:** 6.2/10
   **Recommendation:** Adopt with phased approach
   ```

**Deliverable:** Trade-off analysis for each major adoption candidate

---

### Phase 7: Synthesis & Recommendations (10-15 min)

**Objective:** Consolidate findings into actionable recommendations

**Actions:**

1. **Calculate Net Value for each opportunity:**
   ```
   Net Value = (Impact Score) - (Risk Score × 0.5) - (Complexity Score × 0.3)
   ```

2. **Categorize recommendations:**

   **High Value, Low Risk (Adopt):**
   - Net Value > 7.0
   - Quick wins, safe improvements
   - Immediate action recommended

   **High Value, Medium Risk (Pilot):**
   - Net Value 5-7
   - Significant potential, needs validation
   - Recommend small-scale test first

   **Low Value or High Risk (Skip):**
   - Net Value < 3.0
   - Not worth the effort/risk
   - Explain why to skip

3. **Create Implementation Roadmap:**

   **Phase 1: Quick Wins (Days)**
   - [Recommendation 1]: [Brief implementation approach]
   - [Recommendation 2]: [Brief implementation approach]

   **Phase 2: Medium Complexity (Weeks)**
   - [Recommendation 3]: [Implementation approach + risks]

   **Phase 3: Long-term (Months)**
   - [Recommendation 4]: [Strategic approach]

4. **Generate Executive Summary:**
   - 3-5 sentences capturing key findings
   - Bottom-line recommendation
   - Highlight top 1-3 adoption priorities

**Deliverable:** Complete recommendations with roadmap

---

### Final: Generate Comparison Report

**Report Location:**
```
[SKILL_DIR]/MEMORY/comparisons/YYYY-MM-DD_[system-name]-comparison.md
```

**Report Structure:** Use template from InfrastructureComparison/SKILL.md

**Report Sections:**
1. Executive Summary
2. System Overview
3. Component Mapping
4. Gap Analysis
5. What They Do Better
6. Risk Assessment
7. Trade-off Analysis
8. Recommendations (Adopt / Pilot / Skip)
9. Implementation Roadmap
10. Appendices (Scoring Matrix, Code Samples, Constitutional Alignment)

**After generating report:**
- Use Read tool to verify report quality
- Ensure all sections are complete
- Verify scoring calculations
- Check that recommendations are actionable

---

## Completion Checklist

Before concluding workflow, verify:

- [ ] All 7 phases completed
- [ ] Component mapping table created
- [ ] Gap analysis with severity scores
- [ ] Strength analysis with WHY reasoning
- [ ] Risk assessment with scores
- [ ] Trade-off analysis for major features
- [ ] Net Value calculations for all recommendations
- [ ] Recommendations categorized (Adopt/Pilot/Skip)
- [ ] Implementation roadmap with phases
- [ ] Executive summary written
- [ ] Report saved to MEMORY/comparisons/
- [ ] Report filename includes date and system name

---

## Voice Notification Format

When workflow completes:

```
🎯 COMPLETED: [AGENT:[AGENT_NAME]] analyzed [system-name] infrastructure with [N] recommendations: [top recommendation summary]
```

Example:
```
🎯 COMPLETED: [AGENT:[AGENT_NAME]] analyzed Claude Flow infrastructure with 12 recommendations: adopt semantic search, pilot memory compression
```

---

## Tips for Effective Analysis

**1. Be Objective:**
- Acknowledge when they do things better
- Don't defend [YOUR_SYSTEM]'s weaknesses
- Look for genuine improvements

**2. Be Specific:**
- "Better UX" is vague
- "Faster search via HNSW indexing" is specific
- Always explain WHY something is better

**3. Be Practical:**
- Consider implementation complexity
- Think about maintenance burden
- Assess cultural/philosophical fit

**4. Be Constitutional:**
- Always check alignment with [YOUR_SYSTEM] principles
- Reject approaches that violate core values
- Find ways to adapt rather than compromise

**5. Be Thorough:**
- Don't skip phases
- Read actual code, not just docs
- Verify claims with evidence

---

## Common Pitfalls to Avoid

❌ **Superficial analysis:** Reading only README
✅ **Deep analysis:** Reading code, running examples, testing claims

❌ **Feature envy:** "They have X, we need X!"
✅ **Need-based evaluation:** "Does X solve a real [YOUR_SYSTEM] problem?"

❌ **Uncritical adoption:** "This looks cool, let's adopt it!"
✅ **Risk-aware adoption:** "This is valuable, but here are the risks..."

❌ **Defensive dismissal:** "Our way is better!"
✅ **Honest assessment:** "They do this better because..."

❌ **Analysis paralysis:** Endless investigation
✅ **Timeboxed execution:** 60 min max for comprehensive analysis

---

## Integration with Other Skills

**Use LLMWorkflow Plan for:**
- Complex integration planning
- Multi-phase implementation strategies
- When adoption requires architectural changes

**Use LLMWorkflow Implement for:**
- Executing the implementation roadmap
- Building proof-of-concept integrations
- Incremental feature adoption

**Use Documents skill for:**
- Creating presentation-ready comparison reports
- Generating stakeholder briefing documents

---

**Workflow Version:** 1.0
**Last Updated:** 2026-01-18
**Estimated Duration:** 20-60 minutes
**Output:** Comprehensive comparison report with actionable roadmap
