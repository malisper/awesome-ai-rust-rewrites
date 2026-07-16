# Awesome AI Rust Rewrites [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> Rewriting existing codebases into Rust with AI.

RoboCrab tracks projects pushing the limits of AI-assisted rewrites into Rust.

Join the community: [RoboCrab Discord](https://discord.gg/SSCVHduG9x).

## Contents

- [AI-Assisted Rust Rewrites](#ai-assisted-rust-rewrites)
- [C2Rust And Automated Translation Case Studies](#c2rust-and-automated-translation-case-studies)
- [Adjacent AI Rewrite Case Studies](#adjacent-ai-rewrite-case-studies)
- [Adjacent Rust Reimplementations](#adjacent-rust-reimplementations)
- [Tools](#tools)
- [Research](#research)
- [Programs And Benchmarks](#programs-and-benchmarks)
- [Articles And Talks](#articles-and-talks)
- [Adjacent Lists](#adjacent-lists)

## AI-Assisted Rust Rewrites

- [Bun Zig-to-Rust rewrite](https://github.com/oven-sh/bun/pull/30412) - Bun merged "Rewrite Bun in Rust" on May 14, 2026 from the `claude/phase-a-port` branch, adding a Rust workspace across thousands of files; Bun canary builds are released from every `main` commit via `bun upgrade --canary`.
- [Grit](https://github.com/gitbutlerapp/grit) - GitButler's AI-authored Git reimplementation in Rust, targeting close behavior compatibility with upstream Git by porting and running the Git test suite against `grit-git`.
- [Ladybird's Rust adoption](https://ladybird.org/posts/adopting-rust/) - Browser project adopting Rust with AI assistance, starting with LibJS because it is relatively isolated and has extensive test coverage.
- [pacquet](https://github.com/pnpm/pnpm/tree/main/pacquet) - Official pnpm rewrite in Rust, porting the pnpm CLI from TypeScript to Rust while matching pnpm behavior, flags, defaults, error codes, file formats, and directory layout.
- [pgrust](https://pgrust.com/) - PostgreSQL rewrite in Rust using AI-assisted engineering, with PostgreSQL behavior and compatibility tests as the bar.
- [tsz](https://github.com/mohsen1/tsz) - AI-assisted Rust implementation of a TypeScript checker targeting drop-in `tsc` compatibility, with conformance progress reported against the official TypeScript test suite.

## C2Rust And Automated Translation Case Studies

These are mostly not AI-assisted, but they are useful prior art for automated translation, cleanup, safety work, and compatibility.

- [libbzip2-rs](https://github.com/trifectatechfoundation/libbzip2-rs) - Drop-in compatible Rust implementation of bzip2 created with C2Rust and later used by the `bzip2` crate.
- [libyaml-safer](https://github.com/simonask/libyaml-safer) - Fully safe Rust fork of `unsafe-libyaml`, originally translated from libyaml with C2Rust.
- [rav1d](https://github.com/memorysafety/rav1d) - Fully safe Rust port of the `dav1d` AV1 decoder, created with C2Rust and then refactored toward safer, more idiomatic Rust.
- [rexpat](https://github.com/immunant/rexpat) - Rust port of Expat used as a C2Rust case study.
- [sapp-kms](https://crates.io/crates/sapp-kms) - C2Rust-derived port of sokol's KMS backend, cleaned up but still unsafe.
- [spiro.rlib](https://github.com/MFEK/spiro.rlib) - Fully safe C2Rust-derived port of the `spiro` spline interpolation library.
- [tsuki](https://github.com/ultimaweapon/tsuki) - Fully safe C2Rust-derived port of the Lua interpreter.
- [unsafe-libyaml](https://github.com/dtolnay/unsafe-libyaml) - Mostly direct C2Rust-derived port of libyaml, kept fully unsafe with minor cleanup.
- [zlib-rs](https://github.com/trifectatechfoundation/zlib-rs) - Rust implementation of zlib exposed as both a C dynamic library and a Rust crate.

## Adjacent AI Rewrite Case Studies

These are not all Rust migrations, but they are useful examples of AI-assisted rewrites, long-running agents, compatibility targets, and guardrails.

- [Cloudflare vinext](https://blog.cloudflare.com/vinext/) - AI-written reimplementation of the Next.js API surface on Vite and Cloudflare Workers, with Cloudflare describing the build process, token cost, test suite, and quality gates.
- [Cursor FastRender browser experiment](https://cursor.com/blog/scaling-agents) - Cursor research run where hundreds of agents worked for close to a week on a Rust browser engine experiment, producing over one million lines across 1,000 files.
- [Cursor self-driving codebases](https://cursor.com/blog/self-driving-codebases) - Follow-up post on the agent harness, coordination patterns, and review problems Cursor saw after the browser experiment.
- [Webernetes](https://ngrok.com/blog/i-ported-kubernetes-to-the-browser) - ngrok's LLM-assisted partial port of Kubernetes from Go to TypeScript for browser-based clusters, with manual review and tests comparing behavior against k3s.

## Adjacent Rust Reimplementations

These are not necessarily AI-assisted, but they show large ecosystems replacing existing developer tooling with Rust implementations.

- [Astro 7](https://astro.build/blog/astro-7/) - Astro rewrote its `.astro` compiler in Rust, made its Rust-powered Markdown and MDX pipeline the default, and reports 15-61% faster builds across benchmark sites.
- [Biome](https://biomejs.dev/) - Rust web toolchain for formatting, linting, and code analysis, positioned as a faster alternative to common JavaScript tooling.
- [Deno 2.0](https://deno.com/blog/v2.0) - Rust-based JavaScript and TypeScript runtime with Node.js and npm compatibility, plus built-in formatter, linter, test runner, and task runner.
- [Lightning CSS](https://github.com/parcel-bundler/lightningcss) - Rust CSS parser, transformer, bundler, and minifier used by Parcel and other tools.
- [Next.js Compiler](https://nextjs.org/docs/architecture/nextjs-compiler) - Rust/SWC-based compiler that replaces Babel for individual files and Terser for minification in Next.js.
- [Oxc](https://oxc.rs/) - Rust JavaScript tooling stack covering parser, linter, formatter, transformer, resolver, and minifier.
- [Rolldown](https://rolldown.rs/) - Rust Rollup-compatible bundler used by Vite to replace its previous esbuild/Rollup split.
- [Rspack](https://rspack.rs/blog/announcing-1-0) - Rust Webpack-compatible bundler designed for progressive migration from Webpack.
- [Ruff](https://github.com/astral-sh/ruff) - Rust Python linter and formatter that replaces or consolidates tools such as Flake8, isort, and Black.
- [Rustwright](https://github.com/Skyvern-AI/rustwright) - Alpha Rust reimplementation of Playwright's browser-control engine under Playwright-shaped Python and Node APIs; reports 515 shared parity cases and 1,046 Docker-gate tests, plus local diagnostic speed and client-memory gains, while explicitly saying full behavioral parity is not yet proven.
- [Tailwind CSS v4](https://tailwindcss.com/blog/tailwindcss-v4) - New high-performance Tailwind engine using Rust-powered pieces and Lightning CSS, with substantially faster full and incremental builds.
- [Turbopack](https://nextjs.org/blog/next-13) - Vercel's Rust-based successor to Webpack, introduced through Next.js.
- [Turso](https://github.com/tursodatabase/turso) - Rust rewrite of SQLite evolving into a pluggable database core; its new [Postgres frontend](https://turso.tech/blog/a-new-modern-version-of-postgres-in-rust) compiles Postgres syntax and types to Turso bytecode, targets common-application compatibility rather than 100% PostgreSQL parity, and documents simulation, oracle, fuzz, and formal-method testing.
- [uv](https://github.com/astral-sh/uv) - Rust Python package and project manager designed as a fast replacement for tools such as `pip`, `pip-tools`, `pipx`, `poetry`, and `virtualenv`.

## Tools

- [C2Rust](https://github.com/immunant/c2rust) - C-to-Rust translator and refactoring toolkit for migrating C code to Rust.
- [Corrode](https://github.com/jameysharp/corrode) - Older C-to-Rust translator, useful historical context for deterministic translation.
- [ShiftCodex](https://shiftcodex.com/) - AI code migration platform built around translate, test, fix, and re-run loops.
- [VLTR](https://www.vltr.ai/) - AI-powered C/C++ to Rust migration tool.

## Research

- [C2RustXW](https://arxiv.org/abs/2603.28686) - C-to-Rust translation that combines program analysis, LLM translation, dependency-aware ordering, and execution-based validation.
- [EvoC2Rust](https://arxiv.org/abs/2508.04295) - Skeleton-guided framework for project-level C-to-Rust translation.
- [Rustine](https://arxiv.org/abs/2511.20617) - Repository-level C-to-Rust translation system targeting compilable, idiomatic, safer Rust with test-verified functional equivalence.
- [&inator](https://arxiv.org/abs/2604.17261) - Correct and precise C-to-Rust interface translation.
- [SafeTrans](https://arxiv.org/abs/2505.10708) - LLM-assisted C-to-Rust transpilation with iterative repair.
- [SACTOR](https://arxiv.org/abs/2503.12511) - LLM-driven multi-step C-to-Rust translation using static analysis.
- [RustMap](https://arxiv.org/abs/2503.17741) - Project-scale C-to-Rust migration using program analysis, LLMs, dependency guidance, and test feedback.
- [LLM4C2Rust](https://arxiv.org/abs/2604.15485) - Retrieval-augmented C/C++ to Rust transpilation framework focused on memory safety.

## Programs And Benchmarks

- [DARPA TRACTOR](https://www.darpa.mil/research/programs/translating-all-c-to-rust) - Program aiming to automate translation of legacy C code to Rust using software analysis and machine learning.
- [TRACTOR Benchmarks](https://www.ll.mit.edu/r-d/projects/translating-all-c-rust-tractor-benchmarks) - MIT Lincoln Laboratory benchmarks and evaluation work for DARPA's C-to-Rust translation program.

## Articles And Talks

- [Porting C to Rust for a Fast and Safe AV1 Media Decoder](https://www.memorysafety.org/blog/porting-c-to-rust-for-av1/) - Prossimo write-up on the goals and approach behind `rav1d`.
- [Making the rav1d Video Decoder 1% Faster](https://ohadravid.github.io/posts/2025-05-rav1d-faster/) - Performance case study on a C2Rust-derived port.
- [Translating bzip2 with C2Rust](https://trifectatech.org/blog/translating-bzip2-with-c2rust/) - Trifecta Tech Foundation write-up on translating bzip2 with C2Rust.
- [Rust Is Eating JavaScript](https://leerob.com/rust) - Lee Robinson's evolving survey of Rust replacing JavaScript tooling, updated in 2026 with Turbopack, Rolldown, Oxc, Biome, Rspack, Tailwind CSS v4, Deno, uv, and Ruff.
- [Using GPT-4 to Assist in C to Rust Translation](https://www.galois.com/articles/using-gpt-4-to-assist-in-c-to-rust-translation) - Galois experiment using GPT-4 for behavior-preserving refactoring in C2Rust output.
- [Function Argument Nullability Using an LLM](https://www.galois.com/articles/function-argument-nullability-using-an-llm) - Galois article on augmenting C2Rust migration analysis with an LLM.

## Adjacent Lists

- [Awesome Rust](https://github.com/rust-unofficial/awesome-rust) - Rust code and resources.
- [Awesome Alternatives in Rust](https://github.com/TaKO8Ki/awesome-alternatives-in-rust) - Reimplementations and alternatives written in Rust.
- [Awesome Transpilers](https://github.com/jashkenas/awesome-transpilers) - Transpilers and source-to-source compilers.

## Footnotes

This list is intentionally narrow. It is not a general Rust list, a general AI coding list, or a list of greenfield Rust projects. Scale and ambition matter: entries should replace a meaningful surface of an established system or demonstrate unusual migration scope. Small wrappers, plugins, and accelerators are out of scope even when they are useful and well built.

Good entries should show at least one serious validation signal: test results, compatibility target, benchmark data, migration log, source and target code links, or discussion of unsafe code and semantic gaps.

Contributions are welcome. See [CONTRIBUTING.md](CONTRIBUTING.md).
