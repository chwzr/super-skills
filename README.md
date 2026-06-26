# Super

Super is a complete software development methodology for your coding agents, built on top of a set of composable skills and some initial instructions that make sure your agent uses them.

> Super is a rebranded fork of [obra/superpowers](https://github.com/obra/superpowers).

## Quickstart

Give your agent Super: [Claude Code](#claude-code), [Antigravity](#antigravity), [Codex App](#codex-app), [Codex CLI](#codex-cli), [Cursor](#cursor), [Factory Droid](#factory-droid), [Gemini CLI](#gemini-cli), [GitHub Copilot CLI](#github-copilot-cli), [Kimi Code](#kimi-code), [OpenCode](#opencode), [Pi](#pi).

## How it works

It starts from the moment you fire up your coding agent. As soon as it sees that you're building something, it *doesn't* just jump into trying to write code. Instead, it steps back and asks you what you're really trying to do. 

Once it's teased a spec out of the conversation, it shows it to you in chunks short enough to actually read and digest. 

After you've signed off on the design, your agent puts together an implementation plan that's clear enough for an enthusiastic junior engineer with poor taste, no judgement, no project context, and an aversion to testing to follow. It emphasizes true red/green TDD, YAGNI (You Aren't Gonna Need It), and DRY. 

Next up, once you say "go", it launches a *subagent-driven-development* process, having agents work through each engineering task, inspecting and reviewing their work, and continuing forward. It's not uncommon for your agent to work autonomously for a couple hours at a time without deviating from the plan you put together.

There's a bunch more to it, but that's the core of the system. And because the skills trigger automatically, you don't need to do anything special. Your coding agent just has Super.

## Installation

Installation differs by harness. If you use more than one, install Super separately for each one.

### Claude Code

Install Super from the Super marketplace:

- Register the marketplace:

  ```bash
  /plugin marketplace add chwzr/super-marketplace
  ```

- Install the plugin from this marketplace:

  ```bash
  /plugin install super@super-marketplace
  ```

### Antigravity

Install Super as a plugin from this repository:

```bash
agy plugin install https://github.com/chwzr/super-skills
```

Antigravity runs the plugin's session-start hook, so Super is active from
the first message. Reinstall with the same command to update.

### Codex App

Super is available via the [official Codex plugin marketplace](https://github.com/openai/plugins).

- In the Codex app, click on Plugins in the sidebar.
- You should see `Super` in the Coding section.
- Click the `+` next to Super and follow the prompts.

### Codex CLI

Super is available via the [official Codex plugin marketplace](https://github.com/openai/plugins).

- Open the plugin search interface:

  ```bash
  /plugins
  ```

- Search for Super:

  ```bash
  super
  ```

- Select `Install Plugin`.

### Cursor

- In Cursor Agent chat, install from marketplace:

  ```text
  /add-plugin super
  ```

- Or search for "super" in the plugin marketplace.

### Factory Droid

- Register the marketplace:

  ```bash
  droid plugin marketplace add https://github.com/chwzr/super-skills
  ```

- Install the plugin:

  ```bash
  droid plugin install super@super
  ```

### Gemini CLI

- Install the extension:

  ```bash
  gemini extensions install https://github.com/chwzr/super-skills
  ```

- Update later:

  ```bash
  gemini extensions update super
  ```

### GitHub Copilot CLI

- Register the marketplace:

  ```bash
  copilot plugin marketplace add chwzr/super-marketplace
  ```

- Install the plugin:

  ```bash
  copilot plugin install super@super-marketplace
  ```

### Kimi Code

Super is available in Kimi Code's plugin marketplace.

- Open Kimi Code's plugin manager:

  ```text
  /plugins
  ```

- Go to `Marketplace` > `Super` and install it.

- Or install directly from this repository:

  ```text
  /plugins install https://github.com/chwzr/super-skills
  ```

- Detailed docs: [docs/README.kimi.md](docs/README.kimi.md)

### OpenCode

OpenCode uses its own plugin install; install Super separately even if you
already use it in another harness.

- Tell OpenCode:

  ```
  Fetch and follow instructions from https://raw.githubusercontent.com/chwzr/super-skills/refs/heads/main/.opencode/INSTALL.md
  ```

- Detailed docs: [docs/README.opencode.md](docs/README.opencode.md)

### Pi

Install Super as a Pi package from this repository:

```bash
pi install git:github.com/chwzr/super-skills
```

For local development, run Pi with this checkout loaded as a temporary package:

```bash
pi -e /path/to/super
```

The Pi package loads the Super skills and a small extension that injects the `using-super` bootstrap at session startup and again after compaction. Pi has native skills, so no compatibility `Skill` tool is required. Subagent and task-list tools remain optional Pi companion packages.

## The Basic Workflow

1. **brainstorming** - Activates before writing code. Refines rough ideas through questions, explores alternatives, presents design in sections for validation. Saves design document.

2. **using-git-worktrees** - Activates after design approval. Creates isolated workspace on new branch, runs project setup, verifies clean test baseline.

3. **writing-plans** - Activates with approved design. Breaks work into bite-sized tasks (2-5 minutes each). Every task has exact file paths, complete code, verification steps.

4. **subagent-driven-development** or **executing-plans** - Activates with plan. Dispatches fresh subagent per task with two-stage review (spec compliance, then code quality), or executes in batches with human checkpoints.

5. **test-driven-development** - Activates during implementation. Enforces RED-GREEN-REFACTOR: write failing test, watch it fail, write minimal code, watch it pass, commit. Deletes code written before tests.

6. **requesting-code-review** - Activates between tasks. Reviews against plan, reports issues by severity. Critical issues block progress.

7. **finishing-a-development-branch** - Activates when tasks complete. Verifies tests, presents options (merge/PR/keep/discard), cleans up worktree.

**The agent checks for relevant skills before any task.** Mandatory workflows, not suggestions.

## What's Inside

### Skills Library

**Testing**
- **test-driven-development** - RED-GREEN-REFACTOR cycle (includes testing anti-patterns reference)

**Debugging**
- **systematic-debugging** - 4-phase root cause process (includes root-cause-tracing, defense-in-depth, condition-based-waiting techniques)
- **verification-before-completion** - Ensure it's actually fixed

**Collaboration** 
- **brainstorming** - Socratic design refinement
- **writing-plans** - Detailed implementation plans
- **executing-plans** - Batch execution with checkpoints
- **dispatching-parallel-agents** - Concurrent subagent workflows
- **requesting-code-review** - Pre-review checklist
- **receiving-code-review** - Responding to feedback
- **using-git-worktrees** - Parallel development branches
- **finishing-a-development-branch** - Merge/PR decision workflow
- **subagent-driven-development** - Fast iteration with two-stage review (spec compliance, then code quality)

**Meta**
- **writing-skills** - Create new skills following best practices (includes testing methodology)
- **using-super** - Introduction to the skills system

## Philosophy

- **Test-Driven Development** - Write tests first, always
- **Systematic over ad-hoc** - Process over guessing
- **Complexity reduction** - Simplicity as primary goal
- **Evidence over claims** - Verify before declaring success

## Contributing

Any update to a skill must work across all of the coding agents we support.

1. Create a branch for your work.
2. Follow the `writing-skills` skill for creating and testing new and modified skills.
3. Submit a PR and fill in the pull request template.

Plugin-infrastructure tests live in `tests/` and run via the relevant `run-*.sh` scripts or `npm test`. See `skills/writing-skills/SKILL.md` and `CLAUDE.md` for the complete guide.

## Updating

Super updates are somewhat coding-agent dependent, but are often automatic.

## License

MIT License - see LICENSE file for details

## Visual companion telemetry

Because skills and plugins don't provide any feedback to maintainers, we have no easy way to know how many people use Super. By default, brainstorming's optional visual companion loads a small logo from `https://telemetry.flxkpe.io`, with the version of Super in use appended to the request. It does not include any details about your project, prompt, or coding agent — no clicks, no content. It only gives a rough sense of how many people use Super and which version. It's 100% optional. To disable it, set the environment variable `SUPER_DISABLE_TELEMETRY` to any true value. Super also honors Claude Code's `DISABLE_TELEMETRY` and `CLAUDE_CODE_DISABLE_NONESSENTIAL_TRAFFIC` opt-outs.

## Community

- **Issues**: https://github.com/chwzr/super-skills/issues
