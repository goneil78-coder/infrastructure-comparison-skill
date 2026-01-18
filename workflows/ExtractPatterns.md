# ExtractPatterns Workflow

**Purpose:** Identify and extract specific architectural patterns and approaches from external systems

**When to use:** User wants to understand "what patterns does X use" without full comparison

---

## Workflow Overview

Focused pattern identification and extraction for learning and potential adoption.

**Expected Duration:** 15-30 minutes depending on pattern complexity
**Output:** Pattern documentation with [YOUR_SYSTEM] applicability assessment

---

## Pattern Categories

### 1. Architectural Patterns
- System organization and structure
- Component interaction patterns
- Separation of concerns approaches
- Modularity strategies

### 2. Code Patterns
- Idioms and conventions
- Reusable abstractions
- Error handling approaches
- Testing strategies

### 3. UX/Workflow Patterns
- User interaction flows
- Command-line interface designs
- Configuration approaches
- Feedback mechanisms

### 4. Integration Patterns
- External service integration
- Plugin/extension systems
- API design patterns
- Data exchange formats

### 5. State Management Patterns
- Persistence approaches
- Caching strategies
- Session management
- Context propagation

---

## Execution Steps

### Step 1: Pattern Discovery (5-10 min)

**Search for pattern mentions:**
```bash
cd /tmp
git clone [repository-url] [system-name]-patterns
cd [system-name]-patterns

# Search documentation for pattern keywords
grep -r "pattern\|architecture\|design" --include="*.md" | head -30

# Look for common pattern files
find . -name "*pattern*" -o -name "*design*" -o -name "ARCHITECTURE*"
```

**Read documentation:**
- ARCHITECTURE.md
- DESIGN.md
- docs/patterns/
- docs/architecture/
- Any design decision documents

**Catalog discovered patterns:**
```markdown
## Discovered Patterns

1. [Pattern Name] - [Brief description]
   - File: [where documented]
   - Category: [Architectural/Code/UX/Integration/State]

2. [Pattern Name] - [Brief description]
   - File: [where implemented]
   - Category: [...]
```

---

### Step 2: Pattern Analysis (10-15 min)

**For each identified pattern:**

1. **Understand the Pattern:**
   - What problem does it solve?
   - How does it work?
   - Why this approach vs alternatives?

2. **Find Implementations:**
   ```bash
   # Search for pattern implementation
   grep -r "[pattern-keyword]" --include="*.ts" --include="*.js" | head -20
   ```

3. **Read Representative Code:**
   - Find 1-3 example files
   - Read implementation
   - Note key characteristics

4. **Document Pattern:**
   ```markdown
   ### Pattern: [Name]

   **Problem:** [What problem does this solve?]

   **Solution:** [How does the pattern work?]

   **Implementation:** [Code example or pseudocode]

   **Advantages:**
   - [Benefit 1]
   - [Benefit 2]

   **Disadvantages:**
   - [Limitation 1]
   - [Limitation 2]

   **When to Use:**
   - [Condition 1]
   - [Condition 2]
   ```

---

### Step 3: [YOUR_SYSTEM] Comparison (5-10 min)

**For each pattern, compare to [YOUR_SYSTEM]:**

**Questions:**
1. Does [YOUR_SYSTEM] use this pattern?
   - Yes, same approach
   - Yes, but different implementation
   - No, uses different pattern
   - No, doesn't address this concern

2. If [YOUR_SYSTEM] uses different pattern, why?
   - Different architectural constraints
   - Different problem space
   - Different philosophy
   - Historical reasons

3. Is their pattern better for [YOUR_SYSTEM]'s use case?
   - Yes, would improve [YOUR_SYSTEM]
   - Maybe, depends on context
   - No, [YOUR_SYSTEM]'s approach is better
   - Not applicable to [YOUR_SYSTEM]

**Document comparison:**
```markdown
### [YOUR_SYSTEM] Comparison

**Current [YOUR_SYSTEM] Approach:**
[How [YOUR_SYSTEM] currently handles this, or "[YOUR_SYSTEM] doesn't address this"]

**Difference:**
[Key differences between their pattern and [YOUR_SYSTEM]'s approach]

**Applicability to [YOUR_SYSTEM]:**
- **Better for [YOUR_SYSTEM]?** [Yes/Maybe/No]
- **Reason:** [Explanation]
- **Adoption Impact:** [What would change in [YOUR_SYSTEM]]
```

---

### Step 4: Adoption Assessment (5 min)

**For patterns worth considering:**

**Score each pattern:**
- **Value:** How much would [YOUR_SYSTEM] improve? (1-10)
- **Fit:** How well does it align with [YOUR_SYSTEM] principles? (1-10)
- **Complexity:** How hard to implement? (1-10, lower is easier)

**Calculate adoption score:**
```
Adoption Score = (Value × 0.5) + (Fit × 0.3) - (Complexity × 0.2)

Interpretation:
  >7.0 = Strong candidate for adoption
  5-7  = Worth experimenting with
  3-5  = Low priority
  <3.0 = Skip
```

