# Agent Phantom Recovery
## UI/UX Design

### 1. Design Philosophy
The UI must reflect the product’s true identity: a long-horizon autonomous engineering and security recovery system.

It should feel like a **mission control workspace** rather than a chat application.

The interface should communicate three things at all times:

- what the agent is trying to do
- what tool it is using now
- what evidence or result it just observed

The design goal is not visual decoration alone. It is operational clarity.

Because the product must support extended technical work, the interface should reduce context switching, expose execution state, and make it easy to inspect evidence without losing the main task.

---

### 2. UX Principles
The experience should follow these principles:

#### 2.1 Clarity Over Novelty
Every surface should answer a question quickly:
- What is happening now?
- What has the agent done?
- What should happen next?

#### 2.2 Visible State
The user should always know whether the system is:
- planning
- browsing
- running terminal commands
- editing code
- verifying
- waiting for input

#### 2.3 Parallel Visibility
The product should let the user see multiple important surfaces at once:
- browser
- code
- terminal
- chat / agent console
- task memory or history

#### 2.4 Controlled Autonomy
The agent should work independently, but the user should still be able to inspect, steer, pause, or approve actions.

#### 2.5 Evidence First
The interface should foreground outputs, logs, code diffs, and browser state rather than only conversational text.

#### 2.6 Long-Horizon Readability
The UI must remain usable over multi-step, multi-hour sessions. That means stable layout, clear sections, and good state retention.

---

### 3. Information Architecture
The application should be organized around five primary concepts:

1. **Workspace** — the active task environment
2. **Browser Surface** — live website or web app inspection
3. **Code Surface** — repository source code and diffs
4. **Terminal Surface** — commands, tools, build output, and execution logs
5. **Agent Console** — chat, planning, reasoning summaries, and task coordination

Supporting surfaces:
- task history
- skill library
- tool library
- memory records
- settings and login controls

This architecture ensures the interface is task-driven rather than chat-driven.

---

### 4. Workspace Layout
The default workspace should be a multi-pane layout optimized for execution.

#### Recommended structure
- **Left sidebar**: chats, memory, skills, tools, login, settings
- **Main center-left panel**: source code
- **Main center-right panel**: browser or task preview
- **Bottom panel**: terminal
- **Right panel or docked region**: chat and agent console

This layout reflects how the product actually works:
- code is inspected and edited
- websites are observed live
- terminal runs commands and tests
- chat guides or explains the process

The layout should allow the user to work without constantly switching tabs.

---

### 5. Browser Workspace
One of your most important requirements is to run the browser inside Agent Phantom Recovery so the user can see the full website directly.

#### Browser workspace goals
- render live websites inside the product
- support inspection of UI behavior
- allow navigation, clicking, and observation
- show the actual running target rather than only a textual description

#### Browser workspace behavior
The browser panel should support:
- page rendering
- URL visibility
- reload control
- navigation history
- element inspection mode
- screenshot or visual snapshot capture
- side-by-side comparison with code or logs

#### Why this matters
A browser embedded in the workspace reduces the gap between code and reality.
The agent can inspect the effect of code changes immediately, which is essential for debugging, QA, and UI recovery tasks.

---

### 6. Source Code Workspace
You want one side of the workspace to show the source code.

That is the correct design choice.

#### Source code panel requirements
- file tree navigation
- syntax-highlighted code editor or viewer
- diff view for modifications
- search inside repo
- open multiple files
- highlight changed lines
- show context around selected functions

#### Source code panel behavior
The code view should support both:
- **read mode** for analysis
- **edit mode** for patching

For long tasks, the panel should keep the current file and cursor state so the agent and user do not lose their place.

#### Why this matters
Most technical work depends on constant movement between code, output, and browser behavior. The code panel must be instantly readable and easy to navigate.

---

### 7. Terminal Workspace
You specifically want the terminal at the bottom because it will be the main tool execution surface.

That is a strong UX decision.

#### Terminal panel requirements
- command execution
- build output
- test results
- logs and errors
- shell history
- clear success/failure feedback

#### Terminal placement rationale
Placing the terminal at the bottom is effective because:
- it mirrors common developer workflows
- it keeps command output visible without dominating the screen
- it allows the code and browser panels to remain primary

#### Terminal behavior
The terminal should support:
- multi-command sessions
- persistent state where possible
- collapsible output sections
- command replay
- copyable logs
- tool invocation trace markers

This panel is especially important because the system’s power depends on tool use, not only reasoning.

---

### 8. Chat & Agent Console
You want a dedicated area where the user can chat with the agent.

This is important, but the chat should not dominate the interface.

#### Chat console purpose
- issue goals
- ask clarifying questions
- review decisions
- inspect the agent’s reasoning summary
- approve or reject certain actions
- receive final updates

#### Chat console behavior
The chat should feel like an operational command lane, not a social messenger.

It should support:
- structured responses
- task checkpoints
- progress summaries
- warnings or blockers
- final conclusions

#### Good design pattern
The chat should be able to show:
- what the system is doing now
- what it found
- what it plans to do next
- what evidence supports the decision

