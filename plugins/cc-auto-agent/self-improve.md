---
description: Trigger self-improvement to auto-detect project needs and install relevant plugins and skills
---

# Self-Improve

Trigger the self-improvement process to analyze your project and automatically install relevant plugins and skills.

## Usage

```
/self-improve
```

## What It Does

1. **Analyzes your project** to detect:
   - Programming languages
   - Frameworks and libraries
   - Testing frameworks
   - Package managers

2. **Installs relevant plugins** from marketplaces:
   - `cc-go` for Go projects
   - `cc-graphql` for GraphQL projects
   - `cc-nextjs` for Next.js projects
   - `cc-playwright` for Playwright testing

3. **Fetches relevant skills** from SkillsMP:
   - Uses AI semantic search
   - Reviews top results
   - Installs up to 5 relevant skills

## Configuration

### Environment Variables

```bash
# Set API key for SkillsMP (required for skill installation)
export SKILLSMP_API_KEY=sk_live_your_key

# Max skills to install per run (default: 5)
export AUTO_SKILL_MAX=5

# Disable skill installation if needed
export AUTO_SKILL_ENABLED=false
```

### Project Settings

Add to `.claude/settings.json`:

```json
{
  "selfImprove": {
    "skipMarketplaces": [],
    "skipPlugins": [],
    "preferredSkills": []
  }
}
```

## Example

```
/self-improve
```

Output:
```
🔄 Self-Improvement Analysis

Detected project:
  • Languages: Go, TypeScript
  • Frameworks: GraphQL, Next.js
  • Testing: Playwright

Plugins to install:
  → cc-go@cc-stack-marketplace
  → cc-graphql@cc-stack-marketplace
  → cc-nextjs@cc-stack-marketplace

Skills to install (from SkillsMP):
  → go-performance (⭐ 234)
  → graphql-schema-design (⭐ 156)
  → nextjs-optimization (⭐ 203)

Install 6 enhancements? [Y/n]
```

## Safety

- Always shows what will be installed before acting
- Never removes existing plugins or skills
- Skips already installed items
- Respects your skip/prefer lists
- Requires API key for SkillsMP integration
