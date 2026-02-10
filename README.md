# AI Bootstrap
Copy `ai-bootstrap/` into to any project for a streamlined AI-based workflow.  Heavily modify per project.


## Agent commands
See the [AGENTS.md](AGENTS.md) cheatsheet for available agent commands.


## Key concepts
### Prioritize PRD-first development
Create documentation before you code. Your `.agents/PRD.md` becomes the source of truth for every AI 
conversation and for each granular feature. Without it AI can make bad assumptions and will context drift. 
So for:
- New projects:  Full PRD with features broken down into phases
- Brownfield:  Document existing codebase, define modules, and what comes next

### Build a modular rules architecture
Stop dumping everything in one massive file for your AI agent rules. 
Split by concern and only load what's relevant on-demand so context remains lean.
Aggressively limit the size and scope of global rules.

For example, create:

    .agents/
    ├── reference/
    │   ├── components.md   # frontend best practices
    │   ├── api.md          # backend best practices
    │   └── deploy.md       # deployment best practices
    └── GLOBAL-RULES.md     # global rules for AI agents

The `.agents/GLOBAL-RULES.md` file mentions each reference material for the AI agent to discover. 
And when working on a given module ensure the AI agent loads only necessary reference documentation 
for the current task at hand.  Limit context bloat as much as possible.

### Add bite-size features in cycles
AI performs at its best when given small tasks, one at a time.
To avoid context window degradation **reset context** between each step in the cycle.

- Step 1) Plan
- Step 2) Implement
- Step 3) Verify

Planning and implementation are **separate** conversations.  
Planning should result in a planned feature document, like so:

    Plan → [Planning Doc] → Reset Context → Implement

For example,

    .agents/
    ├── plan/
    │   └── features/
    │       ├── feature-YYYY-MM-secure_password.md    # one-off change
    |       ├── feature-users.md                      # desired state for users; evolves over time
    │       └── feature-dashboard.md                  # desired state for dashboard; evolves over time 
    └ ...


### Start planning with the `prime` command
Start each planning session with the `prime` command to load repeatable, predictable context every time.


### Adopt an evolution mindset
If you do something more than a few times, create a new command. 
Over time your agent commands and reference documentation should become specific to each project.
In addition, treat every bug as an opportunity to evolve your AI coding system. 
For each bug you can also fix:
- Global rules
- On demand context and references
- Commands & workflows

For example,
| Bug | Evolution |
|-----|-----------|
| AI uses wrong import style | New rule: always use @/ path aliases |
| AI forgets to run tests | Update structured plan to include section for tests to always run |
| AI doesn't understand auth flow | New context reference doc: auth_architecture.md |

Every time you develop a new feature, your coding agent should become smarter.

### Use high-value context engineering
Conversations with an agent can include:
- Goals
- Success criteria
- What not to do
- Documentation to reference
- Task list
- Validation strategy
- Desired codebase structure

