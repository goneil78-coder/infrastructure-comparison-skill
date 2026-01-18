# QuickAssess Workflow

**Purpose:** Rapid initial assessment of external AI infrastructure system

**When to use:** User wants quick "is this worth investigating" determination, not full analysis

---

## Workflow Overview

Lightweight 15-minute assessment to determine if deeper analysis is warranted.

**Expected Duration:** 10-15 minutes
**Output:** Go/No-Go recommendation with brief rationale

---

## Execution Steps

### Step 1: Quick Repository Scan (3 min)

**Read these files (parallel):**
- README.md (overview, features, purpose)
- package.json or requirements.txt (dependencies)
- ARCHITECTURE.md or docs/ (if exists)

**Extract:**
- What problem does it solve?
- Who is it for?
- What's the core approach/architecture?
- How mature is it? (GitHub stars, commits, age)

---

### Step 2: Relevance Filter (2 min)

**Ask these questions:**

1. **Is it relevant to [YOUR_SYSTEM]'s domain?**
   - AI infrastructure? ✅
   - Code assistant tooling? ✅
   - Agent orchestration? ✅
   - Completely unrelated? ❌ Stop here

2. **Does it solve a problem [YOUR_SYSTEM] has?**
   - Addresses known [YOUR_SYSTEM] pain point? ✅
   - Fills identified gap? ✅
   - Solves problem [YOUR_SYSTEM] doesn't have? ⚠️ Lower priority

3. **Is it compatible with [YOUR_SYSTEM]'s principles?**
   - CLI-first approach? ✅
   - Deterministic code patterns? ✅
   - Violates constitutional principles? ❌ Flag concern

**If fails relevance check:** Recommend "Skip - not relevant to [YOUR_SYSTEM]"

---

### Step 3: Novelty Check (3 min)

**Identify what's unique or interesting:**

```bash
# Quick search for novel concepts
grep -r "interesting-concept" --include="*.md" | head -10
```

**Questions:**
- What do they do differently from [YOUR_SYSTEM]?
- What novel approaches do they use?
- What's their "killer feature"?

**Categorize:**
- **Novel & Valuable:** Unique approach that solves real problem
- **Incremental:** Better implementation of existing concept
- **Derivative:** Nothing new, just different implementation

**If nothing novel:** Recommend "Skip - no unique value"

---

### Step 4: Quick Quality Assessment (3 min)

**Check indicators:**

1. **Code Quality:**
   - Open 2-3 random source files
   - Are they readable?
   - Good structure and naming?
   - Test coverage evident?

2. **Documentation:**
   - Clear README?
   - Architecture docs?
   - Examples provided?
   - Setup instructions clear?

3. **Community Health:**
   ```bash
   # Quick stats
   git log --since="1 month ago" --oneline | wc -l  # Recent commits
   gh repo view --json stargazers,forks,issues | head -20
   ```
   - Active development?
   - Community engagement?
   - Issue response quality?

**Red Flags:**
- ❌ No commits in 6+ months
- ❌ Many open issues, few responses
- ❌ Poor code quality in samples
- ❌ Missing or terrible documentation

**If quality concerns:** Note in recommendation

---

### Step 5: Impact Potential (2 min)

**Estimate potential impact on [YOUR_SYSTEM]:**

**Quick Scoring:**
- **Impact Potential:** How much better could [YOUR_SYSTEM] be? (1-10)
- **Adoption Risk:** How risky to integrate? (1-10)
- **Complexity:** How hard to implement? (1-10)

**Rules of Thumb:**
```
Impact 8-10, Risk 1-3: DEFINITELY investigate
Impact 6-8, Risk 4-6: PROBABLY investigate
Impact <6: SKIP unless very low risk
Risk >8: SKIP unless transformative impact
```

---

### Step 6: Recommendation (2 min)

**Output Format:**

```markdown
# Quick Assessment: [System Name]

**Assessment Date:** YYYY-MM-DD
**Repository:** [URL]
**Time Spent:** 15 minutes

## Bottom Line
[Go/No-Go/Maybe] - [One sentence rationale]

## Quick Scores
- Impact Potential: X/10
- Adoption Risk: X/10
- Implementation Complexity: X/10
- **Net Value:** X.X/10

## What They Do
[2-3 sentences explaining their purpose and approach]

## What's Novel
- [Unique aspect 1]
- [Unique aspect 2]

## Potential Value to [YOUR_SYSTEM]
[2-3 sentences on what [YOUR_SYSTEM] could gain]

## Concerns
- [Concern 1]
- [Concern 2]

## Recommendation
**[INVESTIGATE FURTHER / SKIP / WATCH]**

[2-3 sentences explaining why]

## Next Steps
[If "Investigate Further":]
- Run full CompareSystem workflow
- Focus on: [specific areas]
- Timeline: [when to do full analysis]

[If "Skip":]
- Reason: [why not worth pursuing]
- Revisit if: [conditions that would change assessment]

[If "Watch":]
- Monitor for: [specific developments]
- Check again in: [timeframe]
```

---

## Decision Tree

```
START
  ↓
Is it relevant to [YOUR_SYSTEM]? ─NO→ SKIP
  ↓ YES
Does it solve [YOUR_SYSTEM] problem? ─NO→ WATCH
  ↓ YES
Is it novel/interesting? ─NO→ SKIP
  ↓ YES
Good quality indicators? ─NO→ WATCH (quality concerns)
  ↓ YES
Impact > 6 AND Risk < 8? ─NO→ SKIP
  ↓ YES
INVESTIGATE FURTHER → Run CompareSystem workflow
```

---

## Quick Assessment Checklist

- [ ] README read
- [ ] Dependencies checked
- [ ] Relevance confirmed
- [ ] Novelty identified
- [ ] Quality spot-checked
- [ ] Scores assigned
- [ ] Recommendation made
- [ ] Next steps defined

---

## Voice Notification Format

```
🎯 COMPLETED: [AGENT:[AGENT_NAME]] quick assessment of [system-name]: [recommendation]
```

Example:
```
🎯 COMPLETED: [AGENT:[AGENT_NAME]] quick assessment of Aider: investigate further - novel code editing approach
```

---

## Tips for Quick Assessment

**Do:**
- ✅ Trust your instincts
- ✅ Focus on signal, not noise
- ✅ Be decisive (Go/No-Go/Watch)
- ✅ Time-box strictly (15 min max)

**Don't:**
- ❌ Read everything
- ❌ Get lost in details
- ❌ Over-analyze
- ❌ Avoid making a call

**Remember:**
- This is a filter, not full analysis
- False positives okay (can do full analysis later)
- False negatives costly (miss valuable systems)
- **Bias toward "Investigate Further" when uncertain**

---

**Workflow Version:** 1.0
**Last Updated:** 2026-01-18
**Estimated Duration:** 10-15 minutes
**Output:** Go/No-Go recommendation
