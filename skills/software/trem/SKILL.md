---
name: trem
description: >-
  Reviews, audits, and guides code generation against the TREM principles: Testable, Readable, Extensible, and Maintainable.
  Use this skill whenever performing code reviews, PR audits, refactoring architecture, or verifying newly generated code.
category: software
---

# TREM Code Review & Verification

A software engineering quality framework founded on four pillars:
- **T - Testable**: Decoupled, deterministic, dependency-injected, and easily unit-testable. *(Prefer using the `tdd` skill so that newly generated and refactored code is authored and verified using a Test-Driven Development approach).*
- **R - Readable**: Self-documenting, low cognitive complexity, with comments explaining non-obvious *why* rather than *what*.
- **E - Extensible**: Open for extension, closed for modification, leveraging design patterns and composition.
- **M - Maintainable**: Single responsibility, small blast radius, structured error handling, and high refactorability.

---

## ⚡ Quick Assessment Checklist

When evaluating or generating any block of code, verify these core questions:

| Pillar | Focus Area | Verification Question |
| :--- | :--- | :--- |
| **T** (Testable) | **Decoupling, DI & TDD** | Can every unit be tested in isolation? Was code generated and verified using a TDD (`tdd` skill) approach? |
| **R** (Readable) | **Clarity & Intent** | Can a new engineer understand the business logic in 60 seconds without decrypting magic logic? |
| **E** (Extensible) | **Open/Closed** | Can new features/strategies be added without modifying existing tested core functions? |
| **M** (Maintainable) | **Cohesion & Blast Radius** | Does every module have a single reason to change with predictable, graceful error handling? |

---

## 🛠️ Workflows

### Workflow 1: Code Review & PR Audit

Use this workflow to review existing code or proposed pull requests.

1. **Analyze Code Structure**: Read the source files and identify module boundaries, dependencies, and control flows.
2. **Evaluate Against TREM Pillars**:
   - **Testability Audit**: Look for hardcoded dependencies (`new Service()`), hidden globals, static clocks, coupled I/O, and missing unit tests.
   - **Readability Audit**: Check for deep nesting (>3 levels), ambiguous names, missing rationale comments, and complex boolean logic.
   - **Extensibility Audit**: Check for large `switch/if-else` chains on types, lack of interfaces/adapters, and tight vendor coupling.
   - **Maintainability Audit**: Check for god functions (>40 lines), shotgun surgery risks, swallowed errors, and missing boundary validation.
3. **Draft Refactored Implementation**: Produce the modernized, clean code resolving all identified findings (prefer applying the `tdd` skill when creating refactored suites).
4. **Verify Against TREM Rule Set**: Perform the mandatory concluding audit against the complete TREM rule set checklist (all 4 pillars) to guarantee zero residual anti-patterns or regressions before delivering the report.
5. **Generate Structured TREM Report**: Produce the review using the standard template below, including the verified scorecard and final rule set compliance sign-off.

---

### Workflow 2: Code Generation Verification

Use this self-verification workflow before presenting generated code to the user.

1. **Testability & TDD Check**: Did you inject dependencies (DB, HTTP client, file system, clocks) via constructors/parameters rather than instantiating them inline? *Prefer using the `tdd` skill (Red-Green-Refactor cycle) so that new functionality is driven and verified by unit tests.*
2. **Readability Check**: Are functions small, guard clauses used, variables expressively named, and complex domain formulas documented?
3. **Extensibility Check**: Are interfaces/contracts defined for behaviors that are expected to vary or grow?
4. **Maintainability Check**: Is error handling explicit, types well-defined, and side effects isolated?
5. **Final TREM Rule Set Verification**: Systematically audit the generated code against the complete TREM rule set checklist to ensure 100% compliance across all 4 pillars before concluding the session.

---

### Workflow 3: TREM Refactoring

Use this workflow when modernizing legacy or non-compliant code.

1. **Extract Interfaces, Invert Dependencies & Apply TDD** (*Testability*): Introduce abstractions for external dependencies and inject them. Prefer utilizing the `tdd` skill to author isolated tests verifying existing and refactored behaviors.
2. **Flatten Control Flow & Clarify Naming** (*Readability*): Replace nested conditions with guard clauses and replace cryptic tokens with intention-revealing names.
3. **Apply Behavioral Patterns** (*Extensibility*): Replace condition-heavy branching with Strategy, Factory, or Adapter patterns.
4. **Enforce Single Responsibility** (*Maintainability*): Split monolithic routines into cohesive, focused units with standardized error envelopes.
5. **Post-Refactoring Rule Set Verification**: Verify the refactored code against every item in the TREM rule set checklist to confirm all smells are eliminated without introducing secondary issues.

