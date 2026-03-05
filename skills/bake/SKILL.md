---
name: bake-claude-md-files
description: >
  Converts CLAUDE.md rules into automated checks (eslint, phpstan, pint, CI, etc.),
  removes the automated rules from CLAUDE.md, and verifies everything passes.
  Frees up agent context by replacing prose with tooling.
user-invocable: true
disable-model-invocation: true
---

Read all CLAUDE.md files in the project, along with the existing tool configurations (eslint, phpstan, pint, package.json scripts, lefthook, git hooks, GitLab CI or GitHub Actions and everything else relevant).

Identify rules in the CLAUDE.md files that can be turned into automated checks. Every rule we can remove is context freed up for the agent.

Then implement the automated checks, remove the corresponding lines from the CLAUDE.md files, and verify everything passes.

## Implementation priority

1. **Discover existing tooling first** - inventory linters, test frameworks, static analyzers, CI pipelines, and git hooks before implementing anything
2. **Use native capabilities** - express checks through tools already in the project:
   - Pest arch tests for structural rules (namespaces, inheritance, forbidden calls)
   - PHPStan/Rector rules for static analysis and automated refactoring
   - Pint/Duster/ESLint configs for style
   - Lefthook for git hook orchestration
   - CI steps for integration checks
3. **Custom scripts only as last resort** - only when no existing tool can express the check
4. **Wire into existing runners** - new checks must run via existing test/lint commands, not new entrypoints
