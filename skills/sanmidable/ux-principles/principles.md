# Classic interaction principles

Complements [laws.md](laws.md). These are design principles Nielsen heuristics imply but do not name cleanly. Still defer hard usability bugs to `ux-heuristics`.

---

## Progressive disclosure

Show only what is needed for the current step; reveal complexity on demand.

**Probes:**
- Is the first screen asking for advanced decisions too early?
- Are power settings behind a clear Advanced / step / drill-in?
- Do defaults cover the common case so disclosure is optional?

**Owns when:** Complexity is present but **badly staged**.  
**Neighbors:** Hick (too many peers at once); H7 (experts need a path — disclosure should not block them).

---

## Affordances & signifiers

Controls should suggest how they work; signifiers make the affordance visible (button looks pressable, link looks navigable).

**Probes:**
- Can users tell what is clickable/tappable without hovering every pixel?
- Are fake affordances present (looks like a button, isn't)?
- Icon-only actions without signifiers/tooltips?

**Owns when:** **Perceived actionability** is wrong.  
**Defer:** Missing accessible name → a11y; vocabulary/jargon → H2.

---

## Natural mapping

Controls should map to effects in spatial or conceptual ways users already understand (up = more, left/right matches the object, stepped wizards match task order).

**Probes:**
- Do sliders/toggles/directions match outcomes?
- Is wizard order fighting the real-world task sequence?

**Owns when:** **Control↔effect mapping** is the bug.  
**Defer:** Domain jargon → H2; platform inconsistency → H4.

---

## Smart defaults

Most users keep pre-selected values — defaults should be safe, common, and reversible.

**Probes:**
- Empty required fields where a sensible default exists?
- Dangerous defaults (public, charge, delete-adjacent)?
- Defaults that lock users into hard-to-undo states?

**Owns when:** **Default choice quality** is the issue.  
**Neighbors:** H5 (prevention); forgiveness (easy to change after).

---

## Forgiveness

Easy recovery from mistakes: undo, cancel, confirm destructive acts with context, reversible exploration.

**Probes:**
- Can users back out mid-flow without data loss?
- Is there undo after risky actions?
- Are confirms informative (what will be lost)?

**Owns when:** Framing the issue as **explorability / recovery posture**.  
**Defer:** Concrete missing exit/undo control → H3; error copy after failure → H9.

---

## Direct manipulation

Let users act on visible objects (drag reorder, inline edit, canvas) rather than opaque commands or remote forms when the task is spatial or object-centric.

**Probes:**
- Is the user editing through a disconnected form when the object is on-screen?
- Would drag/inline edit match the mental model better?

**Owns when:** Interaction model should be **object-direct** and isn't.  
**Defer:** Platform standard patterns → H4.

---

## Perceived performance

Beyond raw Doherty timing: skeletons, optimistic UI, stable layout, progress that feels continuous, avoiding blank freezes.

**Probes:**
- Does waiting feel shorter via skeleton/placeholder?
- Layout shift during load?
- Optimistic updates where safe?

**Owns when:** **Perceived** wait/quality is the issue and raw latency notes aren't enough.  
**Neighbors:** Doherty (budget); H1 (status visibility).
