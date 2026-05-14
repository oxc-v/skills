# skills

Codex extension workspace for lightweight skills and packaged plugins.

## Layout

```text
.agents/
├── skills/                 # Simple repo-level skills
│   └── simple-skill/
│       ├── SKILL.md
│       └── agents/
│           └── openai.yaml
└── plugins/
    └── marketplace.json    # Plugin catalog for this repository

plugins/
└── my-plugin/
    ├── .codex-plugin/
    │   └── plugin.json
    ├── skills/
    │   └── plugin-skill/
    │       ├── SKILL.md
    │       └── agents/
    │           └── openai.yaml
    └── assets/
```

Use `.agents/skills` for small standalone skills. Use `plugins/` when a capability needs packaging, marketplace metadata, MCP/App integrations, hooks, or richer assets.
