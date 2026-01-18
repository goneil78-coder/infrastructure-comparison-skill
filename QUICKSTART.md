# Quick Start Guide

Get the Infrastructure Comparison Skill up and running in 5 minutes.

## Step 1: Clone the Repository

```bash
git clone https://github.com/[YOUR_USERNAME]/infrastructure-comparison-skill.git
cd infrastructure-comparison-skill
```

## Step 2: Copy to Your Skill Directory

```bash
# Copy to your AI infrastructure's skill directory
cp -r . [YOUR_SKILL_DIRECTORY]/InfrastructureComparison
cd [YOUR_SKILL_DIRECTORY]/InfrastructureComparison
```

## Step 3: Find and Replace Placeholders

```bash
# Replace with your system name (e.g., "MyAI", "Jarvis", "Assistant")
find . -type f -name "*.md" -exec sed -i 's/\[YOUR_SYSTEM\]/YourSystemName/g' {} +

# Replace with your skill directory path (e.g., ~/.ai/, ~/.assistant/)
find . -type f -name "*.md" -exec sed -i 's|\[SKILL_DIR\]|~/.your-path|g' {} +

# Replace with your name
find . -type f -name "*.md" -exec sed -i 's/\[YOUR_NAME\]/YourName/g' {} +

# Replace with your agent name (e.g., "assistant", "helper")
find . -type f -name "*.md" -exec sed -i 's/\[AGENT_NAME\]/your-agent/g' {} +
```

## Step 4: Customize Constitutional Principles

Edit `SKILL.md` and replace the constitutional principles section with your own system's principles.

**Find this section:**
```markdown
**[YOUR_SYSTEM] Constitutional Principles:**
1. ✅ **CLI-First Architecture** - Tools wrap prompts, not vice versa
2. ✅ **Deterministic Code First** - Prefer deterministic code over prompts
...
```

**Replace with your principles:**
```markdown
**MyAI Constitutional Principles:**
1. ✅ **Your Core Principle 1** - Description
2. ✅ **Your Core Principle 2** - Description
...
```

## Step 5: Test the Skill

Try a quick assessment:

```bash
# In your AI interface
"Quick assessment of Claude Flow"
```

Or run a comprehensive comparison:

```bash
"Compare Aider infrastructure to my system"
```

## Step 6: Review Your First Report

Check the generated report at:
```
[SKILL_DIR]/MEMORY/comparisons/YYYY-MM-DD_[system-name]-comparison.md
```

## Example Complete Setup

```bash
# Clone
git clone https://github.com/yourname/infrastructure-comparison-skill.git
cd infrastructure-comparison-skill

# Copy to your skill directory
cp -r . ~/.ai/skills/InfrastructureComparison
cd ~/.ai/skills/InfrastructureComparison

# Customize
find . -type f -name "*.md" -exec sed -i 's/\[YOUR_SYSTEM\]/MyAI/g' {} +
find . -type f -name "*.md" -exec sed -i 's|\[SKILL_DIR\]|~/.ai|g' {} +
find . -type f -name "*.md" -exec sed -i 's/\[YOUR_NAME\]/Alice/g' {} +
find . -type f -name "*.md" -exec sed -i 's/\[AGENT_NAME\]/assistant/g' {} +

# Edit constitutional principles in SKILL.md (use your favorite editor)
vim SKILL.md  # or nano, code, etc.

# Test
echo "Ready! Try: 'Quick assessment of Claude Flow'"
```

## Troubleshooting

**Issue:** Skill not activating

**Solution:** Check that your AI system's skill routing recognizes the trigger phrases. You may need to:
- Restart your AI system
- Check skill activation logs
- Verify the skill directory path is correct

**Issue:** Reports not saving

**Solution:** Ensure the MEMORY directory exists:
```bash
mkdir -p [SKILL_DIR]/MEMORY/comparisons/
```

**Issue:** Git clone fails on external repos

**Solution:** Ensure you have:
- Git installed and configured
- SSH keys set up for GitHub (if using SSH URLs)
- Network access to clone repositories

## Next Steps

1. Read the full [README.md](README.md) for detailed documentation
2. Review the [workflows/](workflows/) directory to understand each workflow
3. Try each workflow type (CompareSystem, QuickAssess, ExtractPatterns, SynthesizeReport)
4. Customize scoring weights based on your priorities
5. Add domain-specific assessment criteria to workflows

## Getting Help

- Read the full [README.md](README.md) for comprehensive documentation
- Review example outputs in the README
- Check the scoring framework section for guidance on interpretation
- Review each workflow's documentation in the `workflows/` directory

---

**Estimated setup time:** 5-10 minutes
**First comparison:** 10-60 minutes depending on workflow type
