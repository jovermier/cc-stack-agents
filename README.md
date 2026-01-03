# Custom Review Agents

Custom AI agents for code review and test generation with domain-specific skills.

## Overview

This plugin provides **4 specialized agents** and **12 domain knowledge skills** following the **Every marketplace methodology**:

- **Agents** = Personalities and perspectives (how to review)
- **Skills** = Domain knowledge (what to know)

## Architecture

```
agents/              # 4 review/generation agents
├── review/
│   ├── go-reviewer.md
│   ├── graphql-reviewer.md
│   └── nextjs-reviewer.md
└── workflow/
    └── playwright-generator.md

skills/              # 12 domain knowledge skills
├── go-concurrency/       # Goroutines, channels, context
├── go-performance/       # Memory, strings.Builder, I/O
├── go-testing/           # Table-driven tests, race detector
├── go-error-handling/    # Error wrapping, errors.Is/As
├── graphql-schema-design/    # Types, pagination, nullability
├── graphql-resolvers/        # Dataloader, N+1, auth
├── graphql-mutations/        # Payloads, field errors
├── nextjs-server-components/ # Server/Client, data fetching
├── nextjs-performance/       # Images, fonts, caching
├── nextjs-metadata/          # SEO, OpenGraph
├── playwright-page-objects/  # Page Object Model
└── playwright-best-practices/ # Selectors, waits, a11y
```

## Agents

### go-reviewer

Reviews Go code for idiomatic patterns, concurrency safety, and performance.

**Skills used**: `go-concurrency`, `go-performance`, `go-testing`, `go-error-handling`

### graphql-reviewer

Reviews GraphQL schemas, resolvers, and mutations for best practices and performance.

**Skills used**: `graphql-schema-design`, `graphql-resolvers`, `graphql-mutations`

### nextjs-reviewer

Reviews Next.js code for framework best practices and performance.

**Skills used**: `nextjs-server-components`, `nextjs-performance`, `nextjs-metadata`

### playwright-generator

Generates E2E tests with Page Object Model and best practices.

**Skills used**: `playwright-page-objects`, `playwright-best-practices`

## Installation

1. Copy this directory to your Claude Code plugins folder
2. Restart Claude Code
3. Agents and skills will be available

## Usage

Agents are automatically invoked based on context, or explicitly:

```
"Have the Go reviewer review this code"
"Review this GraphQL schema for N+1 queries"
"Check this Next.js component for proper Server Component usage"
"Generate Playwright tests for the checkout flow"
```

Skills are automatically loaded by agents when needed.

## License

MIT
