# OpenHands Agent Supervisor

A skill for OpenHands that spawns and coordinates multi-agent workflows when triggered.

## Quick Start

### Installation

In any OpenHands conversation, type:
```
/add-skill https://github.com/sonamcgoo-dev/openhands-agent-supervisor/tree/main
```

Or manually copy `SKILL.md` to your workspace's `.agents/skills/agent-supervisor/` folder.

### Usage

1. Start any OpenHands conversation
2. When you have a task that needs multiple agents, just say: **`go time`**
3. The supervisor will:
   - Analyze your task
   - Declare what work needs agents
   - Spawn and coordinate sub-agents
   - Report results back to you

## Example

**You:**
> I need to build a REST API with authentication, write tests, and deploy it. **go time**

**Supervisor activates:**
```
[AGENT: researcher] Investigate best practices for REST auth
[AGENT: coder] Implement the API endpoints
[AGENT: coder] Implement authentication middleware
[AGENT: tester] Write integration tests
[AGENT: reviewer] Security review of implementation
[AGENT: doc_writer] Document the API endpoints
```
→ Agents work in parallel/sequence as needed
→ Supervisor monitors and coordinates
→ Final report with deliverables

## Agent Types

| Type | Purpose |
|------|---------|
| `researcher` | Investigation, exploration, gathering info |
| `coder` | Implementation, writing code |
| `tester` | Testing, QA, validation |
| `reviewer` | Code review, quality checks |
| `doc_writer` | Documentation, comments |

## How It Works

1. **Trigger**: When "go time" is detected, supervisor mode activates
2. **Analysis**: Task is broken into components
3. **Declaration**: Agent work is declared explicitly with `[AGENT: type]` tags
4. **Spawning**: Sub-agents are created via OpenHands Cloud API
5. **Coordination**: Supervisor monitors progress, handles dependencies
6. **Reporting**: Summary delivered when complete

## Configuration

No configuration needed. The skill uses your OpenHands API credentials automatically.

## License

MIT License
