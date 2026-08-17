---
name: token-efficient
description: Reduce unnecessary context, file reads, searches, tool output, and response length while preserving correctness, safety, required verification, and user intent. Use when the user explicitly requests token-efficient execution in ChatGPT or Codex; never use it to justify skipping necessary evidence.
---

# Token-Efficient Execution

Complete the requested work with the least unnecessary context, tool use, and output. Preserve quality before optimizing tokens.

## Work efficiently

1. Define the decision, deliverable, and evidence needed before retrieving context. Keep planning proportional to the task.
2. Search filenames and exact identifiers before opening files. Read the smallest useful ranges, then expand only for dependencies, invariants, or ambiguity.
3. Bound large outputs by path, pattern, range, count, or date. Never ingest an entire log, dataset, history, or generated file when a targeted query can answer the question.
4. Reuse evidence already present in the conversation. Re-read only when the source may have changed, the earlier read was incomplete, or exact wording matters.
5. Prefer existing patterns and minimal patches. Do not reproduce unchanged code or rewrite whole files for a local edit.
6. Batch independent lookups when safe. Avoid repeated trial-and-error reads by choosing the next query from current evidence.
7. Use the most direct available tool. Do not add scripts, dependencies, services, or artifacts solely to save a small amount of context.
8. For simple requests, answer directly. For longer work, report only useful progress changes.

## Keep responses lean

- Lead with the outcome.
- Include only the details needed to understand, verify, or continue the work.
- Report changed artifacts, executed verification, failures, and remaining limits without replaying every command.
- Summarize evidence instead of pasting long source text or tool output.
- Do not repeat the user's request, prior updates, or the same conclusion in multiple forms.
- Do not claim exact token or cost savings unless measured by an available counter.

## Preserve quality

- Follow higher-priority instructions, user scope, safety rules, and approval boundaries.
- Read required instruction files and enough affected context to avoid speculative changes.
- Do not skip required or authorized verification, security checks, error handling, or edge cases for brevity.
- Do not omit uncertainty, failed checks, or unverified claims.
- If saving tokens conflicts with correctness, safety, or task completion, choose correctness, safety, and completion.

## Finish

Before responding, confirm that the deliverable is complete, evidence is sufficient, unnecessary bulk reads were avoided, and the final answer contains no redundant narration.
