---
description: Search and install skills from SkillsMP.com marketplace using keyword search
---

# SkillsMP Skill Installer (Keyword Search)

Search and install Claude skills from the SkillsMP.com marketplace using keyword matching.

## Usage

```
/skill-add <search-query>
```

## Examples

- `/skill-add go performance` - Search for Go performance skills
- `/skill-add graphql` - Find GraphQL-related skills
- `/skill-add testing` - Browse testing skills
- `/skill-add code review` - Find code review skills

## How it works

1. Calls SkillsMP API: `GET /api/v1/skills/search?q=<query>` with API key from `SKILLSMP_API_KEY` env var
2. Displays top 5 results with name, description, stars, and repository
3. Reviews each skill for relevance to the current project
4. Prompts you to select skills to install
5. Clones the skill's GitHub repo to `.claude/skills/` directory

## Installation locations

- **Project skills**: `.claude/skills/` (project-specific, shared with team)
- **Personal skills**: `~/.claude/skills/` (personal, across all projects)

Skills are automatically discovered by Claude Code when placed in these directories.

## API Details

**Endpoint**: `GET https://skillsmp.com/api/v1/skills/search`

**Parameters**:
- `q` (required): Search query
- `page` (optional): Page number (default: 1)
- `limit` (optional): Items per page (default: 20, max: 100)
- `sortBy` (optional): Sort by `stars` or `recent`

**Headers**:
- `Authorization: Bearer SKILLSMP_API_KEY`

## Example Implementation

When user runs `/skill-add go testing`:

```bash
# Fetch matching skills
curl -X GET "https://skillsmp.com/api/v1/skills/search?q=go+testing&limit=5&sortBy=stars" \
  -H "Authorization: Bearer $SKILLSMP_API_KEY"
```

Review results, then install selected skill:
```bash
git clone https://github.com/user/repo.git .claude/skills/skill-name
```
