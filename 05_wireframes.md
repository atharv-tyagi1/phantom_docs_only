# Agent Phantom Recovery
## Wireframes

### 1. Wireframe Purpose
This document defines the structural layout of the application in text form so the UI can be designed and implemented consistently.

The wireframes are organized around the product’s actual workflow:
- left sidebar for navigation and memory
- main workspace for code and browser
- bottom terminal for tool execution
- side chat/agent console for coordination

The goal is to preserve clarity, execution speed, and long-horizon task visibility.

---

### 2. Primary Desktop Wireframe

```text
+----------------------------------------------------------------------------------+
| Top Bar: Project Name | Current Task | Active State | Search | Profile / Status   |
+----------------------+-----------------------------------------------------------+
| Left Sidebar         | Main Workspace                                            |
|                      |                                                           |
|  - Old Chats         |  +----------------------+  +-------------------------+  |
|  - Skills            |  | Source Code Panel     |  | Browser Panel           |  |
|  - Tools             |  |                      |  |                         |  |
|  - Memory            |  |                      |  |                         |  |
|  - Sessions          |  |                      |  |                         |  |
|                      |  +----------------------+  +-------------------------+  |
|  - Login             |                                                           |
|  - Settings          |  +-----------------------------------------------------+  |
|                      |  | Terminal Panel                                      |  |
|                      |  |                                                     |  |
|                      |  +-----------------------------------------------------+  |
|                      |  +-----------------------------------------------------+  |
|                      |  | Chat / Agent Console                                |  |
|                      |  |                                                     |  |
|                      |  +-----------------------------------------------------+  |
+----------------------+-----------------------------------------------------------+
```

This is the core workspace layout. It is designed to keep the browser, code, terminal, and chat visible together.

---

### 3. Layout Intent

#### Left Sidebar
Used for navigation and state management:
- old chats
- saved sessions
- skills
- tools
- memory
- login
- settings

#### Source Code Panel
Used for reading and editing repository code.

#### Browser Panel
Used for rendering the full website or application inside the workspace.

#### Terminal Panel
Used for commands, logs, test execution, and tool output.

#### Chat / Agent Console
Used for user interaction, agent summaries, planning updates, and task checkpoints.

---

### 4. Sidebar Wireframe

```text
+------------------------------+
| Agent Phantom Recovery       |
+------------------------------+
| Search / Filter              |
+------------------------------+
| Recent Chats                 |
|  - Session 1                 |
|  - Session 2                 |
|  - Session 3                 |
+------------------------------+
| Skills                       |
|  - Debugging                 |
|  - Browser Inspection        |
|  - Code Recovery             |
|  - Security Review           |
+------------------------------+
| Tools                        |
|  - Terminal                  |
|  - Browser                   |
|  - File System               |
|  - Code Runner               |
|  - Search                    |
|  - Git / GitHub              |
+------------------------------+
| Memory                       |
|  - Active Task               |
|  - Project Memory            |
|  - Prior Findings            |
+------------------------------+
| Login                        |
| Settings                     |
+------------------------------+
```

The sidebar is a control surface, not just a navigation menu.

---

### 5. Main Workspace Wireframe

```text
+----------------------------------------------------------------------------------+
| Source Code Panel                          | Browser Panel                        |
|--------------------------------------------|--------------------------------------|
| File Tree                                  | URL / Page Title                     |
|                                            |                                      |
| Code Editor / Viewer                      | Live Website Render                   |
|                                            |                                      |
| Diff / Highlighted Changes                 | Navigation / Inspect Controls         |
|                                            |                                      |
+----------------------------------------------------------------------------------+
| Terminal Panel                                                                    |
|----------------------------------------------------------------------------------|
| Command Output / Logs / Test Results                                              |
+----------------------------------------------------------------------------------+
| Chat / Agent Console                                                              |
|----------------------------------------------------------------------------------|
| User Input | Agent Plan | Progress Updates | Verification Notes                    |
+----------------------------------------------------------------------------------+
```

This arrangement keeps the most important execution surfaces visible at the same time.

---

### 6. Browser Panel Wireframe

```text
+----------------------------------------------------------+
| Browser Header                                           |
| URL Bar | Back | Forward | Reload | Inspect | Snapshot   |
+----------------------------------------------------------+
|                                                          |
|                  Live Website / App View                 |
|                                                          |
|                                                          |
+----------------------------------------------------------+
| Status: page loaded | element selected | network state   |
+----------------------------------------------------------+
```

The browser panel should be able to show the real website as the agent works on it.

---

### 7. Source Code Panel Wireframe

```text
+----------------------------------------------------------+
| Code Header                                              |
| File Name | Branch | Save State | Diff Mode | Search     |
+----------------------------------------------------------+
| File Tree                                                |
| - src/                                                   |
| - tests/                                                 |
| - docs/                                                  |
+----------------------------------------------------------+
| Code Editor / Read View                                  |
|                                                          |
|  - syntax highlighting                                   |
|  - selected function focus                                |
|  - line markers                                           |
|  - changed lines                                          |
+----------------------------------------------------------+
| Context Bar: file path | cursor position | modified state |
+----------------------------------------------------------+
```

The code panel should support inspection and modification without losing context.

