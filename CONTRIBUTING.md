# Contributing

Thanks for helping make this list useful. Open a pull request with the entry you want to add, and maintainers will review it.

## What Belongs Here

Good additions should be about rewriting, migrating, porting, or reimplementing an existing codebase in Rust.

Scale and ambition matter. The list focuses on substantial rewrites of established codebases, runtimes, compilers, databases, browsers, package managers, and similarly important infrastructure. An entry should replace a meaningful part of an incumbent system or demonstrate unusual migration scope. A useful but small wrapper, plugin, accelerator, or greenfield alternative is not enough by itself.

Strong entries usually have at least one of:

- test-suite results
- compatibility target
- benchmark data
- migration log
- source and target code links
- detailed toolchain description
- discussion of unsafe code, FFI, or semantic gaps

## What Does Not Belong

Please avoid:

- generic AI coding tools
- generic Rust projects
- small wrappers, plugins, or accelerators that retain the incumbent for core behavior
- early MVPs whose scope is narrow relative to the projects already on the list
- low-detail marketing pages
- "we might rewrite this someday" posts
- projects with no evidence of behavior validation

## Entry Format

Most entries should be one Markdown bullet:

```md
- [Name](https://example.com) - Short description of what was rewritten, what role AI or automated tooling played, and what evidence exists.
```

If the rewrite is large or unusual, include extra links in the PR description: source language, target code, AI/tooling used, validation, benchmarks, or migration write-up.

## Tone

This list is pro-AI and anti-slop. Be concrete about what worked, what failed, and how behavior was verified.
