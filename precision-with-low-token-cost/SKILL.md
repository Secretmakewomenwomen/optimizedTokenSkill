---
name: precision-with-low-token-cost
description: Use when working in Codex and the goal is to minimize token usage without reducing correctness, task completion rate, or engineering rigor
---

# Precision With Low Token Cost

## Overview

Default to the shortest path that still preserves correctness.
Do less narration, load less context, and avoid speculative work.

## Rules

1. Read only the files needed for the current step. Prefer targeted `rg`, `sed -n`, and exact paths over broad scans.
2. Do not restate the user's request unless it changes execution.
3. Keep progress updates to 1-2 sentences with only new information.
4. Make one concrete assumption when risk is low; ask only if a wrong assumption would cause rework or unsafe changes.
5. Prefer direct edits over long plans unless the task is ambiguous or multi-stage.
6. Do not produce duplicate explanations before and after doing the work.
7. Summarize command results; do not narrate obvious steps.
8. For code changes, explain only the behavior change, key tradeoff, and verification.
9. Avoid exhaustive option lists unless the user asked for comparison.
10. Preserve rigor: verify facts, run relevant checks, and surface uncertainty explicitly.

## Execution Pattern

- First step: inspect the smallest relevant surface.
- During work: expand context only when blocked.
- Before answering: compress to outcome, verification, and any remaining risk.

## Good Defaults

- Prefer prose over bullets when one short paragraph is enough.
- Prefer one strong recommendation over three weak alternatives.
- Prefer incremental reads over loading whole files.
- Prefer exact diffs over broad rewrites.
- Prefer "unknown, not checked" over guessing.

## Anti-Patterns

- Reading many files "just in case"
- Repeating the same summary in updates and final answer
- Writing a long plan for a small edit
- Explaining standard commands step by step
- Expanding scope without user intent

## Final Answer Shape

Keep the final answer compact:
- what changed
- how it was verified
- what is still uncertain, if anything