---

### 8. Terminal Wireframe

```text
+----------------------------------------------------------+
| Terminal Header                                          |
| Session | Clear | Split | Copy Logs | Re-run Last Cmd    |
+----------------------------------------------------------+
|                                                          |
|  $ command output                                        |
|  build logs                                              |
|  test failures                                           |
|  warnings                                                |
|  status messages                                         |
|                                                          |
+----------------------------------------------------------+
| Input Line                                               |
| >                                                        |
+----------------------------------------------------------+
```

The terminal should be persistent, readable, and central to tool execution.

---

### 9. Chat / Agent Console Wireframe

```text
+----------------------------------------------------------+
| Agent Console                                            |
| Mode: Planning / Executing / Verifying                  |
+----------------------------------------------------------+
| Agent Summary                                            |
| - current goal                                           |
| - next action                                            |
| - reason for action                                      |
+----------------------------------------------------------+
| Conversation                                            |
| User: ...                                               |
| Agent: ...                                              |
| System: ...                                             |
+----------------------------------------------------------+
| Input Box                                                |
| Ask the agent...                                         |
+----------------------------------------------------------+
```

This area should communicate the reasoning state without turning the entire interface into a chat screen.

---

### 10. Task Timeline Wireframe

```text
+----------------------------------------------------------+
| Task Timeline                                            |
+----------------------------------------------------------+
| 1. Goal received                                         |
| 2. Plan created                                          |
| 3. Tool selected                                         |
| 4. Result observed                                       |
| 5. Replanned                                             |
| 6. Verification started                                  |
| 7. Fix confirmed                                         |
+----------------------------------------------------------+
```

This is useful for long tasks because it gives the user a visible history of the agent’s work.

---

### 11. Memory Panel Wireframe

```text
+----------------------------------------------------------+
| Memory                                                   |
+----------------------------------------------------------+
| Active Task                                              |
| Project Context                                          |
| Prior Decisions                                          |
| Previous Failures                                        |
| Useful Findings                                          |
+----------------------------------------------------------+
```

Memory should be visible as a structured reference, not as an overwhelming dump.

---

### 12. Tool Panel Wireframe

```text
+----------------------------------------------------------+
| Tools                                                    |
+----------------------------------------------------------+
| Terminal                                                |
| Browser                                                 |
| Search                                                  |
| File System                                             |
| Code Runner                                             |
| Git / GitHub                                            |
+----------------------------------------------------------+
| Active Tool: Terminal                                   |
| Last Action: Ran test suite                              |
+----------------------------------------------------------+
```

The tool panel helps users understand what the system can do and what it is doing now.

---

### 13. Empty State Wireframe

```text
+----------------------------------------------------------+
| No Active Task                                           |
+----------------------------------------------------------+
| Start by describing a bug, repository, or goal.          |
| The agent will plan, use tools, verify, and deliver.     |
+----------------------------------------------------------+
```

The empty state should encourage action without feeling like a dead end.

---

### 14. Busy State Wireframe

```text
+----------------------------------------------------------+
| Task Running                                             |
+----------------------------------------------------------+
| Current Step: Running tests                              |
| Current Tool: Terminal                                   |
| Last Observation: 2 tests failed                         |
| Next Step: Inspect failing module                        |
+----------------------------------------------------------+
```

This keeps the user informed during long execution cycles.

---

### 15. Failure State Wireframe

```text
+----------------------------------------------------------+
| Task Blocked                                             |
+----------------------------------------------------------+
| What happened:                                           |
| - command failed                                         |
| - missing dependency                                     |
| - insufficient context                                   |
|                                                          |
| Recommended next step:                                   |
| - inspect logs                                           |
| - change strategy                                        |
| - ask user for input                                     |
+----------------------------------------------------------+
```

Failure states should still be useful and actionable.

---

### 16. Verification State Wireframe

```text
+----------------------------------------------------------+
| Verification                                             |
+----------------------------------------------------------+
| Checks Passed:                                            |
| - unit tests                                             |
| - regression scan                                        |
| - diff review                                            |
| - verifier model approval                                |
+----------------------------------------------------------+
| Result: Ready to deliver                                 |
+----------------------------------------------------------+
```

Verification should be visually separated from ordinary execution.

---

### 17. Liquid Glass Presentation Notes
The wireframes should be implemented with a liquid glass visual system inspired by Apple:

- translucent panels
- soft blur layers
- rounded corners
- subtle borders
- layered depth
- polished reflections
- restrained shadows

The glass effect should never reduce readability or usability.

---

### 18. Wireframe Priorities
The highest-priority surfaces are:

1. source code
2. browser
3. terminal
4. chat / agent console
5. sidebar memory and tool access

This ordering reflects how the agent performs real work.

---

### 19. Final Wireframe Summary
The wireframe system for Agent Phantom Recovery should support a desktop-first, multi-pane execution workspace with:

- left sidebar for chats, skills, tools, memory, login, settings
- source code view on one side
- browser view for live websites
- terminal docked at the bottom
- chat and agent console for coordination
- timeline and verification surfaces for long-horizon task tracking
- liquid glass visual styling

The result should be a clear, professional, mission-control-style workspace built for autonomous engineering work.

