# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

**2cerebro** is a specification and documentation repository for an LLM-powered knowledge management system ("Second Brain"). It contains architectural documentation and prompt templates written in Portuguese-Brazilian. There is no build/compile/test pipeline — this is a pure Markdown documentation project.

## Repository Structure

```
2cerebro/
└── doc/
    ├── karpathy_llm_kb.md      # Core architecture concept (3-layer LLM wiki)
    ├── second_brain_llm.md     # Full system overview with Claude Code integration
    ├── prompt_wiki_llm.md      # Ready-to-use implementation prompts (PT-BR, 2 versions)
    └── inema_llm_wiki.md       # Simplified course-format summary + base prompts
```

## Architecture: The LLM Wiki System

The documentation describes a **three-layer knowledge architecture** where the LLM acts as a "librarian + compiler" rather than a retrieval engine:

```
Raw Sources (immutable) → LLM Compiler → Persistent Wiki (Markdown)
```

**Three core layers:**
- `raw/` — Original source documents, never modified
- `wiki/` — LLM-compiled knowledge pages (summaries, concepts, entities, comparisons)
- Schema files — `CLAUDE.md` (rules), `index.md` (navigation catalog), `log.md` (history)

**Three core operations:**
- **Ingest** — LLM reads raw source → generates wiki pages → updates `index.md` and `log.md`
- **Query** — LLM reads `index.md` → finds relevant pages → synthesizes response
- **Lint** — LLM audits for contradictions, orphaned pages, and missing links

This contrasts with RAG: instead of embedding and searching at query time, knowledge is pre-compiled into structured Markdown, reducing token usage by ~95% per query.

## Working in This Repository

This repo holds the **specification**. When implementing an actual wiki instance:
1. Use Obsidian as the vault interface
2. Deploy the prompts from `doc/prompt_wiki_llm.md` to bootstrap a new vault
3. The operational vault lives separately (with its own `CLAUDE.md`, `index.md`, `log.md`)

When editing documentation here, maintain consistency with the PT-BR terminology used throughout (e.g., "ingerir", "wiki", "compilar").
