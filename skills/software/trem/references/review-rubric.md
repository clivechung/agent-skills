# TREM Review Rubric & Scoring Guide

A standardized grading rubric to evaluate code quality, categorize severity, and determine readiness for merge.

---

## 🚦 Status Indicators & Severity Levels

When reviewing code, assign a rating to each of the 4 pillars:

| Status | Meaning | Action Required |
| :---: | :--- | :--- |
| 🟢 **Pass** | Meets modern engineering standards. No major violations. | Ready to merge. Minor suggestions are optional. |
| 🟡 **Needs Work** | Contains code smells or anti-patterns that increase tech debt. | Should address recommendations before merge. |
| 🔴 **Blocker** | Severe architectural violation (e.g. untestable side-effects, god method, swallowed exceptions). | Must be refactored before proceeding. |

---

## 📋 Evaluation Matrix

### 1. Testability (T)

- 🟢 **Pass**:
  - All external dependencies (I/O, network, database, time, crypto) are injected.
  - Business logic is isolated from infrastructure.
  - 100% of branch logic can be unit-tested without network/DB mocks or monkey-patching.
  - *Prefer using the `tdd` skill (Red-Green-Refactor) during code generation and refactoring to verify code against automated test cases.*
- 🟡 **Needs Work**:
  - Some optional dependencies instantiated inline with default fallbacks.
  - Unit testing requires extensive mocking libraries or reflection.
- 🔴 **Blocker**:
  - Direct database/HTTP calls embedded in core business logic.
  - Global mutable state or static singletons preventing concurrent testing.

---

### 2. Readability (R)

- 🟢 **Pass**:
  - Clear, intent-revealing names conforming to domain terms.
  - Cognitive complexity is low: shallow nesting ($\le 2$ levels), guard clauses used.
  - Comments explain non-obvious business rules or performance trade-offs without restating code.
- 🟡 **Needs Work**:
  - 3-4 levels of nesting or overly dense inline boolean expressions.
  - A few vague names (`data`, `temp`, `res`).
- 🔴 **Blocker**:
  - Deep pyramid of doom ($\ge 5$ levels of indentation).
  - Obfuscated "clever" one-liners or misleading variable names.

---

### 3. Extensibility (E)

- 🟢 **Pass**:
  - Follows Open-Closed Principle: new variants can be plugged in via interfaces/strategies.
  - Uses composition over inheritance.
  - Zero tight coupling to third-party SDK types in domain layer.
- 🟡 **Needs Work**:
  - Switch/case branching used for variants, but isolated in a single factory.
- 🔴 **Blocker**:
  - Sprawling switch statements across multiple files to handle type variants.
  - Hardcoded vendor APIs directly intertwined with core domain rules.

---

### 4. Maintainability (M)

- 🟢 **Pass**:
  - Strict Single Responsibility Principle; functions are focused ($\le 30$ lines).
  - Explicit error handling with structured context; no silent failures.
  - Clear module boundaries with minimal blast radius.
- 🟡 **Needs Work**:
  - Functions doing slightly too much (40-60 lines) but still understandable.
  - Generic error messages without domain context.
- 🔴 **Blocker**:
  - Monolithic God object/function (>100 lines).
  - Catch-all exception blocks swallowing errors silently.
  - High risk of regression cascade across unrelated modules.

---

## 🛡️ Mandatory Final TREM Rule Set Verification Matrix

At the conclusion of every code review, refactoring, or code generation session, the reviewer must audit the final code against each item in this rule set. All items must achieve **PASS (✅)** status before concluding the session.

| Pillar | Rule ID | Quality Standard & Verification Criteria | Required State for Pass |
| :--- | :--- | :--- | :--- |
| **Testable** | **T1** | **Dependency Inversion & Injection** | All I/O, network clients, databases, and filesystem access are injected via interfaces/parameters; no inline `new Service()`. |
| **Testable** | **T2** | **Deterministic Time & Environment** | Clocks, timestamps, RNG, and environment variables are parameterized or provided via clock abstractions. |
| **Testable** | **T3** | **Isolated Business Logic** | Pure domain calculations and validations are partitioned from infrastructure side-effects. |
| **Testable** | **T4** | **Observability & Clear Outputs** | All routines return explicit values, typed result structures, or domain errors; zero hidden side effects. |
| **Readable** | **R1** | **Intention-Revealing Naming** | Variables, functions, and types use unambiguous domain nomenclature; booleans use predicate phrasing (`isX`, `hasY`). |
| **Readable** | **R2** | **Flat Control Flow & Guard Clauses** | Indentation depth does not exceed 2 levels; validations and preconditions exit early with guard clauses. |
| **Readable** | **R3** | **Explanatory Rationale Comments** | Comments explain the *why* (domain logic, performance trade-offs, constraints), never restating obvious syntax. |
| **Readable** | **R4** | **Strict Type Contracts** | Strict typing enforced across inputs and outputs; no untyped `any`, raw `Object`, or primitive obsession. |
| **Extensible** | **E1** | **Open-Closed Principle (OCP)** | New variants, channels, or strategies can be added by implementing contracts without modifying core orchestrator logic. |
| **Extensible** | **E2** | **Composition Over Inheritance** | Behavior is composed via strategies, adapters, and functional composition rather than deep class hierarchies. |
| **Extensible** | **E3** | **Narrow Role Interfaces** | Interfaces are segregated, cohesive, and decoupled from third-party vendor SDK types. |
| **Maintainable** | **M1** | **Single Responsibility Principle (SRP)** | Every class/module has a single reason to change; functions remain small, focused, and cohesive ($\le 30$ lines). |
| **Maintainable** | **M2** | **Encapsulation & Blast Radius** | Internal state and implementation details are private; module interfaces minimize ripple effects across consumers. |
| **Maintainable** | **M3** | **Structured Error Handling** | No swallowed exceptions or empty `catch` blocks; errors are wrapped in typed domain exceptions with contextual metadata. |

---

## 🏁 Session Sign-Off Decision Flow

```
┌──────────────────────────────────────────────────────────┐
│  Code Review / Generation / Refactoring in Progress      │
└────────────────────────────┬─────────────────────────────┘
                             │
                             ▼
┌──────────────────────────────────────────────────────────┐
│  Apply Refactorings & Remediations                       │
└────────────────────────────┬─────────────────────────────┘
                             │
                             ▼
┌──────────────────────────────────────────────────────────┐
│  Audit Final Code Against TREM Rule Set (T1-T4, R1-R4,   │
│  E1-E3, M1-M3)                                           │
└────────────────────────────┬─────────────────────────────┘
                             │
            ┌────────────────┴────────────────┐
            ▼                                 ▼
   [Any Rule Violations?]             [All Rules Passed?]
            │                                 │
            ▼ YES                             ▼ YES
┌───────────────────────────┐     ┌───────────────────────────────┐
│ Fix residual anti-pattern │     │ Generate Final Review Report  │
│ & re-audit                │     │ with Verified Sign-Off Table  │
└───────────────────────────┘     └───────────────────────────────┘
```
