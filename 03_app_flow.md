# Agent Phantom Recovery
## App Flow

### 1. Purpose of the App Flow
This document defines how a user moves through the product and how the system should move through a task from start to finish. The flow is designed for an autonomous engineering agent, not a conventional chatbot.

The experience should feel like a controlled execution pipeline:

**User Goal → System Analysis → Tool Use → Observation → Replanning → Verification → Delivery**

The flow must also be optimized for use inside **Antigravity**, meaning it should support structured task execution, clear progress visibility, and clean separation between planning, tool activity, and final output.

---

### 2. Core Interaction Principle
The product should not ask the user to manually coordinate every step.
Instead, the user gives a goal, and the system handles the work loop internally.

That loop is:

1. Understand the goal
2. Create a plan
3. Decide the first action
4. Use the appropriate tool
5. Observe the result
6. Update the plan
7. Repeat until the objective is complete
8. Present the final outcome

This is the central behavioral model of the application.

---

### 3. Primary App Flow Stages

## 3.1 Entry Stage
The user enters the system with one of three intents:

- investigate a bug
- inspect a repository
- find and fix a vulnerability in an authorized environment
- complete a technical task that requires multiple steps

At this stage, the system should gather the minimum required context:

- objective
- target repository or project
- constraints
- expected deliverable
- authorization boundary if security work is involved

If the input is vague, the system should refine it before execution.

---

## 3.2 Task Interpretation Stage
The system converts the user request into an internal task definition.

This includes:

- the main goal
- known constraints
- unknowns
- likely tools needed
- success criteria
- risks
- execution strategy

Example:

**User Goal:** Fix a failing test in a repository.

**Internal Interpretation:**
- inspect repository structure
- identify failing test output
- locate the source of failure
- reproduce locally
- patch the relevant code
- rerun tests
- verify no regressions
- produce final summary

This stage prevents the system from acting blindly.

---

## 3.3 Planning Stage
The planning layer decides the sequence of actions.

The plan should be short, explicit, and adaptive.

A good plan is not a long essay. It is a working map.

Typical plan structure:

- inspect repository
- read logs or failure output
- identify suspicious files
- run targeted tests
- edit code
- rerun tests
- verify output
- finalize deliverable

For security analysis, the plan may include:

- static scan
- call graph analysis
- inspect authentication or input-validation paths
- review candidate functions
- assess exploitability in a controlled context
- design a defensive fix
- verify the patch

The planning stage should remain visible to the user as progress, but the detailed reasoning can stay internal.

---

## 3.4 Tool Execution Stage
The system selects and uses the right tool for the job.

Supported tool classes:

- terminal
- code execution
- browser
- search
- file system
- code runner
- Git / GitHub

Tool use should be deliberate. The system should not use tools for the sake of activity.
Each tool call must answer a specific question or move the task forward.

Examples:

- terminal: run tests, install packages, inspect project files
- code execution: parse logs, analyze structured outputs, automate checks
- browser: inspect live app behavior or docs
- search: find references, library behavior, or repository context
- file system: read and modify files
- Git/GitHub: create branches, commit changes, prepare PRs

---

## 3.5 Observation Stage
After every tool call, the system must interpret the result.

This means:

- reading the output
- identifying whether the expected outcome occurred
- checking for new clues
- deciding what changed
- detecting whether the original hypothesis was wrong

Observation is not passive. It is a decision point.

Example:

- If tests pass, the system may move toward verification and cleanup.
- If tests fail, the system must inspect the failure and adapt.
- If evidence contradicts the hypothesis, the system must revise the plan.

This stage is what makes the system agentic rather than scripted.

---

## 3.6 Replanning Stage
The system updates its strategy based on the latest evidence.

Possible replanning outcomes:

- continue with the same approach
- narrow the scope
- inspect a different file
- run a different test
- add more evidence
- reject the previous hypothesis
- escalate to a deeper analysis pass

This step is essential for long-horizon work because the first path is often incomplete.

---

