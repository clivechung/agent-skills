# Custom Skills Directory

This folder holds custom agent skills developed in this project, grouped by category.

---

## 🛠️ Software Skills

- [**trem**](software/trem/SKILL.md) — Comprehensive code review, verification, and refactoring framework based on the 4 pillars: **T**estable (DI & decoupling), **R**eadable (intent-revealing & low complexity), **E**xtensible (Open-Closed & patterns), and **M**aintainable (cohesion & blast radius).

---

## 🎮 For-Fun Skills

- [**code-haiku**](for-fun/code-haiku/SKILL.md) — Summarizes code changes, pull requests, or debugging sessions as poetic 5-7-5 syllable haikus.

---

## Directory Structure

Each skill resides within a category directory (`skills/<category>/<skill-name>/`):

```text
skills/
├── <category>/                # e.g., software, for-fun
│   └── <skill-name>/
│       ├── SKILL.md           # Required: Main instruction file (with category frontmatter)
│       ├── references/        # Optional: Deep specs and reference manuals
│       ├── examples/          # Optional: Usage examples
│       └── scripts/           # Optional: Deterministic helper scripts
```

To create a new skill in a category, use the `write-a-skill` meta-skill or copy from `templates/skill-scaffold/`.
