# Agent Phantom Recovery

> Autonomous Engineering Intelligence Platform

**Tagline**

```text
Plan.
Investigate.
Reason.
Verify.
Execute.
```

---

# Table of Contents

1. Introduction
2. Vision
3. Problem Statement
4. Core Principles
5. System Overview
6. Core Capabilities
7. Architecture Overview
8. LLM Architecture
9. Tool Architecture
10. Memory Architecture
11. RAG Architecture
12. Antigravity IDE
13. Repository Structure
14. Technology Stack
15. Development Roadmap
16. Build Instructions For Antigravity
17. Engineering Principles
18. Repository Reading Order
19. Current Status
20. Future Roadmap

---

# Introduction

Agent Phantom Recovery is a long-horizon autonomous engineering platform designed to investigate, analyze, repair, verify, and complete complex software engineering tasks.

It is not a chatbot.

It is not a code-completion tool.

It is not a traditional AI assistant.

Its purpose is to function as an engineering execution system capable of understanding repositories, planning investigations, using tools, reasoning about architecture, generating fixes, verifying results, and completing objectives.

The system combines:

```text
LLMs
+
Agents
+
Tools
+
Memory
+
RAG
+
Repository Intelligence
+
Verification
```

into a unified execution platform.

---

# Vision

Traditional AI systems focus on generating answers.

Agent Phantom Recovery focuses on generating outcomes.

Traditional Workflow:

```text
Question
↓
Answer
```

Agent Phantom Recovery Workflow:

```text
Goal
↓
Plan
↓
Investigate
↓
Use Tools
↓
Collect Evidence
↓
Reason
↓
Verify
↓
Execute
↓
Complete
```

The system is designed for long-horizon engineering tasks that may require dozens or hundreds of execution steps.

---

# Problem Statement

Modern software systems are becoming increasingly complex.

Developers spend significant time:

- Understanding unfamiliar repositories
- Tracing bugs
- Investigating failures
- Reading logs
- Running tests
- Performing verification
- Reviewing patches
- Understanding architecture

Current AI systems help with isolated coding tasks but struggle with:

```text
Long-Term Planning
Repository Scale
Verification
Multi-Step Execution
Tool Usage
State Persistence
```

Agent Phantom Recovery aims to bridge that gap.

---

# Core Principles

## Planning First

Never act before understanding.

```text
Understand
↓
Plan
↓
Execute
```

---

## Evidence Over Assumptions

Always prefer:

```text
Observed Evidence
```

over:

```text
Guesses
```

---

## Verification Before Acceptance

Every major conclusion should be challenged.

```text
Finding
↓
Verify
↓
Accept
```

---

## Long-Horizon Thinking

Optimize for:

```text
Task Completion
```

not:

```text
Fast Responses
```

---

## Tool-Driven Reality

Tools provide evidence.

Models provide reasoning.

Both are required.

---

# System Overview

```text
User
 ↓
Antigravity IDE
 ↓
API Gateway
 ↓
Orchestrator
 ↓
Planner
Reasoner
Verifier
 ↓
Tool System
 ↓
Memory System
 ↓
RAG Layer
 ↓
Repository Intelligence
```

---

# Core Capabilities

## Repository Intelligence

Capabilities:

```text
Repository Understanding
Architecture Analysis
Dependency Analysis
Call Graph Analysis
Semantic Search
```

---

## Autonomous Execution

Capabilities:

```text
Task Planning
Tool Usage
Observation
Replanning
Execution
```

---

## Engineering Intelligence

Capabilities:

```text
Root Cause Analysis
Patch Generation
Architecture Reasoning
Impact Analysis
```

---

## Verification

Capabilities:

```text
Patch Review
Regression Detection
Evidence Validation
Independent Verification
```

---

## Memory

Capabilities:

```text
Working Memory
Session Memory
Project Memory
Experience Memory
```

---

# Architecture Overview

## High-Level System

