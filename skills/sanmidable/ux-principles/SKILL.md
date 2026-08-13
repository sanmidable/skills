---name: ux-principles
description: >-
  UX principles review using Laws of UX and classic interaction principles
  (progressive disclosure, affordances, mapping, defaults, forgiveness, direct
  manipulation, perceived performance). Use when the user asks for a principles
  pass, Laws of UX review, Fitts/Hick/Doherty/Peak-End check, progressive
  disclosure audit, or says ux-principles, laws of ux, or apply UX principles.
  For Nielsen heuristic scoring, use ux-heuristics instead.
author: sanmidable
source: https://github.com/sanmidable/ux-principles
homepage: https://github.com/sanmidable/ux-principles/blob/main/SKILL.md
---

# UX principles review

Apply psychology and interaction principles to a screen or flow. **One job:** explain and prioritize principle-level guidance. Do not run a Nielsen scorecard here — that belongs to `ux-heuristics`. Do not redesign or edit code unless asked.

## Ownership (no double-counting)

| Skill | Owns |
| --- | --- |
| **`ux-heuristics`** | Nielsen's 10 usability heuristics (usability problem scorecard) |
| **`ux-principles`** (this skill) | Laws of UX + classic principles below |

**Anti-overlap rules:**

1. If the issue is fully a Nielsen violation (status, errors, consistency, recall, etc.), say so and defer the finding to `ux-heuristics` — do not re-score it here.
2. Jakob's Law, Mental Model, Miller's Law, Chunking, Working Memory, general Cognitive Load, Occam's Razor, and Paradox of the Active User are **folded into Nielsen** — mention as mechanism only, never as standalone principle findings.
3. Accessibility sizing/contrast/ARIA → a11y skill. Motion craft → animation skills.
4. One root cause → one finding. Cite the primary principle; mention secondary effects in **Why**.

## Rubrics

| File | Contents |
| --- | --- |
| [laws.md](laws.md) | Fitts, Hick, Doherty, Peak-End, Serial Position, Von Restorff, Zeigarnik, Goal-Gradient, Tesler, Postel, Gestalt, Aesthetic-Usability (caution) |
| [principles.md](principles.md) | Progressive disclosure, affordances & signifiers, natural mapping, smart defaults, forgiveness, direct manipulation, perceived performance |

## Workflow

### 1. Resolve scope and mode

| Mode | Coverage | Finding cap |
| --- | --- | --- |
| `quick` | Primary path; HIGH/MEDIUM only | 5 |
| `full` | Full requested scope + edge states | 12 |

Default `quick`. State the screen/flow and primary task.

### 2. Walk the task

Complete or simulate the primary path. Prefer evidence over speculation.

### 3. Apply laws, then classic principles

1. Load [laws.md](laws.md) — check each applicable law.
2. Load [principles.md](principles.md) — check each classic principle.
3. Skip folded-into-Nielsen items as standalone findings.
4. Consolidate duplicates.

### 4. Severity

- `CRITICAL` — blocks task, data loss, or hostile peak/end with no escape
- `HIGH` — major friction from choice overload, unhittable targets, missing progress near goals, brittle input, etc.
- `MEDIUM` — meaningful inefficiency or confused grouping/disclosure
- `LOW` — polish; `full` mode only

### 5. Read-only by default

Do not edit product code unless asked to implement.

## Output format

```markdown
# UX principles review: [scope]

**Mode:** quick | full
**Primary task:** …

## Principles hit

| Principle | Status | Notes |
| --- | --- | --- |
| Fitts's Law | ok / issue / n/a | … |
| … | | |

(Include only principles you actually assessed.)

## Findings

| Sev | Principle | Location | Issue | Why | Fix |
| --- | --- | --- | --- | --- | --- |
| HIGH | Hick's Law | … | … | … | … |

## Defer to ux-heuristics
- (Nielsen-owned issues noticed but not scored here)

## Strengths
- 2–3 principle-aligned things that already work

## Out of scope / not verified
- …
```

## Common mistakes

- Re-running a full Nielsen audit inside this skill
- Treating Aesthetic-Usability Effect as a positive score
- Filing Gestalt clutter as H8 *and* as a principle finding — pick one owner (`ux-heuristics` H8 vs Gestalt when grouping relationships are wrong)
- Padding to the finding cap
