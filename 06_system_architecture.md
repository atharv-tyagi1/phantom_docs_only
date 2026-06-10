# Agent Phantom Recovery
## System Architecture

### 1. Architecture Purpose
This document defines the high-level system architecture for Agent Phantom Recovery, a long-horizon autonomous engineering and security recovery platform.

The architecture is designed to support:
- multi-step technical reasoning
- iterative tool use
- repository inspection
- bug fixing and verification
- authorized security analysis
- long-context memory
- multi-LLM orchestration
- final deliverables such as patches, reports, or pull requests

The core principle is simple: **reduce the search space deterministically, then use LLMs to reason over high-signal evidence**.

---

### 2. Architectural Identity
Agent Phantom Recovery is not a chatbot architecture.
It is an **agentic execution architecture**.

That means the system is organized around:
- goals
- plans
- tools
- observations
- replanning
- verification
- delivery

The system should behave like a technical operator that can persist across long work sessions.

---

### 3. High-Level System View

```text
User Goal
   ↓
Task Intake Layer
   ↓
Planner / Orchestrator LLM
   ↓
Evidence & Repository Analysis Layer
   ↓
Reasoner / Auditor LLM
   ↓
Verifier / Reviewer LLM
   ↓
Tool Execution Layer
   ↓
Memory Layer
   ↓
Delivery Layer
```

This is a closed-loop system, not a one-pass response generator.

---

### 4. Core Architectural Principles

#### 4.1 Tool-First Evidence Gathering
The system should use deterministic tools before relying on model judgment.
Examples:
- repo scanning
- AST parsing
- dependency analysis
- test runs
- logs
- code search
- browser inspection

#### 4.2 Role Separation
Different models should handle different responsibilities.
This reduces correlated failure and improves reliability.

#### 4.3 Verification as a Gate
No important action should be accepted without verification.
The verifier must be able to reject weak findings or unsafe patches.

#### 4.4 Long-Horizon State
The system must preserve working memory, task state, and useful evidence across many steps.

#### 4.5 Controlled Execution
The execution controller must manage timeouts, retries, permissions, and sandboxing.

---

### 5. Major Subsystems

## 5.1 User Interface Layer
This layer presents the workspace to the user.
It includes:
- chat / agent console
- source code panel
- browser panel
- terminal panel
- sidebar for chats, skills, tools, login, and settings
- task timeline
- memory references

The UI is designed to expose state clearly rather than hide it behind abstract chat.

---

## 5.2 Task Intake Layer
This layer receives the user’s goal and converts it into a structured internal task.

Responsibilities:
- capture the objective
- detect task type
- identify constraints
- determine whether authorization is required
- select the likely workflow
- define success criteria
- initialize task state

Example task types:
- bug fix
- repository inspection
- security review
- browser debugging
- PR preparation
- multi-step engineering task

---

## 5.3 Planner / Orchestrator Layer
This is LLM 1 in the three-model design.

Responsibilities:
- refine the goal
- decompose the task
- choose tools
- decide the next step
- manage subtask ordering
- preserve working context
- summarize progress

The planner should act like a project manager rather than a deep code analyst.
It should be fast, structured, and reliable at task decomposition.

---

## 5.4 Evidence & Repository Analysis Layer
This layer compresses a large codebase into a smaller, high-signal evidence set.

Responsibilities:
- ingest repository structure
- parse files
- build dependency and call graphs
- run static analysis tools
- inspect tests and logs
- locate suspicious regions
- rank candidate files or functions

Recommended analysis outputs:
- file map
- call graph
- suspicious function list
- failing test summary
- relevant log excerpts
- dependency relationships

This layer is critical because it prevents the LLM from having to reason over the whole repository blindly.

---

## 5.5 Reasoner / Auditor Layer
This is LLM 2 in the three-model design.

Responsibilities:
- inspect suspicious code chunks deeply
- explain root cause
- reason about side effects
- design fixes
- evaluate exploitability in authorized contexts
- propose safe implementations
- assess compatibility and performance risks

This should be the strongest technical model in the stack.
It is where deep code intelligence is concentrated.

---

## 5.6 Verifier / Reviewer Layer
This is LLM 3 in the three-model design.

Responsibilities:
- challenge assumptions
- look for false positives
- check whether the reasoning is evidence-backed
- inspect the proposed fix for regressions
- reject weak or unsafe patches
- confirm that the final result is supported by tests or logs

The verifier acts as a skeptical gatekeeper.
Its job is not to agree.
Its job is to prevent confident errors.

---

## 5.7 Tool Execution Layer
This layer performs real actions in the environment.

Supported tools:
- terminal
- code execution
- browser
- search
- file system
- code runner
- Git / GitHub

Responsibilities:
- run commands
- inspect repository state
- execute tests
- edit files
- capture outputs
- navigate websites
- generate diffs and commits

The tool layer should be isolated from the reasoning layers so execution remains controlled.

---

## 5.8 Memory Layer
Memory is essential for long-horizon operation.

The memory layer should store:
- current task state
- project-specific facts
- prior decisions
- failed attempts
- successful strategies
- important evidence
- reusable patterns

Recommended memory categories:

#### Working Memory
Short-term state for the active task.