```text
                      User
                        │
                        ▼
                 Antigravity IDE
                        │
                        ▼
                   API Gateway
                        │
                        ▼
                  Orchestrator
                        │
        ┌───────────────┼───────────────┐
        ▼               ▼               ▼
     Planner        Reasoner        Verifier
       Kimi            Qwen         Nemotron
                        │
                        ▼
                   Tool Layer
                        │
      Browser  Terminal  Filesystem
               GitHub     Search
                        │
                        ▼
                   Memory Layer
                        │
                        ▼
                     RAG Layer
                        │
                        ▼
              Repository Intelligence
```

---

# LLM Architecture

The system uses a specialized three-model architecture.

---

## Planner

Model:

```text
Kimi K2.6 Free
```

Responsibilities:

```text
Goal Understanding
Task Decomposition
Planning
Replanning
Strategy
```

---

## Reasoner

Model:

```text
Qwen3 Coder 480B Free
```

Responsibilities:

```text
Code Analysis
Repository Understanding
Root Cause Analysis
Patch Generation
Architecture Understanding
```

---

## Verifier

Model:

```text
Nemotron 3 Ultra Free
```

Responsibilities:

```text
Review
Validation
Regression Detection
Risk Analysis
```

---

## Execution Pipeline

```text
Goal
↓
Planner
↓
Plan
↓
Tools
↓
Evidence
↓
Reasoner
↓
Patch
↓
Verifier
↓
Approve / Reject
↓
Execute
↓
Verify Again
↓
Complete
```

---

# Tool Architecture

The tool system enables interaction with reality.

---

## Browser Tool

Capabilities:

```text
Navigation
DOM Analysis
Screenshots
Automation
```

---

## Terminal Tool

Capabilities:

```text
Command Execution
Process Management
Streaming Output
```

---

## Filesystem Tool

Capabilities:

```text
Read Files
Write Files
Move Files
Search Files
```

---

## Git Tool

Capabilities:

```text
Status
Branches
Diffs
Commits
```

---

## GitHub Tool

Capabilities:

```text
Repository Sync
Pull Requests
Reviews
```

---

# Memory Architecture

Memory provides long-term persistence.

---

## Working Memory

Stores:

```text
Current Task Context
```

---

## Session Memory

Stores:

```text
Current Session Knowledge
```

---

## Project Memory

Stores:

```text
Repository Knowledge
Architecture Knowledge
```

---

## Experience Memory

Stores:

```text
Past Fixes
Past Failures
Strategies
Patterns
```

---

# RAG Architecture

Purpose:

```text
Provide Relevant Context
At The Right Time
```

---

## Pipeline

```text
Repository
Logs
Memory
Reports
Browser Data
Terminal Data
        │
        ▼
 Ingestion Pipeline
        │
        ▼
 Chunking
        │
        ▼
 Embeddings
        │
        ▼
 Vector Database
        │
        ▼
 Retrieval Engine
        │
        ▼
 Context Builder
        │
        ▼
 Planner
 Reasoner
 Verifier
```

---

## Vector Storage

MVP:

```text
Supabase pgvector
```

Production:

```text
Qdrant
```

---

# Antigravity IDE

Antigravity is the operational interface of Agent Phantom Recovery.

---

## Workspace Layout

```text
┌─────────────────────────────────────┐
│ Sidebar                             │
├─────────────────────────────────────┤
│ Chat Workspace                      │
│ Source Code Workspace               │
│ Browser Workspace                   │
│ Memory Workspace                    │
│ Timeline Workspace                  │
├─────────────────────────────────────┤
│ Terminal Workspace                  │
└─────────────────────────────────────┘
```

---

## Chat Workspace

Displays:

```text
Goals
Plans
Agent Messages
Status Updates
```

---

## Source Code Workspace

Displays:

```text
Repository Files
Diffs
Search Results
```

---

## Browser Workspace

Displays:

```text
Live Browser
Agent Actions
Observations
```

---

## Terminal Workspace

Displays:

```text
Commands
Processes
Logs
```

---

## Memory Workspace

Displays:

```text
Retrieved Context
Experience Memory
```

---

## Timeline Workspace

Displays:

```text
Events
Execution Progress
```

---

# Repository Structure

