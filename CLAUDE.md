# Custom Review Agents

This plugin extends Claude Code with specialized code review and test generation agents, following the Every marketplace methodology.

## Architecture

**Agents** = Review perspectives and personalities (how to think)
**Skills** = Domain knowledge bases (what to know)

This separation enables:
- Reusable domain knowledge across agents
- Progressive disclosure (skills loaded only when needed)
- Scalable architecture (more skills without bloating agents)

## Agents

### Code Review Agents

- **go-reviewer** ([agents/review/go-reviewer.md](agents/review/go-reviewer.md)) - Go specialist for idiomatic patterns, concurrency, and performance
- **graphql-reviewer** ([agents/review/graphql-reviewer.md](agents/review/graphql-reviewer.md)) - GraphQL specialist for schema design and N+1 prevention
- **nextjs-reviewer** ([agents/review/nextjs-reviewer.md](agents/review/nextjs-reviewer.md)) - Next.js specialist for Server Components and App Router

### Workflow Agents

- **playwright-generator** ([agents/workflow/playwright-generator.md](agents/workflow/playwright-generator.md)) - Playwright E2E test generator with Page Object Model

## Skills

### Go Skills

- **go-concurrency** ([skills/go-concurrency/SKILL.md](skills/go-concurrency/SKILL.md)) - Goroutines, channels, context, sync
- **go-performance** ([skills/go-performance/SKILL.md](skills/go-performance/SKILL.md)) - Memory, strings.Builder, I/O, allocations
- **go-testing** ([skills/go-testing/SKILL.md](skills/go-testing/SKILL.md)) - Table-driven tests, race detector, coverage
- **go-error-handling** ([skills/go-error-handling/SKILL.md](skills/go-error-handling/SKILL.md)) - Error wrapping, custom errors, errors.Is/As

### GraphQL Skills

- **graphql-schema-design** ([skills/graphql-schema-design/SKILL.md](skills/graphql-schema-design/SKILL.md)) - Types, pagination, nullability, naming
- **graphql-resolvers** ([skills/graphql-resolvers/SKILL.md](skills/graphql-resolvers/SKILL.md)) - Dataloader, N+1 prevention, auth, context
- **graphql-mutations** ([skills/graphql-mutations/SKILL.md](skills/graphql-mutations/SKILL.md)) - Payloads, field errors, input objects

### Next.js Skills

- **nextjs-server-components** ([skills/nextjs-server-components/SKILL.md](skills/nextjs-server-components/SKILL.md)) - Server/Client Components, data fetching, Server Actions
- **nextjs-performance** ([skills/nextjs-performance/SKILL.md](skills/nextjs-performance/SKILL.md)) - Images, fonts, dynamic imports, caching
- **nextjs-metadata** ([skills/nextjs-metadata/SKILL.md](skills/nextjs-metadata/SKILL.md)) - Metadata API, SEO, OpenGraph

### Playwright Skills

- **playwright-page-objects** ([skills/playwright-page-objects/SKILL.md](skills/playwright-page-objects/SKILL.md)) - Page Object Model, fixtures, helpers
- **playwright-best-practices** ([skills/playwright-best-practices/SKILL.md](skills/playwright-best-practices/SKILL.md)) - Selectors, waits, accessibility, flaky prevention

## Quick Reference

| Agent | Skills Used |
|-------|-------------|
| go-reviewer | go-concurrency, go-performance, go-testing, go-error-handling |
| graphql-reviewer | graphql-schema-design, graphql-resolvers, graphql-mutations |
| nextjs-reviewer | nextjs-server-components, nextjs-performance, nextjs-metadata |
| playwright-generator | playwright-page-objects, playwright-best-practices |

## Usage Notes

- Agents delegate to skills for domain knowledge
- Skills are loaded progressively based on code patterns
- Each skill has reference files for detailed content
- Agents provide the review perspective and process
