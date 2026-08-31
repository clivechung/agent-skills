# Third-Party Notices & Skill Licenses

This document declares the skills bundled, distributed, and used within the **SkillMCP** project, along with their authors, provenance, and license terms.

---

## Summary of Packaged Domain Skills (`skills/`)

These domain skills are served and distributed via the SkillMCP Model Context Protocol (MCP) server:

| Skill | Category | Primary Purpose | Origin / Attribution | License |
| :--- | :--- | :--- | :--- | :--- |
| **`skillmcp`** | `ai` | MCP connection, discovery, and tool integration guide | SkillMCP Project (clivechung) | MIT |
| **`trem`** | `software` | TREM code review & verification framework (T, R, E, M) | SkillMCP Quality Engineering | MIT |
| **`trem-python`** | `software` | Python engineering patterns (`uv`, `fastmcp`, `typer`, `fastapi`) | SkillMCP Quality Engineering | MIT |
| **`code-haiku`** | `for-fun` | Summarizes code changes or PRs into 5-7-5 haikus | SkillMCP Project (clivechung) | MIT |
| **`pour-over-coffee-brewing`** | `for-fun` | Pour-over coffee brewing, grinder calibration & troubleshooting | SkillMCP Project (clivechung) | MIT |

---

## Summary of Workspace Agent Skills (`.agents/skills/`)

These meta-skills assist autonomous coding agents during development within this repository:

| Skill | Primary Purpose | Origin / Attribution | License |
| :--- | :--- | :--- | :--- |
| **`write-a-skill`** | 4-phase interactive skill authoring workflow | Adapted from Matt Pocock's skill authoring methodology | MIT |
| **`trem`** | TREM architectural review and quality audit | SkillMCP Quality Engineering | MIT |

---

## Detailed Skill Declarations & Licenses

### 1. SkillMCP Server Integration (`skills/ai/skillmcp`)
- **Path**: `skills/ai/skillmcp/SKILL.md`
- **Author**: clivechung <https://github.com/clivechung/skillmcp>
- **License**: MIT
- **Copyright**: Copyright (c) 2026 clivechung
- **Description**: Operational workflow and JSON-RPC specifications for discovering, searching, inspecting, and retrieving skills from SkillMCP.

```text
MIT License

Copyright (c) 2026 clivechung

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.
```

---

### 2. TREM Engineering Framework (`skills/software/trem`, `skills/software/trem-python`, & `.agents/skills/trem`)
- **Paths**: `skills/software/trem/SKILL.md`, `skills/software/trem-python/SKILL.md`, `.agents/skills/trem/SKILL.md`
- **Author**: SkillMCP Quality Engineering / clivechung
- **License**: MIT
- **Copyright**: Copyright (c) 2026 clivechung
- **Description**: Software quality assessment framework evaluating codebases against the 4 TREM pillars: Testable, Readable, Extensible, and Maintainable, including modern Python ecosystem standards.

```text
MIT License

Copyright (c) 2026 clivechung

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.
```

---

### 3. Skill Authoring Workflow (`.agents/skills/write-a-skill`)
- **Path**: `.agents/skills/write-a-skill/SKILL.md`
- **Attribution**: Adapted from Matt Pocock's agent skill workflows and prompt design methodologies (<https://github.com/mattpocock>)
- **License**: MIT
- **Description**: Workflows for structured skill authoring, progressive disclosure decomposition, and skill validation.

```text
MIT License

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.
```

---

### 4. Code Haiku (`skills/for-fun/code-haiku`)
- **Path**: `skills/for-fun/code-haiku/SKILL.md`
- **Author**: SkillMCP Project / clivechung
- **License**: MIT
- **Copyright**: Copyright (c) 2026 clivechung
- **Description**: Poetic summarizer converting code changes, pull requests, and software concepts into 5-7-5 syllable haikus.

```text
MIT License

Copyright (c) 2026 clivechung

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.
```

---

### 5. Master Pour-Over Coffee Brewing (`skills/for-fun/pour-over-coffee-brewing`)
- **Path**: `skills/for-fun/pour-over-coffee-brewing/SKILL.md`
- **Author**: SkillMCP Project / clivechung
- **License**: MIT
- **Copyright**: Copyright (c) 2026 clivechung
- **Description**: Comprehensive guide to grinder calibration, pour-over extraction recipes (3-Pour and 4:6 methods), and dialing-in troubleshooting.

```text
MIT License

Copyright (c) 2026 clivechung

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.
```

---

## Main Project License

For the core SkillMCP server engine, CLI tools, Docker configurations, and tests, see [LICENSE](LICENSE).
