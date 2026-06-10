# Agent Phantom Recovery
## Product Vision

### 1. Product Summary
Agent Phantom Recovery is a long-horizon autonomous engineering system built to investigate codebases, reason over complex technical problems, use tools repeatedly, verify findings, implement fixes, and deliver completed engineering outcomes such as patches, test results, and pull requests.

It is not a chatbot. It is a work-performing agent.

The system is designed to operate across extended sessions, maintain task continuity, and improve its decisions through observation, verification, and experience.

---

### 2. Vision Statement
Build an autonomous engineering and security recovery platform that can understand code deeply, plan multi-step actions, use tools effectively, verify its own work, and complete real technical tasks with high precision.

---

### 3. Core Mission
The mission of Agent Phantom Recovery is to help users:

- investigate codebases
- detect bugs and vulnerabilities in authorized environments
- explain root causes clearly
- design safe, compatible fixes
- implement changes
- run tests and debug failures
- continue working until the objective is complete
- produce a final engineering artifact such as a PR, report, or patch

---

### 4. Primary Product Identity
The product should be recognized as:

- a long-horizon agent, not a chat interface
- a multi-tool engineering system, not a single-model assistant
- a reasoning-and-verification workflow, not an instant-answer engine
- a security-forward platform that also excels at bug fixing and repository recovery

Security is important because it is a strong benchmark for deep reasoning, but the underlying value is broader engineering capability.

---

### 5. Target Users
The product is intended for:

- developers debugging complex repositories
- security researchers working in authorized environments
- engineering teams reviewing code quality and reliability
- advanced users who need multi-step technical assistance
- builders who want an autonomous system that can actually complete technical work

---

### 6. Core User Promise
When a user gives the system a technical goal, the system should not stop at explanation.
It should:

1. understand the goal
2. create a plan
3. use tools
4. observe results
5. update strategy
6. continue iterating
7. verify the outcome
8. present a completed result

That is the central promise of the product.

---

### 7. Differentiation
Most assistants are optimized for conversation.
Agent Phantom Recovery is optimized for execution.

Its key differentiators are:

- long-horizon task persistence
- tool-driven investigation
- multi-stage reasoning
- self-verification and critique
- repository-aware debugging
- support for security analysis and remediation
- patch-oriented output instead of only descriptive output

---

### 8. Core Capability Areas
The system should be strong in these areas:

#### A. Autonomous Task Execution
The agent should handle loops such as:
Goal → Plan → Tool Use → Observe Result → Update Plan → Repeat → Complete.

#### B. Debugging and Recovery
The agent should inspect repositories, read logs, run tests, modify files, rerun tests, identify secondary failures, and converge on a stable fix.

#### C. Vulnerability Discovery and Fixing
The agent should reason about suspicious code paths, identify possible weaknesses, understand whether issues can chain, and then design and validate safe fixes.

#### D. Deep Code Understanding
The agent should understand architecture, dependencies, side effects, compatibility constraints, and performance implications.

#### E. Verification Discipline
The agent should not trust its first answer. It should verify assumptions, challenge its own reasoning, and confirm outcomes through tests or evidence.

#### F. Memory and Continuity
The system should preserve project context, prior decisions, failed attempts, and useful findings across long sessions.

---

### 9. Product Principles
Agent Phantom Recovery should be built around the following principles:

- Use deterministic tools before asking the model to reason.
- Reduce the search space before analysis.
- Use multiple models for different roles.
- Treat verification as a first-class step.
- Prefer correctness over speed.
- Preserve continuity across long tasks.
- Optimize for real engineering output, not just text.
- Keep the system focused on investigation, remediation, and validation.

---

### 10. Reasoning Philosophy
The product should follow a deliberate workflow:

Question → Analysis → Verification → Answer

Or in execution form:

Goal → Plan → Tool → Observe → Re-plan → Tool → Verify → Deliver

This ensures the system behaves like an engineer rather than a reactive chatbot.

---

### 11. Model Strategy
The product should use a three-model structure:

- Planner / Orchestrator: decomposes goals and manages task flow
- Reasoner / Auditor: performs deep technical analysis and fix design
- Verifier / Reviewer: challenges reasoning, checks evidence, and rejects weak patches

This separation reduces correlated failure and improves reliability.

---

### 12. Success Definition
The product succeeds when it can:

- investigate a repository without losing context
- find meaningful technical issues
- explain why they happen
- implement safe fixes
- validate the fixes with tests
- recover from failed attempts
- produce a useful final deliverable

The success criterion is not whether it sounds intelligent.
The success criterion is whether it completes the work.

---

### 13. Non-Goals
At the product vision stage, the system is not primarily defined as:

- a general chat assistant
- a passive code summarizer
- a one-shot vulnerability scanner
- a system that answers immediately without investigation

It must behave as an active engineering agent.

---

### 14. V1 Product Scope
The first version should focus on:

- repo ingestion
- tool orchestration
- test execution
- file editing
- patch generation
- verification loop
- task memory
- clean final reporting

Security analysis can be included in V1 as a strong use case, but the product should remain broadly useful for debugging and code recovery.

---

### 15. One-Sentence Vision
Agent Phantom Recovery is an autonomous engineering and security recovery system that investigates, fixes, verifies, and completes complex technical work through long-horizon reasoning and tool use.

