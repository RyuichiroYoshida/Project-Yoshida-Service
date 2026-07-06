# Project Context Bootstrap

## Repository

Repository: `RyuichiroYoshida/Project-Yoshida-Service`

This repository will be used to build a **technical knowledge management system**.

## Project Goal

The goal is not just to collect technical articles.

The goal is to build a system that can:

* collect technical articles and trends
* summarize them
* record what I read
* extract what I learned
* convert articles into reusable knowledge
* store knowledge as structured context
* make the knowledge usable by AI agents, Codex CLI, Codex Cloud, and future tools

The long-term goal is to turn my reading history and technical learning into an asset.

## Background

I currently check summarized technical articles through Chrome Discover during free time, but I rarely read the full articles.

I want a system that helps me:

* understand current technical trends quickly
* decide which articles are worth reading
* save useful articles
* summarize articles
* add my own learning notes
* search and reuse accumulated knowledge later
* provide structured context to AI agents

This should become a **technical knowledge management system**, not just an RSS reader or article summary tool.

## Core Concept

There are two major types of context:

1. **Shared context**

   * reusable knowledge, rules, expertise, and experience across projects

2. **Project-specific context**

   * concrete context for a specific project

The system should support both.

## Proposed Context Directory Structure

```text
context/
│
├── shared/
│   ├── domains/
│   ├── knowledge/
│   ├── expertise/
│   ├── experience/
│   └── rules/
│
└── projects/
    └── tech-knowledge/
        │
        ├── context/
        │   ├── domain/
        │   ├── rules/
        │   ├── knowledge/
        │   └── expertise/
        │
        ├── docs/
        ├── prompts/
        ├── agents/
        ├── workflows/
        └── decisions/
```

## Directory Responsibilities

### `context/shared/domains/`

Shared domain-level context.

Use this for broad technical areas such as:

* backend
* database
* AWS
* security
* AI
* software architecture

This directory describes the worldview and basic assumptions of each technical domain.

### `context/shared/knowledge/`

Shared conceptual knowledge.

Use this for "What is X?" type knowledge.

Examples:

* OAuth
* goroutine
* Clean Architecture
* RAG
* MCP
* vector search
* API design
* SQL transaction

Each file should ideally represent one concept.

### `context/shared/expertise/`

Shared practical knowledge.

Use this for "How should X be designed or implemented?" type knowledge.

Examples:

* REST API design
* worker pool design
* repository pattern usage
* error handling strategy
* authentication design
* logging design

This is more practical than `knowledge/`.

### `context/shared/experience/`

Personal experience and lessons learned.

Use this for:

* implementation mistakes
* things learned from debugging
* PR review feedback
* failed approaches
* successful patterns
* project retrospectives

This is valuable because it represents personal knowledge that cannot be obtained directly from public articles.

### `context/shared/rules/`

Reusable rules for development and AI behavior.

Use this for:

* coding rules
* architecture rules
* context writing rules
* naming rules
* markdown rules
* security rules
* review rules

This directory should act as a common rulebook.

## Project-Specific Context

### `context/projects/tech-knowledge/`

This is the project-specific context for the technical knowledge management system.

It should contain concrete information for this project only.

### `context/projects/tech-knowledge/context/`

Project-specific context.

Use this for knowledge, rules, expertise, and domain definitions that only apply to this project.

For example:

* this project's definition of a knowledge card
* this project's article ingestion policy
* this project's summary format
* this project's tagging policy
* this project's agent behavior rules

### `context/projects/tech-knowledge/docs/`

Project documentation.

Expected files:

```text
overview.md
requirements.md
architecture.md
database.md
api.md
roadmap.md
glossary.md
constraints.md
```

### `context/projects/tech-knowledge/prompts/`

Prompt templates used by AI agents.

Examples:

```text
summarize-article.md
extract-tags.md
create-knowledge-card.md
review-context.md
weekly-summary.md
```

### `context/projects/tech-knowledge/agents/`

Agent definitions.

Examples:

```text
article-ingestion-agent.md
summary-agent.md
tagging-agent.md
knowledge-card-agent.md
review-agent.md
```

Each agent file should define:

* role
* goal
* input
* output
* context to read
* rules to follow
* failure cases

### `context/projects/tech-knowledge/workflows/`

Workflow definitions.

Examples:

```text
article-ingestion.md
article-summary.md
knowledge-card-creation.md
weekly-review.md
context-maintenance.md
```

Each workflow should describe the process step by step.

### `context/projects/tech-knowledge/decisions/`

Architecture Decision Records.

Examples:

```text
0001-use-markdown-for-context.md
0002-use-project-specific-context.md
0003-use-discord-notification.md
0004-use-ai-assisted-summary.md
```

Each decision file should include:

* context
* decision
* reason
* alternatives considered
* consequences

## MVP Scope

The first MVP should focus on:

1. register article URL
2. save title, URL, and metadata
3. generate a short summary using AI
4. add my own memo
5. attach tags
6. manage read status
7. generate a daily or weekly summary
8. store the result as reusable Markdown context

The MVP should avoid overbuilding.

Do not start with:

* browser extension
* complex web dashboard
* full RAG system
* vector database
* advanced knowledge graph
* multi-agent automation

Those can be added later.

## Article Knowledge Model

An article should not only be stored as a URL.

A useful article record should include:

```yaml
title:
url:
source:
published_at:
read_at:
status:
tags:
summary:
learned:
related_concepts:
related_projects:
priority:
```

Recommended status values:

```text
unread
summarized
reading
read
archived
```

## Knowledge Card Concept

A knowledge card is different from an article.

An article is a source.

A knowledge card is reusable understanding extracted from one or more sources.

Example:

```text
Article:
- Go worker pool article

Knowledge cards:
- goroutine
- channel
- worker pool
- goroutine leak
- sync.WaitGroup
```

Knowledge cards should be stored as independent Markdown files.

## Context Writing Rules

Create these rules first:

```text
context/shared/rules/context/
├── directory.md
├── granularity.md
├── metadata.md
├── linking.md
├── naming.md
└── lifecycle.md
```

### Important principles

* one file should represent one concept or one decision
* avoid large files that mix multiple topics
* use YAML front matter
* use consistent tags
* add related links
* separate public knowledge from personal experience
* separate shared context from project-specific context
* write for future AI agents as well as future myself

## Recommended Front Matter

```yaml
---
title:
summary:
type:
tags:
aliases:
status:
created:
updated:
related:
---
```

Possible `type` values:

```text
domain
knowledge
expertise
experience
rule
project-doc
prompt
agent
workflow
decision
```

## AI Context Loading Order

When AI agents work on this project, they should read context in this order:

1. `context/shared/rules/`
2. `context/shared/knowledge/`
3. `context/shared/expertise/`
4. `context/shared/experience/`
5. `context/projects/tech-knowledge/context/`
6. `context/projects/tech-knowledge/docs/`
7. `context/projects/tech-knowledge/workflows/`
8. `context/projects/tech-knowledge/agents/`
9. task-specific files

This order allows the agent to understand:

* common rules
* shared knowledge
* practical expertise
* personal experience
* project-specific assumptions
* current requirements
* target workflow
* assigned role

## Initial Tasks

Start with these tasks:

1. Create the `context/` directory structure
2. Create `context/shared/rules/context/`
3. Add rules for directory structure, granularity, metadata, linking, naming, and lifecycle
4. Create `context/projects/tech-knowledge/docs/overview.md`
5. Create `context/projects/tech-knowledge/docs/requirements.md`
6. Create `context/projects/tech-knowledge/docs/roadmap.md`
7. Create `context/projects/tech-knowledge/decisions/0001-use-markdown-context.md`
8. Create a sample article context file
9. Create a sample knowledge card
10. Create an initial summarization prompt

## Development Policy

Prefer a small and maintainable MVP.

Recommended initial stack:

* Markdown for context storage
* Git for version control
* simple CLI or script first
* later add API or UI if needed
* AI-generated summaries should always allow human notes
* human notes are more valuable than AI summaries

## Important Design Principle

The system should not only answer:

> What articles did I read?

It should answer:

> What did I learn?
> Why was it useful?
> How does it relate to my development work?
> Can AI reuse this context later?

## Expected Future Extensions

Possible later extensions:

* Discord daily notification
* RSS/API article ingestion
* Qiita/Zenn/Hacker News integration
* Notion or Obsidian export
* full-text search
* embedding search
* RAG
* knowledge graph
* browser extension
* AI agent automation
* weekly/monthly learning review