```text
agent-phantom-recovery/

├── apps/
│   ├── antigravity-web/
│   └── api-gateway/
│
├── services/
│   ├── orchestrator/
│   ├── planner/
│   ├── reasoner/
│   ├── verifier/
│   ├── memory/
│   ├── rag/
│   ├── repository-intelligence/
│   ├── tools/
│   └── execution-engine/
│
├── packages/
│   ├── shared-types/
│   ├── shared-utils/
│   ├── prompts/
│   └── sdk/
│
├── docs/
│
├── infrastructure/
│
├── tests/
│
└── scripts/
```

---

# Technology Stack

## Frontend

```text
Next.js
TypeScript
Tailwind CSS
shadcn/ui
Monaco Editor
React Query
Zustand
```

---

## Backend

```text
FastAPI
Python
Pydantic
SQLAlchemy
```

---

## Database

```text
Supabase PostgreSQL
pgvector
Redis
```

---

## Storage

```text
Supabase Storage
```

---

## AI

```text
OpenRouter
Kimi K2.6
Qwen3 Coder 480B
Nemotron 3 Ultra
```

---

# Development Roadmap

## Phase 0

Foundation

---

## Phase 1

Authentication

---

## Phase 2

Projects & Tasks

---

## Phase 3

LLM Layer

---

## Phase 4

Tool System

---

## Phase 5

Memory

---

## Phase 6

RAG

---

## Phase 7

Repository Intelligence

---

## Phase 8

Orchestrator

---

## Phase 9

Verification Layer

---

## Phase 10

Antigravity IDE

---

## Phase 11

Realtime Infrastructure

---

## Phase 12

Production Hardening

---

# Instructions For Antigravity

This section defines how Antigravity should build Agent Phantom Recovery.

---

## Build Philosophy

Never begin with UI.

Build from the core outward.

Correct sequence:

```text
Database
↓
Backend
↓
APIs
↓
LLMs
↓
Tools
↓
Memory
↓
RAG
↓
Repository Intelligence
↓
Orchestrator
↓
Verification
↓
UI
```

---

## Development Order

```text
1. Database Schema
2. Supabase Integration
3. Core Backend
4. API Layer
5. LLM Gateway
6. Planner
7. Reasoner
8. Verifier
9. Tool System
10. Memory System
11. RAG Layer
12. Repository Intelligence
13. Orchestrator
14. Verification Layer
15. Antigravity IDE
16. Realtime Infrastructure
17. Security
18. Optimization
19. Production Deployment
```

---

## Engineering Rules

Always:

```text
Read Architecture Documents First
Maintain Provider Independence
Use Abstraction Layers
Verify Before Accepting Results
Preserve Modularity
```

Never:

```text
Hardcode Model Vendors
Skip Verification
Couple Modules Tightly
Build Features Before Foundations
```

---

# Repository Reading Order

Before implementing anything:

```text
01-product-vision.md
↓
02-prd.md
↓
03-app-flow.md
↓
06-system-architecture.md
↓
07-trd.md
↓
09-backend-architecture.md
↓
10-backend-schema.md
↓
11-database-schema.md
↓
12-supabase-schema.md
↓
13-api-specification.md
↓
14-llms-integration.md
↓
15-rag-architecture.md
↓
16-module-implementation-plan.md
↓
17-full-implementation-plan.md
↓
18-antigravity-master-instructions.md
```

---

# Current Status

## Documentation

```text
Complete
```

---

## Architecture

```text
Complete
```

---

## Specifications

```text
Complete
```

---

## Backend

```text
Not Started
```

---

## Frontend

```text
Not Started
```

---

## Production Status

```text
Planning Phase
```

---

# Future Roadmap

## Version 1.0

```text
Core Autonomous Engineering Platform
```

---

## Version 1.5

```text
Advanced Browser Automation
Improved Verification
Enhanced Recovery
```

---

## Version 2.0

```text
Knowledge Graph
Advanced Memory Networks
Multi-Agent Expansion
```

---

# Master Directive

Agent Phantom Recovery exists to achieve validated engineering outcomes.

It must optimize for:

```text
Plan
↓
Reason
↓
Verify
↓
Execute
↓
Complete
```

rather than:

```text
Prompt
↓
Response
```

Every subsystem, service, model, tool, workflow, and future extension must remain aligned with this principle.

---

**Status:** Architecture Complete  
**Version:** 1.0  
**Project:** Agent Phantom Recovery  
**Interface:** Antigravity IDE