#### Project Memory
Persistent facts about the repository or project.

#### Experience Memory
Strategy-outcome pairs and lessons learned from previous attempts.

#### Session Memory
Recent actions and observations for continuity.

This prevents the system from repeatedly rediscovering the same information.

---

## 5.9 Delivery Layer
This layer transforms a successful investigation into an output artifact.

Possible outputs:
- code patch
- commit
- pull request
- remediation report
- audit summary
- bug-fix report
- verification log

The delivery layer should make the final result easy for the user to review and trust.

---

### 6. Closed-Loop Execution Model
The system should run as a continuous loop.

```text
Goal
  ↓
Plan
  ↓
Use Tool
  ↓
Observe Result
  ↓
Update Plan
  ↓
Use Another Tool
  ↓
Repeat
  ↓
Verify
  ↓
Deliver
```

This is the operational core of Agent Phantom Recovery.

A one-shot model is not sufficient for the intended behavior.

---

### 7. Security Workflow Sub-Architecture
Because the project includes authorized vulnerability discovery and remediation, the architecture should support a security workflow without making the whole system security-only.

Security workflow stages:
1. identify suspicious region
2. confirm with static or dynamic evidence
3. reason about exploitability in a controlled context
4. determine whether issues can chain
5. design a defensive fix
6. verify the fix
7. document findings

The system should remain focused on investigation and remediation, not spectacle.

---

### 8. Bug-Fix Workflow Sub-Architecture
Bug fixing should be a first-class workflow.

Bug-fix stages:
1. inspect repo and logs
2. reproduce failure
3. isolate root cause
4. patch code
5. rerun tests
6. investigate follow-up failures
7. verify stability
8. produce final solution

This workflow is just as important as security analysis because it proves the system can actually repair software.

---

### 9. Data Flow
A typical data flow looks like this:

```text
User Request
   ↓
Task Object
   ↓
Plan
   ↓
Tool Calls + Repository Evidence
   ↓
Analysis Output
   ↓
Proposed Fix / Decision
   ↓
Verifier Review
   ↓
Patch / Report / PR
   ↓
Memory Update
```

Every major step should create a traceable artifact.

---

### 10. State Management
The system should maintain explicit task states.

Suggested states:
- Idle
- Intake
- Planning
- Evidence Gathering
- Deep Analysis
- Patch Design
- Tool Execution
- Verification
- Delivery
- Blocked
- Completed

This makes the agent’s progress understandable both to the user and to the system itself.

---

### 11. Execution Controller
The execution controller is a key infrastructure component.

Responsibilities:
- schedule actions
- enforce permissions
- handle retries
- apply timeouts
- isolate unsafe operations
- prevent runaway loops
- manage tool outputs
- record traces

This controller is what turns model intent into safe and reliable action.

---

### 12. Repository Analysis Pipeline
The architecture should use a deterministic narrowing pipeline.

Suggested pipeline:
1. repo ingestion
2. file indexing
3. AST parsing
4. dependency graph generation
5. call graph generation
6. static analysis
7. candidate extraction
8. model reasoning on suspicious regions only

This approach is much more scalable than sending the entire repository into the model.

---

### 13. Verification Pipeline
Before a result is accepted, it should pass through verification.

Verification may include:
- unit tests
- integration tests
- lint or build checks
- log review
- patch diff review
- verifier model review
- regression inspection

The system should never treat a patch as complete until evidence supports it.

---

### 14. Antigravity Integration Considerations
Since the UI and workflow must be optimized for Antigravity, the architecture should support:

- multi-pane execution surfaces
- visible tool activity
- live browser rendering
- terminal output docking
- code and browser coexistence
- clear task progression visualization
- session continuity across long work periods

Antigravity should feel like the natural operating environment for the agent.

---

### 15. Failure Handling
The architecture must gracefully handle failures.

Examples:
- command failure
- missing file
- failing tests
- contradictory evidence
- blocked permissions
- incomplete task context
- invalid assumption

When failure occurs, the system should:
- record what happened
- explain the failure
- update the plan
- choose the next best action
- ask the user only when necessary

Failure should still produce useful progress.

---

### 16. Scalability Considerations
The architecture should scale in three dimensions:

#### 16.1 Task Complexity
Support longer tasks with more steps and more tool usage.

#### 16.2 Repository Size
Support larger repos by narrowing analysis through indexing and candidate extraction.

#### 16.3 Model Specialization
Support different reasoning roles with different model strengths and costs.

A single-model architecture can work for small tasks, but it is less reliable for long-horizon technical work.

---

### 17. Suggested Implementation Decomposition
A practical implementation should be divided into modules such as:
- orchestrator
- planner
- evidence collector
- repository indexer
- tool executor
- verifier
- memory manager
- reporting engine
- UI workspace controller

This modularity improves maintainability and testability.

---

### 18. Final Architecture Summary
Agent Phantom Recovery should be implemented as a modular, closed-loop, agentic engineering system with:
- structured task intake
- planner-driven execution
- deterministic evidence collection
- deep reasoning on high-signal code regions
- strict verification
- persistent memory
- controlled tool execution
- final artifact delivery

The architecture should prioritize correctness, traceability, and long-horizon completion over shallow conversational response.