## 3.7 Verification Stage
Before finalizing work, the system must verify the result.

Verification may include:

- rerunning tests
- checking logs
- comparing behavior before and after the change
- reviewing changed files
- checking for regressions
- asking the verifier model to challenge the patch

The app should treat verification as mandatory, not optional.

---

## 3.8 Delivery Stage
The final stage should produce a clear output artifact.

Possible deliverables:

- fixed code
- commit
- pull request
- issue summary
- root-cause explanation
- remediation report
- security analysis summary

The deliverable should be explicit and structured so the user can understand what was done and why it is trustworthy.

---

### 4. User Flow by Scenario

## 4.1 Bug-Fix Flow
1. User submits bug-fix goal.
2. System analyzes context.
3. System inspects repository and logs.
4. System runs tests.
5. System identifies root cause.
6. System edits the relevant files.
7. System reruns tests.
8. System handles any new failures.
9. System verifies stability.
10. System outputs the fix and summary.

---

## 4.2 Security Investigation Flow
1. User submits an authorized security investigation task.
2. System scans code paths and metadata.
3. System identifies suspicious regions.
4. System reasons about possible weaknesses.
5. System evaluates whether issues are isolated or chainable.
6. System proposes a defensive fix.
7. System validates the fix in a controlled context.
8. System documents the reasoning and outcome.

The flow should emphasize remediation and verification.

---

## 4.3 Long-Horizon Engineering Flow
1. User provides a broad engineering objective.
2. System decomposes it into stages.
3. System executes each stage with tools.
4. System stores progress and intermediate findings.
5. System adapts as evidence changes.
6. System continues until the task is done.
7. System returns the completed result.

This is the most important flow for the product identity.

---

### 5. Antigravity-Optimized Flow Design
The app flow should be optimized for Antigravity so that the UI and execution model support deep agentic work.

#### 5.1 What Antigravity Optimization Means
It means the interface should make these things easy:

- clearly see the current task state
- understand the next action
- review evidence and tool outputs
- inspect intermediate reasoning summaries
- track progress across many steps
- switch between planning, execution, and verification without confusion

#### 5.2 Recommended Antigravity Layout Behavior
The app should present:

- a **goal panel** for the user’s objective
- a **plan panel** for current steps
- a **tool activity panel** for live execution
- an **evidence panel** for logs, files, and findings
- a **verification panel** for test results and reviewer feedback
- a **final output panel** for commits, reports, or PRs

This reduces cognitive overload and makes long tasks readable.

#### 5.3 Why This Matters
Agentic systems become hard to trust when the UI hides state.
Antigravity should therefore expose structure, not just conversation.

That makes the app feel like a mission control surface for technical work.

---

### 6. State Model in the App Flow
The system should move through explicit states:

- Idle
- Intake
- Planning
- Tool Execution
- Observation
- Replanning
- Verification
- Delivery
- Completed
- Failed / Needs User Input

These states help the user understand progress and help the agent manage long tasks cleanly.

---

### 7. Feedback and Control Points
The user should be able to intervene at key points:

- approve or adjust the goal
- review the plan
- inspect evidence
- stop execution
- request a different strategy
- accept or reject a final deliverable

This keeps the system controlled while still being autonomous.

---

### 8. Failure Flow
If the system cannot complete the task, it should not stall silently.
It should:

- report what was attempted
- show what evidence was found
- explain why the current strategy failed
- propose the next best action
- ask for missing input if needed

Failure handling should still produce useful progress.

---

### 9. Design Principle for the Flow
The flow should minimize empty chat and maximize actionable work.

A good flow does not waste time asking the user to re-explain everything.
It remembers context, uses tools, and keeps moving.

---

### 10. Final Flow Summary
The app flow for Agent Phantom Recovery is:

**User Goal → Context Capture → Task Interpretation → Planning → Tool Use → Observation → Replanning → Verification → Delivery**

For Antigravity, the flow must be visibly structured, state-driven, and optimized for long-horizon execution rather than short back-and-forth conversation.