---

## 📋 Standard TREM Review Output Template

When providing a TREM code review, use the following structured output:

````markdown
# 🛡️ TREM Code Review Report

## Executive Summary
[1-2 paragraph summary of the overall code quality, architectural strengths, and key risks.]

## 📊 TREM Scorecard

| Pillar | Status | Key Observations |
| :--- | :---: | :--- |
| **Testable** | 🟢/🟡/🔴 | [Summary of testability findings] |
| **Readable** | 🟢/🟡/🔴 | [Summary of readability findings] |
| **Extensible** | 🟢/🟡/🔴 | [Summary of extensibility findings] |
| **Maintainable** | 🟢/🟡/🔴 | [Summary of maintainability findings] |

---

## 🔍 Detailed Findings & Recommendations

### 1. Testability (T)
- ⚠️ **[Issue Title]** (Line XX-YY): [Description of problem, e.g. tightly coupled database client]
  - **Remediation**: [How to fix, e.g. introduce Repository interface and constructor injection]

### 2. Readability (R)
- 💡 **[Issue Title]** (Line XX-YY): [Description of problem, e.g. nested ternary expressions]
  - **Remediation**: [How to fix, e.g. extract into descriptive helper with early return]

### 3. Extensibility (E)
- ⚠️ **[Issue Title]** (Line XX-YY): [Description of problem, e.g. hardcoded payment gateway switch]
  - **Remediation**: [How to fix, e.g. apply Strategy pattern]

### 4. Maintainability (M)
- 🚨 **[Issue Title]** (Line XX-YY): [Description of problem, e.g. swallowed exception without logging]
  - **Remediation**: [How to fix, e.g. structured custom error with context propagation]

---

## 🚀 Refactored Implementation

```[language]
// Present the clean, TREM-compliant refactored version here
```

---

## ✅ Final TREM Rule Set Verification Sign-Off

*Mandatory verification confirming that all 4 pillars comply with the full TREM rule set at the conclusion of the session:*

| Pillar | Rule / Standard | Status | Verification Note |
| :--- | :--- | :---: | :--- |
| **Testable** | Inverted Dependencies & Dependency Injection | ✅ PASS | [e.g., All external DB/HTTP calls abstracted and injected via constructor] |
| **Testable** | Deterministic Execution & Isolated Clocks/State | ✅ PASS | [e.g., Clocks and random state decoupled for deterministic tests] |
| **Testable** | Pure Business Logic & Observable Outcomes | ✅ PASS | [e.g., Pure calculation routines isolated from I/O boundaries] |
| **Readable** | Domain Intention-Revealing Naming | ✅ PASS | [e.g., Clear domain names; boolean predicates used throughout] |
| **Readable** | Flat Control Flow & Guard Clauses | ✅ PASS | [e.g., Nesting depth ≤ 2 levels; early validation returns] |
| **Readable** | Explanatory Rationale Comments (*Why*, not *What*) | ✅ PASS | [e.g., Domain discount rules and edge cases documented] |
| **Extensible** | Open-Closed Principle (OCP) Compliance | ✅ PASS | [e.g., New strategies addable without editing core processor] |
| **Extensible** | Modern Behavioral & Structural Design Patterns | ✅ PASS | [e.g., Strategy pattern with registry used for polymorphic handling] |
| **Maintainable** | Single Responsibility Principle & High Cohesion | ✅ PASS | [e.g., Monolith decoupled into 4 cohesive, single-purpose classes] |
| **Maintainable** | Structured & Predictable Error Handling | ✅ PASS | [e.g., Explicit domain errors thrown with context; no swallowed errors] |
````

---

## 📚 Deep Dive References & Examples

- [TREM Principles In-Depth](references/trem-principles.md) — Comprehensive technical reference on modern software design patterns and standards for T, R, E, and M.
- [Anti-Patterns & Code Smells](references/anti-patterns.md) — Catalog of typical violations and how to diagnose them.
- [Review Rubric & Scoring Guide](references/review-rubric.md) — Severity tiers, TREM rule set checklist, and session sign-off rubric.
- [Code Review Walkthrough Example](examples/code-review-walkthrough.md) — End-to-end refactoring demonstration with final rule set verification.
