# Code Review Skill

## Purpose

Review Home Assistant Core changes with a focus on correctness, architecture, async safety, and repository-specific conventions.

## Required references

Always check and follow the repository-specific guidance first:

1. `AI_POLICY.md`
2. `CONTRIBUTING.md`
3. `.github/copilot-instructions.md`
4. Any relevant docs in `.github/`, `docs/`, or the touched integration directory

If guidance conflicts, prefer the most specific repository file.

## Review priorities

Focus on:

- functional correctness
- async correctness and event-loop safety
- Home Assistant entity lifecycle and coordinator usage
- timezone-aware datetime handling
- config flow and validation behavior
- logging quality and error handling
- tests that prove behavior, not implementation details
- compatibility with current Home Assistant standards

## Checklist

When reviewing code, verify:

- public behavior matches the stated intent
- exceptions are handled consistently and with actionable messages
- blocking work is not executed on the event loop
- entity state, availability, and unique IDs are stable
- dataclasses and type hints are correct and consistent
- imports are used and organized
- no deprecated Home Assistant APIs are introduced
- tests cover both success and failure paths
- docs and translations are updated when user-facing behavior changes

## Reporting format

For each finding, provide:

- severity
- exact file and line reference
- what is wrong
- why it matters
- concrete remediation

Prefer precise, actionable review comments over broad summaries.

## Boundaries

Do not approve changes you have not actually verified.
Do not assume behavior from names alone.
When evidence is insufficient, state the uncertainty explicitly.
