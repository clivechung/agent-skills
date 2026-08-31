# Reusable Agent Skills

A modular repository of **reusable agent skills and capabilities** designed for autonomous AI agents and coding assistants to execute structured, automated tasks. The catalog spans mission-critical engineering workflows—such as architecture reviews and Python API refactoring—to lifestyle tasks like precision pour-over coffee brewing.

This repository is inspired by **Matt Pocock's `write-a-skill` / `writing-great-skills`** methodology and adheres to the Antigravity & Agent Skills standard specification.

---

## 🧭 Skills Catalog

| Skill Name | Category | Primary Focus & Purpose | Skill File |
| :--- | :--- | :--- | :--- |
| **`trem`** | `software` | Language-agnostic code review, audit, and refactoring framework based on four pillars: **T**estable, **R**eadable, **E**xtensible, and **M**aintainable. | [`SKILL.md`](skills/software/trem/SKILL.md) |
| **`trem-python`** | `software` | Python-specific TREM engineering framework covering `uv`, `typer`, `fastapi`, `pydantic`, `logging`, `alembic` / `sqlalchemy`, and `fastmcp`. | [`SKILL.md`](skills/software/trem-python/SKILL.md) |
| **`skillmcp`** | `ai` / `software` | Stateless Model Context Protocol (MCP) server integration over Streamable HTTP to discover, search, inspect, and retrieve agent skills dynamically. | [`SKILL.md`](skills/ai/skillmcp/SKILL.md) |
| **`pour-over-coffee-brewing`** | `for-fun` | Master barista guide for pour-over coffee brewing, Timemore S3 Chestnut grinder calibration, 3-Pour and 4:6 brewing methods, and extraction troubleshooting. | [`SKILL.md`](skills/for-fun/pour-over-coffee-brewing/SKILL.md) |

---

## 💡 Skill Usage Examples

### 1. `trem` — Universal Code Review & Verification

Evaluates any codebase or pull request against the four TREM pillars (Testability, Readability, Extensibility, Maintainability) and produces a structured scorecard with remediations.

**Sample Prompts:**
- *"Review this authentication service implementation using TREM principles."*
- *"Audit this pull request for testability bottlenecks and extensibility anti-patterns."*
- *"Refactor this monolithic order-processing function into a clean TREM-compliant module."*

**Example Agent Workflow:**
1. Evaluates dependency injection, cyclomatic complexity, open/closed compliance, and blast radius.
2. Generates a **TREM Scorecard** with ratings (🟢 / 🟡 / 🔴) for each pillar.
3. Provides concrete remediation steps and a fully refactored, decoupled code implementation.

---

### 2. `trem-python` — Modern Python Engineering Framework

Audits and builds Python applications using modern idiomatic tooling: `uv`, `pydantic-settings`, `logging`, `fastapi`, `typer`, `alembic`, `sqlalchemy` (async), and `fastmcp`.

**Sample Prompts:**
- *"Build a new FastAPI microservice with Pydantic settings and async SQLAlchemy following TREM Python standards."*
- *"Review this legacy Python script, eliminate bare `print()` statements, and convert configuration to Pydantic BaseSettings."*
- *"Create a testable Typer CLI tool with shared domain services and pytest fixtures."*

**Example Agent Workflow:**
1. Inspects dependency management (`uv` / `pyproject.toml`) and architectural layer separation.
2. Ensures all endpoints use `fastapi.Depends()` for test isolation with `pytest` and `httpx.AsyncClient`.
3. Verifies schema migrations are tracked via `alembic` and logging uses `logging.getLogger(__name__)`.

---

### 3. `skillmcp` — Stateless Skill Management MCP Server

Integrates with a containerized or remote SkillMCP server over stateless Streamable HTTP to query, search, and load skills on demand.

**Sample Prompts:**
- *"Search our remote SkillMCP server for any available testing and verification skills."*
- *"Fetch the complete instructions and reference guides for `trem-python` via SkillMCP."*
- *"Connect to `http://localhost:8080/mcp` and list all registered agent capabilities."*

**Example Agent Workflow:**
1. Connects to `POST /mcp` with stateless JSON-RPC over Streamable HTTP.
2. Executes tools like `list_skills`, `search_skills(query="...")`, and `get_skill(name="...")`.
3. Loads supplemental reference documents via `read_skill_reference` without polluting the model's base context.

---

### 4. `pour-over-coffee-brewing` — Precision Coffee Brewing & Calibration

Calibrates hand grinders (such as the Timemore S3 Chestnut), applies precision pour frameworks (3-Pour and 4:6 methods), and diagnoses extraction defects.

**Sample Prompts:**
- *"I am brewing a washed Ethiopian light roast with a Timemore S3 grinder. What grind setting, water temperature, and ratio should I use?"*
- *"My pour-over finished in 2 minutes and tastes sour and weak. How should I adjust my grind and recipe?"*
- *"Guide me step-by-step through the 4:6 method with 20g of medium-dark roast beans."*