**Categorize:**
```markdown
## Adoption Recommendations

### High Priority (Adopt)
- [Pattern 1]: Score X.X - [Brief rationale]
- [Pattern 2]: Score X.X - [Brief rationale]

### Medium Priority (Experiment)
- [Pattern 3]: Score X.X - [Brief rationale]

### Low Priority (Skip)
- [Pattern 4]: Score X.X - [Brief rationale]
```

---

### Step 5: Implementation Guidance (5 min)

**For high-priority patterns:**

**Provide implementation notes:**
```markdown
### Implementation: [Pattern Name]

**Files to Modify:**
- [[YOUR_SYSTEM] file 1]: [What changes]
- [[YOUR_SYSTEM] file 2]: [What changes]

**New Files to Create:**
- [File path]: [Purpose]

**Migration Strategy:**
1. [Step 1]
2. [Step 2]
3. [Step 3]

**Risks:**
- [Risk 1 with mitigation]
- [Risk 2 with mitigation]

**Testing Approach:**
- [How to validate pattern works in [YOUR_SYSTEM]]

**Rollback Plan:**
- [How to revert if pattern doesn't work out]
```

---

## Output Report

**Save to:** `[SKILL_DIR]/MEMORY/patterns/YYYY-MM-DD_[system-name]-patterns.md`

**Report Structure:**

```markdown
# Pattern Extraction: [System Name]

**Date:** YYYY-MM-DD
**Source:** [Repository URL]
**Focus:** [What patterns were sought]

---

## Summary

[2-3 sentences: key patterns found and adoption recommendation]

---

## Extracted Patterns

### 1. [Pattern Name]

**Category:** [Architectural/Code/UX/Integration/State]

**Problem:** [What problem this solves]

**Solution:** [How the pattern works]

**Implementation:**
```[language]
[Code example]
```

**Advantages:**
- [Advantage 1]
- [Advantage 2]

**Disadvantages:**
- [Limitation 1]

**When to Use:**
- [Use case 1]
- [Use case 2]

#### [YOUR_SYSTEM] Comparison

**Current [YOUR_SYSTEM] Approach:**
[How [YOUR_SYSTEM] handles this currently]

**Key Differences:**
[What's different about their approach]

**Applicability Assessment:**
- Value: X/10
- Fit: X/10
- Complexity: X/10
- **Adoption Score:** X.X/10
- **Recommendation:** [Adopt / Experiment / Skip]

**If Adopted, Impact:**
[What would change in [YOUR_SYSTEM]]

---

[Repeat for each pattern]

---

## Adoption Roadmap

### Phase 1: Quick Wins
- [Pattern X]: [Implementation approach]

### Phase 2: Experimental
- [Pattern Y]: [Pilot approach]

### Phase 3: Deferred
- [Pattern Z]: [Why deferred]

---

## References

- [Link to their architecture docs]
- [Link to pattern implementation files]
- [Link to relevant discussions/issues]
```

---

## Pattern-Specific Searches

**For common pattern types:**

### Agent Orchestration Patterns
```bash
grep -r "agent\|orchestrat\|coordinat" --include="*.ts" | head -30
find . -path "*/agent*" -o -path "*/orchestr*"
```

### Memory/State Management Patterns
```bash
grep -r "memory\|state\|context\|persist" --include="*.ts" | head -30
find . -path "*/memory*" -o -path "*/state*"
```

### CLI/UX Patterns
```bash
grep -r "cli\|command\|interface" --include="*.ts" | head -30
find . -path "*/cli*" -o -path "*/commands*"
```

### Integration Patterns
```bash
grep -r "integration\|plugin\|extension\|hook" --include="*.ts" | head -30
find . -path "*/integrations*" -o -path "*/plugins*"
```

---

## Checklist

- [ ] Patterns discovered and cataloged
- [ ] Each pattern analyzed (problem/solution/implementation)
- [ ] [YOUR_SYSTEM] comparison completed for each pattern
- [ ] Adoption scores calculated
- [ ] Patterns categorized (Adopt/Experiment/Skip)
- [ ] Implementation guidance provided for high-priority patterns
- [ ] Report saved to MEMORY/patterns/
- [ ] References and code examples included

---

## Voice Notification Format

```
🎯 COMPLETED: [AGENT:[AGENT_NAME]] extracted [N] patterns from [system-name]: [top pattern recommendation]
```

Example:
```
🎯 COMPLETED: [AGENT:[AGENT_NAME]] extracted 8 patterns from Claude Flow: adopt semantic search indexing pattern
```

---

## Tips for Pattern Extraction

**Focus on:**
- ✅ Reusable, general patterns (not one-off implementations)
- ✅ Patterns that solve real problems
- ✅ Well-documented patterns
- ✅ Patterns with clear benefits

**Avoid:**
- ❌ Implementation details without pattern
- ❌ Language-specific idioms (unless that's the focus)
- ❌ Patterns tied to specific dependencies
- ❌ Over-engineered patterns for simple problems

**Look for patterns that:**
- Solve problems [YOUR_SYSTEM] has
- Align with [YOUR_SYSTEM]'s principles
- Can be adapted to TypeScript
- Have clear adoption path

---

**Workflow Version:** 1.0
**Last Updated:** 2026-01-18
**Estimated Duration:** 15-30 minutes
**Output:** Pattern documentation with adoption guidance
