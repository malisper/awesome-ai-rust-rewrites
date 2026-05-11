# Contributing

Thanks for helping make this list useful. Open a pull request with the entry you want to add, and maintainers will review it.

## What Belongs Here

Good additions should be about rewriting, migrating, porting, or reimplementing an existing codebase in Rust.

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
