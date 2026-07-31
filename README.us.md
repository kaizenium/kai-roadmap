# Kai Roadmap

This document tracks the development order for the Kai language and its ecosystem. Phases are dependency-ordered rather than date-ordered - each phase needs the core output of the one before it. This is a realistic level of commitment for a project that is currently at the spec stage.

## Status Key

| Label | Meaning |
|---|---|
| DONE | Completed |
| IN PROGRESS | Actively being worked on |
| PLANNED | Scheduled, not yet started |
| IDEA | Under consideration, not finalized |

---

## Phase 0 Language Design

**Goal:** Settle syntax and semantics on paper.

| Status | Item |
|---|---|
| DONE | Define philosophy and target domains |
| IN PROGRESS | v0.1 language specification ([about-kai](https://github.com/kaizenium/about-kai)) |
| PLANNED | Expand syntax examples (edge cases: generic constraints, operator overloading rules, macro system details) |
| PLANNED | Collect community feedback on the spec |

## Phase 1 Lexer and Parser

**Goal:** A minimal front end that can turn Kai source into an AST.

| Status | Item |
|---|---|
| PLANNED | Lexer: token definitions, string/char/numeric literal handling |
| PLANNED | Parser: expression/statement grammar, precedence rules |
| PLANNED | AST definitions |
| PLANNED | Parser error messages (with line/column info) |

## Phase 2 Semantic Analysis

**Goal:** Working type checking and basic validation.

| Status | Item |
|---|---|
| PLANNED | Symbol table and scope resolution |
| PLANNED | Type checking (`i8`-`i64`, `u8`-`u64`, `f32`/`f64`, `bool`, `char`, `str`) |
| PLANNED | Struct/class field and method resolution |
| PLANNED | Enforce visibility rules (`public`/`private`/`protected`) |
| PLANNED | Generic type resolution (`Vector<T>`) |

## Phase 3 Code Generation

**Goal:** Turn a validated AST into working x86-64 Assembly.

| Status | Item |
|---|---|
| PLANNED | Codegen for basic expressions and control flow (`if`/`for`/`while`/`switch`) |
| PLANNED | Function calling convention, stack frame management |
| PLANNED | Struct/class memory layout |
| PLANNED | Inline assembly (`asm {}`) block integration |
| PLANNED | Combine NASM/GAS output via the linker |
| PLANNED | Milestone: run "Hello World" (Linux x86-64) |

## Phase 4 Compiler Maturity

**Goal:** Real programs become possible to write.

| Status | Item |
|---|---|
| PLANNED | Codegen for pointers/references under manual memory management |
| PLANNED | Constructor/destructor call order, inheritance and virtual dispatch |
| PLANNED | constexpr evaluation |
| PLANNED | Macro system implementation |
| PLANNED | Improve compiler error and warning messages |
| IDEA | Basic optimization passes (dead code elimination, constant folding) |

## Phase 5 Tooling Ecosystem

**Goal:** Make the language usable day to day.

| Status | Item |
|---|---|
| PLANNED | [kai](https://github.com/kaizenium/kai) CLI: `build`/`run`/`clean`/`add`/`remove`/`update` |
| PLANNED | [kai-syntax](https://github.com/kaizenium/kai-syntax): editor syntax highlighting (VSCode, Vim) |
| PLANNED | [kaifmt](https://github.com/kaizenium/kaifmt): code formatter |
| PLANNED | [kaistd](https://github.com/kaizenium/kaistd): minimal standard library (I/O, strings, collections) |
| IDEA | [kaitest](https://github.com/kaizenium/kaitest): test tool |
| IDEA | [kaibench](https://github.com/kaizenium/kaibench): benchmark tool |

## Phase 6 Platform Expansion

**Goal:** Move beyond Linux x86-64.

| Status | Item |
|---|---|
| IDEA | Cross compile: `--target windows-x86_64` |
| IDEA | Cross compile: `--target linux-arm64` |
| IDEA | Cross compile: `--target riscv64` |
| IDEA | macOS support |

## Phase 7 — Developer Experience

**Goal:** IDE-level support and documentation.

| Status | Item |
|---|---|
| IDEA | [kailsp](https://github.com/kaizenium/kailsp): Language Server (autocomplete, go-to-definition, diagnostics) |
| IDEA | [kaidoc](https://github.com/kaizenium/kaidoc): documentation generator |
| IDEA | Package ecosystem (`shared/` community repository) |

## Phase 8 — Self-Host

**Goal:** The Kai compiler is written in Kai.

| Status | Item |
|---|---|
| IDEA | [kai-bootstrap](https://github.com/kaizenium/kai-bootstrap): bootstrap compiler |
| IDEA | Port the existing compiler to Kai |
| IDEA | Define a stable ABI |

---

## Where Are We Now?

The project is in **Phase 0** - the language specification is under active work. The move to Phase 1 (Lexer and Parser) will begin once the spec has stabilized enough to build against.

## Want to Contribute?

At this stage, the most valuable contribution is discussion and feedback on the [about-kai](https://github.com/kaizenium/about-kai) specification. A separate call for code contributions will go out once Phase 1 begins.
