# Agent Skills Development Workspace

A dedicated workspace for authoring, structuring, testing, and refining AI agent skills.

This repository is inspired by **Matt Pocock's `write-a-skill` / `writing-great-skills`** methodology and adheres to the Antigravity & Agent Skills standard specification.

---

## 📂 Project Structure

```text
agent-skills/
├── .agents/
│   └── skills/
│       └── write-a-skill/           # Meta-skill for authoring new skills
│           ├── SKILL.md
│           ├── references/
│           └── templates/
├── templates/
│   └── skill-scaffold/              # Starter boilerplate for new skills
│       ├── SKILL.md
│       ├── references/
│       ├── examples/
│       └── scripts/
├── skills/                          # Categorized skills directory
│   ├── software/                    # Technical & software engineering skills
│   ├── for-fun/                     # Creative & entertainment skills
│   └── README.md
└── README.md
```

---

## 🚀 How to Author a New Skill

When you want to create a new skill in this repository:

1. **Invoke the workflow**: Ask the agent: *"Let's write a new skill for [your topic]"* or *"Help me create a skill for [goal]"*.
2. **Follow the 4-Phase Process**:
   - **Phase 1: Gather Requirements**: Clarify category (`software`, `for-fun`, etc.), trigger conditions, and reference needs.
   - **Phase 2: Draft the Skill**: Scaffold under `skills/<category>/<skill-name>/` with a clean `SKILL.md` (<500 lines) leveraging progressive disclosure.
   - **Phase 3: Review & Validate**: Audit against the [Quality Checklist](.agents/skills/write-a-skill/references/checklist.md) and [Best Practices](.agents/skills/write-a-skill/references/best-practices.md).
   - **Phase 4: Finalize**: Verify paths, test trigger scenarios, and update `skills/README.md`.

---

## 🎯 Key Design Principles

1. **Progressive Disclosure**: Keep `SKILL.md` concise. Move voluminous reference documentation to `references/` and code examples to `examples/`.
2. **Precision Descriptions**: The YAML frontmatter `description` acts as the router for model activation. Write it in third-person, clearly defining *what* it does and *when* to use it.
3. **Category Grouping**: Group skills into clean category folders (`software`, `for-fun`) and include `category` in YAML frontmatter.
4. **Determinism over Stochasticity**: Encapsulate fragile, multi-step CLI commands into scripts inside `scripts/`, letting the LLM manage execution and error handling.
