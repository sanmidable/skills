# Laws of UX (diagnostic lenses)

Compiled from the [Laws of UX](https://lawsofux.com/) tradition (Jon Yablonski et al.). **Not a second scorecard.**

Use a law in one of two ways:

| Tag | Meaning | How to report |
| --- | --- | --- |
| **Mechanism** | Explains *why* a Nielsen finding hurts | Cite in the finding's **Why** cell only |
| **Nielsen-gap** | Dimension Nielsen does not score directly | Own finding allowed; still prefer mapping to a heuristic if one fits |

If a law is listed under **Folded into Nielsen (do not file separately)**, never create a Law-only finding.

---

## Folded into Nielsen (do not file separately)

| Law / concept | Use instead |
| --- | --- |
| Jakob's Law | H2 / H4 |
| Mental Model | H2 |
| Miller's Law | H6 |
| Chunking | H6 |
| Working Memory | H6 |
| Cognitive Load (general) | H6 (and H8 when clutter is the cause) |
| Occam's Razor | H8 |
| Paradox of the Active User | Informs H10 posture; not a finding type |
| Cognitive Bias (umbrella) | Too broad — name the specific bias/law or heuristic |

---

## Nielsen-gap laws (may own a finding)

Only when evidence is clear and no heuristic already owns the issue.

### Fitts's Law — target acquisition

Time to acquire a target grows with distance and shrinks with size.

**Look for:** Tiny click/tap targets; primary actions far from the pointer's likely position; nested hit areas; toast actions too small.

**Typical heuristic neighbor:** Often co-occurs with a11y hit-target issues — if the product has an a11y skill, defer sizing standards there and only note Fitts here when reviewing pure pointing efficiency.

### Hick's Law / Choice overload — decision time

Decision time rises with number and complexity of choices.

**Look for:** Long undifferentiated action lists; expose-everything nav; settings walls with no progressive disclosure or defaults.

**Neighbor:** H7/H8 — prefer those if the issue is "experts need speed" or "noise hides signal." Use Hick when the **count/complexity of simultaneous choices** is the measurable problem.

### Doherty Threshold — interaction pace

Keep system response under ~400ms where possible so neither user nor system waits on the other; for longer, show progress (ties to H1).

**Look for:** UI that feels idle with no feedback past ~0.4s; blocking the thread with no status; optimistic UI missing.

**Neighbor:** H1 owns feedback; Doherty-gap finding is for **latency budget** when status is fine but wait is still too long for the action type.

### Peak-End Rule — remembered experience

People judge an experience mainly by its peak (best/worst) and its end.

**Look for:** Painful last step (paywall surprise, forced rating); error-prone checkout finale; no clear success ending after hard work.

**Neighbor:** Not covered cleanly by a single heuristic — allowed as Nielsen-gap when the *memory structure* of the journey is the issue.

### Serial Position Effect — first and last items

People recall first and last items in a series best.

**Look for:** Critical actions buried mid-list; destructive items placed where habit-clicks land; onboarding that hides the key action in the middle.

### Von Restorff (Isolation) Effect — distinct items remembered

Among similar items, the distinct one is remembered (and draws attention).

**Look for:** Primary CTA not visually distinct; or the wrong element (ads, secondary) is the most distinct.

**Neighbor:** H8 if the issue is clutter; Von Restorff when **relative distinctiveness** among peers is wrong.

### Zeigarnik Effect — incomplete tasks stick

Uncompleted tasks occupy memory more than completed ones.

**Look for:** Missing progress persistence; no resume; checklists that vanish; unclear "you're done."

**Neighbor:** H1 for live status; Zeigarnik when **resume / incomplete-task memory** is the gap.

### Goal-Gradient Effect — acceleration near the goal

Motivation rises as people approach a goal.

**Look for:** Progress indicators that don't move early; unclear distance-to-done; false progress.

**Neighbor:** H1 for presence of progress; Goal-Gradient when progress *shape* demotivates.

### Tesler's Law — conservation of complexity

Every process has irreducible complexity; someone must absorb it (user or system/designer).

**Look for:** Complexity dumped on users that the system could absorb (manual formatting, raw IDs, repeated entry).

**Neighbor:** H6/H7 — prefer those; Tesler when the product decision is "who carries complexity."

### Postel's Law (Robustness Principle) — accept liberally, emit conservatively

Be liberal in what you accept, conservative in what you send.

**Look for:** Brittle input (rejecting spaces, punctuation, pasted values); pedantic validation; intolerant parsers.

**Neighbor:** H5 when prevention is over-strict; Postel when **tolerance of messy real-world input** is the point.

### Gestalt grouping — Proximity, Similarity, Common Region, Uniform Connectedness, Prägnanz

People group by nearness, likeness, shared region, visible connection; and simplify ambiguous forms.

**Look for:** Related controls spaced apart; unrelated items grouped; weak grouping of form fields; lines/cards that imply false relationships.

**Neighbor:** H4 if inconsistent patterns; Gestalt-gap when **perceptual grouping** is wrong despite consistent components.

### Aesthetic-Usability Effect — caution, not a score

Attractive UI is often *perceived* as more usable — which can hide real usability debt.

**Use:** In **Out of scope / not verified** or Strengths caveats — never as a scored win. Do not congratulate beauty in the scorecard.

### Flow / Selective Attention — optional notes

- **Flow:** Deep focus state — flag only when interruptions (modals, toasts, layout shift) break a concentration task.
- **Selective Attention:** Users miss UI outside their goal path — supports hierarchy findings under H8, not a separate score.

### Pareto Principle — prioritization only

80/20 for *what to fix first* — use when ranking findings, never as a usability violation.

### Parkinson's Law — usually skip

Work expands to fill time — rarely an interface finding; ignore unless the product literally invents busywork UI.

---

## Shneiderman / Tog (what we keep vs drop)

To avoid a third overlapping checklist:

| Idea | Treatment |
| --- | --- |
| Shneiderman: consistency, feedback, reversal, error prevention, memory load | Already Nielsen H1–H6 — **drop** |
| Shneiderman: dialog closure | Map to H1 (status) + Peak-End / clear completion — no separate score |
| Shneiderman: universal usability | Out of scope → a11y skill |
| Shneiderman: direct manipulation | Note under H2/H3 when users edit through visible objects vs opaque commands |
| Tog: Fitts, latency, defaults, explorable interfaces | Covered by Fitts, Doherty, H3/H5, H7 |
| Tog: color blindness, readability | Out of scope → a11y / typography skills |
