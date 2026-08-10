# Nielsen's 10 usability heuristics

Sole scorecard for this skill. Source tradition: Jakob Nielsen / NN/g (heuristics refined 1994; definitions stable since). These are **rules of thumb**, not WCAG.

For each heuristic: definition → what good looks like → probe questions → common failures.

---

## H1 — Visibility of system status

**Definition:** Keep users informed about what is going on, through timely feedback.

**Good:** Loading/progress for waits; confirmation of accepted actions; clear current location/selection; live status for long jobs.

**Probes:**
- After every primary action, does the UI acknowledge within ~0.1s (instant) or show progress for longer work?
- Can the user tell where they are (nav, step, selection)?
- Are background processes (sync, save, generate) visible?

**Failures:** Silent saves; spinners with no context; no selection state; stale data that looks live.

---

## H2 — Match between system and the real world

**Definition:** Speak the users' language — words, concepts, and conventions familiar to them. Information follows real-world order.

**Good:** Domain language users already use; natural reading order; metaphors that match the task (not internal eng jargon).

**Probes:**
- Would a first-time user in this domain understand every critical label?
- Are dates, units, and steps ordered the way people think about the task?
- Any leaked schema names, enums, or API errors in the UI?

**Failures:** "Submit payload"; cryptic codes as primary UI; wizard order that fights the mental model.

*Mechanism overlap (do not double-count):* Jakob's Law, Mental Model — cite under H2/H4, not as separate Law findings.

---

## H3 — User control and freedom

**Definition:** Users often choose system functions by mistake and need a clear "emergency exit." Support undo, redo, cancel, and leaving unwanted states.

**Good:** Cancel/close on overlays; back without data loss where expected; undo for destructive or bulk actions; easy logout / exit from modes.

**Probes:**
- Can the user abort mid-flow without feeling trapped?
- Is there undo or a confirmed path back after risky actions?
- Do modes (drawing, selecting, editing) have an obvious way out?

**Failures:** Modal dead-ends; no cancel on multi-step forms; irreversible delete with weak confirm; gesture-only exits.

---

## H4 — Consistency and standards

**Definition:** Users should not wonder whether different words, situations, or actions mean the same thing. Follow platform and product conventions.

**Good:** Same action → same label/placement; platform patterns (back, share, settings); consistent components for the same job.

**Probes:**
- Do identical actions reuse the same control and copy?
- Any custom pattern where a standard platform pattern exists?
- Internal inconsistency across sibling screens?

**Failures:** "Save" vs "Apply" vs "Done" for the same effect; reinvented nav; mixed date formats.

*Mechanism overlap:* Jakob's Law — report under H4/H2 only.

---

## H5 — Error prevention

**Definition:** Better than good error messages is a design that prevents problems. Eliminate error-prone conditions or check and confirm before commit.

**Good:** Constraints (pickers over free-text where valid set is known); inline validation before submit; confirm destructive actions; disable impossible actions with explanation when useful.

**Probes:**
- Can the user enter invalid states that the system already knows are invalid?
- Are destructive actions confirmed with enough context (what will be lost)?
- Are defaults safe?

**Failures:** Easy mass-delete; ambiguous units; submit enabled with known-invalid forms; no confirmation on irreversible moves.

---

## H6 — Recognition rather than recall

**Definition:** Minimize memory load by making objects, actions, and options visible or easily retrievable. The user should not have to remember information from one part of the dialog to another.

**Good:** Visible options; recent items; persistent context; inline hints; breadcrumbs; previews.

**Probes:**
- Must the user remember codes, IDs, or prior-step values without on-screen support?
- Are actions discoverable without memorizing gestures/shortcuts?
- Is needed context available at decision time?

**Failures:** Multi-step wizards that hide earlier answers; icon-only toolbars with no tooltips; forcing re-entry of known data.

*Mechanism overlap:* Miller's Law, Chunking, Working Memory, Cognitive Load — cite under H6, not as separate findings.

---

## H7 — Flexibility and efficiency of use

**Definition:** Accelerators — unseen by novices — speed up experts. Allow users to tailor frequent actions.

**Good:** Shortcuts, bulk actions, defaults from history, saved views, personalization that does not block first use.

**Probes:**
- Can frequent users go faster without hurting first-time clarity?
- Are there power paths for repetitive work (multi-select, templates)?
- Do accelerators conflict with accessibility or platform norms?

**Failures:** Only novice-paced wizards for daily tasks; hidden power features with no progressive disclosure; customization that is required before use.

---

## H8 — Aesthetic and minimalist design

**Definition:** Interfaces should not contain information that is irrelevant or rarely needed. Every extra unit of information competes with relevant units and diminishes their visibility.

**Good:** Focus on the task; progressive disclosure; quiet secondary chrome; content hierarchy that matches priority.

**Probes:**
- What can be removed without harming the task?
- Is rare information competing with primary actions?
- Are there decorative or marketing blocks inside the working UI?

**Failures:** Dense settings dumps; competing CTAs; dashboard widgets nobody uses on the critical path.

*Mechanism overlap:* Occam's Razor — cite under H8 only. H8 is **not** "make it pretty"; Aesthetic-Usability Effect is a caution in [laws.md](laws.md), not a score.

---

## H9 — Help users recognize, diagnose, and recover from errors

**Definition:** Error messages in plain language (no codes), precisely indicate the problem, and constructively suggest a solution.

**Good:** Human-readable errors next to the field; next step included; preserve user input; link to fix or support when needed.

**Probes:**
- Does the message say what went wrong and what to do next?
- Is the failing field identified?
- Is input preserved after failure?

**Failures:** "Error 500"; toast that vanishes before reading; wiping the form on failure; blame-the-user tone.

**Boundary:** Prevention → H5. Messaging & recovery after failure → H9. Do not file both for the same root cause unless prevention and recovery are separately broken.

---

## H10 — Help and documentation

**Definition:** Even if the system can be used without docs, help may still be needed. Help should be easy to search, focused on the user task, and list concrete steps.

**Good:** Contextual help at the point of need; short task-oriented docs; empty-state guidance; examples.

**Probes:**
- Can someone succeed without docs? If not, is help reachable from the stuck state?
- Is help task-shaped (steps) or feature-shaped (spec dumps)?
- Are empty states instructive?

**Failures:** Only a dense knowledge base with no in-product entry; tooltips that repeat the label; mandatory tutorial walls.

*Related caution:* Paradox of the Active User (people jump in without manuals) — design for that; still provide H10 for complex domains. Not a separate finding type.
