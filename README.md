# AI Bootstrap
Copy `ai-bootstrap` into to any project for a streamlined AI-based workflow.  Heavily modify per project.


## Agent Command Cheatsheet
See [AGENT-COMMANDS.md](AGENT-COMMANDS.md)


## Key Concepts
### PRD-First Development
Create documentation before you code. Your `.agents/PRD.md` becomes the source of truth for every AI 
conversation and for each granular feature. Without it AI makes assumptions and is likely to context drift. So for:
- New projects:  Full PRD with features broken down into phases
- Brownfield:  Document existing codebase, define modules, and what comes next

### Modular rules context architecture
Stop dumping everything in one massive file for your AI agent rules. 
Split by concern and only load what's relevant on-demand so context remains lean.
Aggressively limit the size and scope of global rules.

For example, create:

    .agents/
    ├── reference/
    │   ├── components.md   # frontend best practices
    │   ├── api.md          # backend best practices
    │   └── deploy.md       # deployment best practices
    └── AGENTS.md           # global AI agent rules

The `.agents/GLOBAL.md` file mentions each reference material for the AI agent to discover. 
And when working on a given module you should ensure the AI agent loads only reference documentation 
that is necessary for the current task at hand.  Limit context as much as possible.

### Build features in cycles
To avoid context window degradation **reset context** between each step in the cycle.

- Step 1) Plan
- Step 2) Implement
- Step 3) Verify

Planning and implementation are **separate** conversations.  
Planning should result in a planned feature document, like so:

    Plan -> [Planning Doc] -> Reset Context -> Implement

As an example,

    .agents/
    ├── plans/
    │   ├── feature-YYMM-add_users.md
    │   ├── feature-YYMM-secure_passwords.md
    │   └── feature-YYMM-dashboard.md
    └ ...


### Start planning with the `prime` command
Start each planning session with the `prime` command to load up repeatable, predictable context every time.


### System evolution mindset
If you do something more than a few times, create a new command. 
Over time your agent commands and references should become specific to each project.
In addition, treat every bug as an opportunity to evolve your AI coding system. 
You can fix:
- Global rules
- On demand context and references
- Commands & workflows

For example,
| Bug | Evolution |
|-----|-----------|
| AI uses wrong import style | New rule: always use @/ path aliases |
| AI forgets to run tests | Update structured plan to include section for tests to always run |
| AI doesn't understand auth flow | New context reference doc: auth_architecture.md |

Every time you develop a new feature, your coding agent should get smarter.
