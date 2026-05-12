# Usage

## Purpose

This document shows how to use `precision-with-low-token-cost` in Codex so responses stay efficient without losing correctness.

## Basic Prompt

```text
Use the precision-with-low-token-cost skill.
```

## Common Prompt Patterns

### 1. General coding work

```text
Use the precision-with-low-token-cost skill. Fix this bug with minimal context loading and concise updates.
```

### 2. Code review

```text
Use the precision-with-low-token-cost skill. Review this change and focus on high-severity findings only.
```

### 3. Small feature work

```text
Use the precision-with-low-token-cost skill. Implement the smallest safe change and keep the explanation brief.
```

### 4. Debugging

```text
Use the precision-with-low-token-cost skill. Investigate the issue step by step, but only read more files if blocked.
```

### 5. Combined with another skill

```text
Use precision-with-low-token-cost and <another-skill>. Keep outputs compact unless detail is required for correctness.
```

## What This Skill Changes

When active, Codex should:

- avoid broad repository scans unless necessary
- avoid restating the prompt
- keep commentary short and information-dense
- summarize command outcomes instead of narrating every step
- keep the final answer focused on result, verification, and risk

## What It Does Not Change

This skill should not make Codex:

- skip tests or verification
- hide uncertainty
- avoid clarifying high-risk ambiguity
- omit important implementation details when they matter

## Best Use Cases

This skill works best for:

- bug fixes
- targeted refactors
- code review
- small to medium feature work
- repository navigation where token efficiency matters

## Weak Use Cases

This skill is less important for:

- open-ended ideation
- architecture exploration
- tasks where the user explicitly wants deep explanation
- large ambiguous projects that need substantial design work first

## Practical Tips

- Pair it with task-specific skills for better results.
- Ask for short answers explicitly if you want even tighter output.
- Ask for a detailed explanation only after the implementation is done.

## Example

```text
Use the precision-with-low-token-cost skill and fix the failing API test. Read only the files you need, avoid long updates, and verify the result.
```
