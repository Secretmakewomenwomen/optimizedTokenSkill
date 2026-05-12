# precision-with-low-token-cost

A Codex skill for reducing token usage without sacrificing precision, task completion, or engineering rigor.

## What It Does

This skill helps Codex stay concise without becoming shallow.

It pushes the model to:

- read only the smallest relevant context
- avoid repeating the user's request
- keep progress updates short
- prefer direct execution over long planning for small tasks
- preserve verification and explicit uncertainty

## Who It Is For

Use this skill if you want Codex to:

- spend fewer tokens during coding tasks
- avoid loading large amounts of context too early
- reduce verbose intermediate updates
- keep final answers compact and actionable

## Skill File

The core skill lives in [SKILL.md](./SKILL.md).

## Installation

Copy this folder into your Codex skills directory:

```bash
cp -R precision-with-low-token-cost ~/.agents/skills/
```

If your setup uses a different skills path, place the folder there instead.

## Activation

Reference the skill by name in your prompt:

```text
Use the precision-with-low-token-cost skill.
```

You can also combine it with a domain skill when needed, for example:

```text
Use precision-with-low-token-cost and bpi-frontend-expert.
```

## Expected Behavior

With this skill active, Codex should generally:

1. inspect the smallest relevant surface first
2. expand context only when blocked
3. avoid duplicate summaries
4. report outcome, verification, and remaining risk only

## Limits

This skill is not meant to trade away rigor for brevity.

It should not be used as a reason to:

- skip validation
- guess when uncertainty matters
- hide risks
- avoid asking necessary clarification questions

## Usage Guide

See [USAGE.md](./USAGE.md) for examples and prompt patterns.
