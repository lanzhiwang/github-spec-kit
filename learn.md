```bash

npm install -g @google/gemini-cli
gemini --help

pip install uv
uv tool install specify-cli --from git+https://github.com/github/spec-kit.git
specify --help
specify init --help

specify init first_project1 --ai gemini --script sh --debug

@lanzhiwang ➜ /workspaces/github-spec-kit (learn-v0.0.79) $ tree -a first_project/
first_project/
├── .gemini
│   └── commands
│       ├── speckit.analyze.toml
│       ├── speckit.checklist.toml
│       ├── speckit.clarify.toml
│       ├── speckit.constitution.toml
│       ├── speckit.implement.toml
│       ├── speckit.plan.toml
│       ├── speckit.specify.toml
│       └── speckit.tasks.toml
└── .specify
    ├── memory
    │   └── constitution.md
    ├── scripts
    │   └── bash
    │       ├── check-prerequisites.sh
    │       ├── common.sh
    │       ├── create-new-feature.sh
    │       ├── setup-plan.sh
    │       └── update-agent-context.sh
    └── templates
        ├── agent-file-template.md
        ├── checklist-template.md
        ├── plan-template.md
        ├── spec-template.md
        └── tasks-template.md

8 directories, 19 files
@lanzhiwang ➜ /workspaces/github-spec-kit (learn-v0.0.79) $

```