**Example Agent Workflow:**
1. Recommends specific click adjustments (e.g., dial collar settings between `5.5` and `8.5`).
2. Provides a timed pour schedule with target water weights and drawdown intervals.
3. Offers targeted troubleshooting (e.g., coarsening grind to prevent fines migration and astringency).

---

## 📂 Skills Directory Structure

```text
skills/
├── software/                        # Software engineering & architecture skills
│   ├── trem/                        # Universal TREM code review & verification
│   │   ├── SKILL.md
│   │   ├── references/              # In-depth principles, rubrics, anti-patterns
│   │   └── examples/                # Review walkthroughs
│   └── trem-python/                 # Python-tailored TREM framework
│       ├── SKILL.md
│       ├── references/              # Stack patterns (FastAPI, uv, Typer, Alembic, FastMCP)
│       └── examples/                # End-to-end Python refactoring examples
├── ai/                              # AI orchestration & MCP skills
│   └── skillmcp/                    # Stateless MCP skill repository client
│       ├── SKILL.md
│       ├── references/              # JSON-RPC spec & Streamable HTTP lifecycle
│       └── examples/                # Client implementations
└── for-fun/                         # Lifestyle, hobby & creative skills
    └── pour-over-coffee-brewing/    # Barista guide & grinder calibration
        ├── SKILL.md
        └── references/              # Grinder math, recipes & extraction matrices
```

> **Authoring a New Skill**: To create a new skill in any category, scaffold it under `skills/<category>/<skill-name>/` using [`templates/skill-scaffold/`](templates/skill-scaffold/) or follow the interactive authoring workflow in [`.agents/skills/write-a-skill/`](.agents/skills/write-a-skill/SKILL.md).


### 🎯 Key Design Principles

1. **Progressive Disclosure**: Keep `SKILL.md` lean and actionable. Move voluminous specifications and cheat sheets to `references/`, and full code samples to `examples/`.
2. **Precision YAML Routing**: The YAML frontmatter `description` acts as the semantic activation trigger for LLMs. It is written in third-person, clearly specifying *what* the skill accomplishes and *when* to activate it.
3. **Category Namespaces**: Skills are neatly partitioned into semantic directories (`software`, `ai`, `for-fun`) to maintain high scalability as the catalog expands.
4. **Determinism over Stochasticity**: Encapsulate fragile, multi-step CLI operations into executable helper scripts inside `scripts/`, letting the agent orchestrate execution with robust error handling.

---

## 📖 Appendix: Using Skills across AI Platforms

You can easily import and run skills from this repository across different LLM environments:

### 1. Google Gemini & Antigravity IDE

* **Antigravity IDE / Agent Customizations**:
  - Clone or copy this repository into your workspace. Antigravity automatically discovers skills placed under `skills/` or referenced in your workspace configuration.
  - Alternatively, register global skills in `%USERPROFILE%\.gemini\config\skills\` (Windows) or `~/.gemini/config/skills/` (macOS/Linux).
* **Gemini CLI / Google AI Studio / Custom Gems**:
  - Open **Gemini Gems** (or Google AI Studio System Instructions).
  - Copy the contents of the target skill's `SKILL.md` (and any key reference documents) directly into the **Instructions / System Prompt** box.
  - If using Gemini Function Calling / MCP, expose the skill instructions via the `skillmcp` tool server.

### 2. Anthropic Claude (Claude Desktop, Claude Projects & Claude Code)

* **Claude Projects**:
  - Create a new Project in Claude (e.g., *"Code Review Assistant"* or *"Coffee Barista"*).
  - Under **Project Knowledge**, upload the `SKILL.md` file along with files from `references/` and `examples/`.
  - In the **Project Instructions**, paste the skill's trigger guidance (e.g., *"Follow the TREM review workflows defined in the attached SKILL.md whenever analyzing code."*).
* **Claude Desktop with MCP**:
  - To load skills dynamically via MCP, add the `skillmcp` server endpoint to your `claude_desktop_config.json`:
    ```json
    {
      "mcpServers": {
        "skillmcp": {
          "command": "uvx",
          "args": ["fastmcp", "run", "path/to/skillmcp_server.py"]
        }
      }
    }
    ```
* **Claude Code (CLI)**:
  - Place skills in `.claude/skills/` or use Claude Code's project instruction files (`CLAUDE.md`) linking to the skill markdown paths.

### 3. OpenAI ChatGPT (Custom GPTs & Custom Instructions)

* **Custom GPTs (GPT Builder)**:
  - Create a new Custom GPT in ChatGPT.
  - In the **Instructions** tab, define the role and summarize when to trigger the workflows.
  - In the **Knowledge** section, upload `SKILL.md`, `references/`, and `examples/` as attached documents.
  - *(Optional)* In **Actions**, configure an OpenAPI or MCP connector pointing to your remote `skillmcp` server to let ChatGPT search and retrieve skills dynamically.
* **ChatGPT Custom Instructions / Prompts**:
  - In standard chat sessions, paste the relevant `SKILL.md` markdown at the top of your prompt enclosed in `<skill>` tags:
    ```markdown
    <skill>
    [Paste contents of SKILL.md here]
    </skill>

    Please apply this skill to the following code/request:
    [Your code or question here]
    ```