This keeps the interface aligned with the agentic workflow.

---

### 9. Sidebar Architecture
You want a left sidebar that contains:
- old chats
- skills
- tools
- login button
- settings button at the bottom

That is a strong and practical structure.

#### Sidebar content sections
1. **Chat history**
   - previous tasks
   - recent investigations
   - saved sessions

2. **Skills**
   - code analysis
   - debugging
   - browser inspection
   - repository recovery
   - security review

3. **Tools**
   - terminal
   - browser
   - code runner
   - file system
   - search
   - Git/GitHub

4. **Bottom controls**
   - login / account
   - settings

#### Why this is effective
The sidebar becomes the control center for memory and capability discovery.
Users can quickly resume old work, inspect what the system can do, and manage their account without leaving the workspace.

---

### 10. Memory Interface
The system should expose memory in a useful, non-intrusive way.

#### Memory UI goals
- show active task context
- preserve old task sessions
- track important decisions
- store reusable insights
- make project memory visible when needed

#### Suggested memory surfaces
- active session memory
- project memory
- prior investigation summaries
- strategy outcomes

#### Design principle
Memory should be accessible without cluttering the main execution view.
It should exist as a structured reference layer, not as noisy text dumps.

---

### 11. Tool Interface
Because tool use is central to the product, the UI should clearly show tool availability and current usage.

#### Tool UI should include
- tool list
- active tool indicator
- recent actions
- permissions or access state
- success/failure feedback

#### Tool interaction model
The user should be able to see:
- which tool the agent chose
- why it chose it
- what result came back
- what the next step is

This creates transparency without requiring the user to micromanage every action.

---

### 12. Execution Timeline
The app should show a visible timeline of work.

Example timeline:
- Goal received
- Plan created
- Browser opened
- Terminal command executed
- Code inspected
- Test failed
- Patch applied
- Tests rerun
- Verification passed
- Task completed

This timeline is highly useful for long sessions because it gives the user a quick audit trail.

---

### 13. Liquid Glass Design System
You want the theme to be **liquid glass inspired by Apple**.

That is a strong visual direction if executed carefully.

#### Liquid glass characteristics
- translucent surfaces
- soft blur layers
- subtle highlights
- depth through layered opacity
- rounded forms
- elegant contrast
- minimal but premium feel

#### Important design warning
Liquid glass should not reduce readability.
If too much blur or transparency is used, the interface can become beautiful but difficult to use. For an execution-heavy product, clarity must win over decoration.

#### Recommended visual treatment
- translucent panels with controlled blur
- soft borders
- layered cards
- subtle reflections
- restrained shadows
- smooth transitions
- high legibility typography

#### Overall aesthetic goal
The interface should feel premium, futuristic, and calm while still being operationally serious.

---

### 14. Antigravity Optimization
The UI must be optimized for Antigravity as an execution environment.

That means the layout should help with:

- long task tracking
- multi-tool coordination
- readable state transitions
- verification and patch review
- browser/code/terminal co-visibility

#### Antigravity-optimized behaviors
- keep the main workspace persistent
- avoid unnecessary modal interruptions
- show task stages clearly
- expose tool results in place
- preserve session context across changes

The key idea is to make the agent’s work legible while it is happening.

---

### 15. Responsive Behavior
The design should adapt across screen sizes while preserving core function.

#### Desktop
Desktop should be the primary target because this product needs multiple visible panels.

#### Tablet
Panels may stack or compress, but browser/code/terminal visibility should still be preserved where possible.

#### Mobile
Mobile should support review, chat, history, and lightweight task monitoring, but full multi-pane execution will be naturally limited.

The product is fundamentally a high-information workspace, so desktop-first design is appropriate.

---

### 16. Accessibility
Even with a premium visual style, accessibility must remain strong.

#### Requirements
- readable contrast
- scalable text
- keyboard navigation
- clear focus states
- visible active panel indication
- no reliance on color alone for status

A liquid-glass interface can easily become inaccessible if contrast is ignored. That should be avoided.

---

### 17. Interaction Patterns
The UI should favor these interactions:

- click to open task
- inspect code in place
- run terminal command
- observe result immediately
- review browser changes side-by-side
- continue without breaking context

The product should minimize friction between intention and action.

---

### 18. Future UI Enhancements
Future versions may add:

- draggable panes
- customizable workspace layouts
- split-view diff inspector
- richer browser debugging overlays
- command replay
- persistent bookmarks for investigations
- task templates
- multi-session comparison mode
- richer visual timelines

These are future improvements, not dependencies for the first version.

---

### 19. Final UI/UX Summary
The UI/UX for Agent Phantom Recovery should be built as a premium, liquid-glass, agentic workspace with:

- browser embedded inside the app
- code visible on one side
- terminal docked at the bottom
- chat and agent console on the other side
- left sidebar for history, skills, tools, login, and settings
- strong support for long-horizon execution
- Antigravity-optimized workflow visibility

The result should feel like a professional mission-control environment for autonomous engineering work, not a conventional chat application.

