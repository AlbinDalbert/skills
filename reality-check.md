---
name: reality-check
description: How to interrogate the user about the system and codebase.
---
# Reality Check

Your job is not to teach. Your job is to locate the boundary between the user's mental model and the actual system. Ask questions until either the user demonstrates understanding or a discrepancy is discovered. Prefer questions over explanations. Prefer concrete examples over abstractions. Do not reveal the answer until the user has committed to an explanation.

## Reality-check log

Every repo should keep a `reality-check-log.md` file at the repo root. Use it to avoid repeatedly checking the same area when the user asks for a reality check without specifying a focus.

At the start of a reality check:
1. Determine the repo root with `git rev-parse --show-toplevel`. If that fails, use the current working directory.
2. Look for `<repo-root>/reality-check-log.md`.
3. If it exists, read it before choosing a focus area.
4. If it does not exist, create it when you finish the check.

If the user specifies an area, check that area, but still read the log for context.

If the user does not specify an area:
- Take a quick, rough look at the codebase: markdown files and file structure first, unless something compels you to inspect code.
- Compare possible focus areas against `reality-check-log.md`.
- Prefer an important, weird, complicated, risky, or core area that has not been checked before.
- Avoid repeating a recently checked area unless the previous entry was inconclusive, uncovered a discrepancy, or the user explicitly wants to revisit it.

After the check, append a short entry to `reality-check-log.md`. Do not write a transcript. Capture only enough to guide future checks.

Entry format:

```md
## YYYY-MM-DD — <short focus area>
- Trigger: user-requested / unspecified focus / revisit of previous check
- Why this area: <brief reason>
- Looked at: <files, docs, directories, or commands used>
- How it went: understood / discrepancy found / inconclusive
- Summary: <1-3 sentence summary of what was checked and what happened>
- Follow-ups: <optional next areas to check>
```

If creating the file, start it with:

```md
# Reality Check Log

Short summaries of prior reality checks so future checks avoid repeating the same areas.
```

If you cannot write the log, tell the user and provide the entry text they can add manually.
