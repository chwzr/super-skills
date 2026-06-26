# Super — Contributor Guidelines

Super is a software-development methodology for coding agents, delivered as a
set of composable skills plus the bootstrap that makes an agent use them. It is
a fork of [obra/superpowers](https://github.com/obra/superpowers).

## Philosophy

- **Zero dependencies.** Super is a zero-dependency plugin by design. If a
  change needs an external tool or service, it belongs in its own plugin.
- **Skills are code, not prose.** Skill content shapes agent behavior. Treat
  changes to it with the same care as code: develop and test them with the
  `writing-skills` skill, and pressure-test across multiple sessions before
  relying on them.
- **General over specific.** Core skills should help any project. Skills tied
  to a specific domain, tool, or workflow belong in a standalone plugin.
- **Deliberate terminology.** Language like "your human partner" is
  intentional. Read the existing skills and understand a design decision before
  changing it.

## Contributing

1. Create a branch for your work.
2. Use the `writing-skills` skill when creating or modifying skills.
3. Keep each PR to one focused change; split unrelated changes apart.
4. Test on at least one harness and describe what you observed.
5. Fill in the PR template and describe the problem you solved, not just what
   you changed.

## Multi-harness support

Super targets multiple harnesses (Claude Code, Codex, Cursor, Gemini CLI,
Kimi, OpenCode, Pi, and others). Any skill change must work across the
harnesses we support. A real integration loads the `using-super` bootstrap at
session start — that bootstrap is what makes skills auto-trigger. Without it the
skills sit on disk and never fire.

**Acceptance test for a new harness:** open a clean session and send:

> Let's make a react todo list

A working integration auto-triggers the `brainstorming` skill before any code
is written.

## Tests

Plugin-infrastructure tests live in `tests/` and run via the relevant
`run-*.sh` scripts or `npm test`.
