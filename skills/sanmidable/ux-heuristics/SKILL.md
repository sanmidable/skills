---name: ux-heuristics
description: >-
  Heuristic UX evaluation of screens, flows, and product interfaces using
  Nielsen's 10 usability heuristics as the sole scorecard, with Laws of UX as
  non-overlapping diagnostic lenses. Use when the user asks for a UX audit,
  heuristic evaluation, usability review, Nielsen heuristics check, Laws of UX
  review, or says ux-heuristics, heuristic review, usability heuristics, UX
  heuristics, or evaluate this flow against heuristics.
author: sanmidable
source: https://github.com/sanmidable/ux-heuristics
homepage: https://github.com/sanmidable/ux-heuristics/blob/main/SKILL.md
---

# UX heuristic evaluation

Expert heuristic evaluation of an interface. **One job:** find usability problems, score them against Nielsen's 10, and prioritize fixes. Do not redesign, rewrite code, or expand into visual polish / a11y deep-dives unless the user also asks.

## Ownership (no double-counting)

| Layer | Role | File |
| --- | --- | --- |
| **Nielsen's 10** | Only scored rubric. Every finding maps to ≥1 heuristic. | [heuristics.md](heuristics.md) |
| **Laws of UX** | Diagnostic lenses for *mechanism* or dimensions Nielsen does not score (target geometry, latency budgets, choice count, peak/end memory, Gestalt grouping). Never a second scorecard. | [laws.md](laws.md) |

**Anti-overlap rules:**

1. If an issue is fully explained by a Nielsen heuristic, report it **once** under that heuristic. You may cite a Law in the **Why** cell as mechanism — do not create a second finding for the Law.
2. Create a Law-only finding **only** when [laws.md](laws.md) marks it as *Nielsen-gap* and no heuristic already covers the evidence.
3. Do not invent Shneiderman or Tog scorecards. Unique scraps from those traditions live in [laws.md](laws.md) under Nielsen-gap laws (or are omitted as duplicates of Nielsen).
4. Accessibility engineering (WCAG, ARIA, focus traps) is out of scope — note the gap and point to an a11y skill; do not recreate those rules here.

## Workflow

### 1. Resolve scope and mode

State the screen, flow, or feature under review. Narrow oversized requests to the highest-traffic complete task path and say so.

| Mode | When | Coverage | Finding cap |
| --- | --- | --- | --- |
| `quick` | Default if unspecified | Primary path + critical states (empty, error, loading if present) | 5 |
| `full` | User asks for full / thorough / complete | Entire requested scope + edge states | 12 |

### 2. Recon

Identify product type, primary user goal, platform conventions, and whether you can inspect source, a running UI, or both. Prefer evidence from the real task path over speculative critique.

### 3. Walk the task, then score heuristics

1. Complete (or simulate) the primary user task.
2. Load [heuristics.md](heuristics.md). Score **all 10** heuristics `0–4` or `n/a` (see scale below).
3. Load [laws.md](laws.md) only to explain mechanisms or catch Nielsen-gap issues.
4. Consolidate: one root cause → one finding. List every confirmed location in that row.

### 4. Severity (shared)

- `CRITICAL` — blocks the task, data loss, or irreversible wrong action with no clear escape
- `HIGH` — major friction, frequent errors, or severe trust/status confusion
- `MEDIUM` — meaningful inefficiency, inconsistency, or recoverable confusion
- `LOW` — minor annoyance; include only in `full` mode

Within a severity, rank by reach (shared component / every session) over one-off screens.

### 5. Heuristic score scale

| Score | Meaning |
| --- | --- |
| `4` | Strong support; no meaningful issues in scope |
| `3` | Mostly solid; minor gaps |
| `2` | Mixed; issues affect the primary path |
| `1` | Weak; frequent or severe violations |
| `0` | Absent / hostile to the heuristic |
| `n/a` | Heuristic does not apply to this scope (state why) |

### 6. Read-only by default

Do not edit product code unless the user asks to implement findings. When implementing, keep the report as the change scope.

## Output format

```markdown
# UX heuristic review: [scope]

**Mode:** quick | full
**Primary task:** …

## Scorecard

| # | Heuristic | Score | Notes |
| --- | --- | --- | --- |
| 1 | Visibility of system status | 0–4 / n/a | … |
| 2 | Match between system and real world | | |
| 3 | User control and freedom | | |
| 4 | Consistency and standards | | |
| 5 | Error prevention | | |
| 6 | Recognition rather than recall | | |
| 7 | Flexibility and efficiency of use | | |
| 8 | Aesthetic and minimalist design | | |
| 9 | Help users recognize, diagnose, recover from errors | | |
| 10 | Help and documentation | | |

## Findings

| Sev | Heuristic | Location | Issue | Why | Fix |
| --- | --- | --- | --- | --- | --- |
| HIGH | H5 | path or screen | … | optional Law cite | concrete next step |

## Nielsen-gap law notes
(Only if a Law applies and no heuristic already owns it; else omit this section.)

## Strengths
- 2–3 things that already support the heuristics well

## Out of scope / not verified
- …
```

## Common mistakes

- Scoring aesthetics or brand taste under H8 when the real issue is clutter competing with the task (H8 is about *signal vs noise*, not beauty contests)
- Filing the same bug under H5 and H9 — pick prevention (H5) vs recovery messaging (H9)
- Treating Jakob's Law / Occam's Razor / Miller's Law as separate findings when H2, H4, H6, or H8 already cover them
- Padding to the finding cap
- Claiming holistic coverage for surfaces you did not inspect
