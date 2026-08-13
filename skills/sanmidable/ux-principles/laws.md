# Laws of UX

From the [Laws of UX](https://lawsofux.com/) tradition (Jon Yablonski et al.). Each entry: definition → probes → when it owns a finding vs defers.

---

## Folded into Nielsen (do not file here)

| Concept | Defer to |
| --- | --- |
| Jakob's Law | `ux-heuristics` H2 / H4 |
| Mental Model | H2 |
| Miller's Law / Chunking / Working Memory | H6 |
| Cognitive Load (general) | H6 / H8 |
| Occam's Razor | H8 |
| Paradox of the Active User | H10 posture only |

---

## Fitts's Law — target acquisition

Time to hit a target grows with distance and shrinks with size.

**Probes:** Are primary actions large enough? Close to likely pointer/thumb position? Are toast/destructive actions too small or awkwardly placed?

**Owns finding when:** Pointing efficiency is the issue (size/distance/placement).  
**Defer:** WCAG hit-target compliance → a11y skill.

---

## Hick's Law / Choice overload — decision time

More/complex simultaneous choices → slower decisions.

**Probes:** How many peer actions compete at the decision point? Is progressive disclosure or defaults missing?

**Owns when:** Choice **count/complexity** is the measurable problem.  
**Defer:** Expert accelerators → H7; pure clutter/noise → H8.

---

## Doherty Threshold — interaction pace

Keep response ~&lt;400ms when possible; otherwise show progress so neither side waits blindly.

**Probes:** Does the UI go silent past ~0.4s? Is there optimistic UI or determinate progress for longer work?

**Owns when:** **Latency budget** is wrong even if some status exists.  
**Defer:** Missing status entirely → H1.

---

## Peak-End Rule — remembered experience

People judge by the emotional peak and the ending more than the average.

**Probes:** What's the worst moment in the path? How does the flow end (success, surprise paywall, error)?

**Owns when:** Journey **memory structure** (peak/end) is the issue — not a single local heuristic miss.

---

## Serial Position Effect — first and last

First and last items in a series are remembered best.

**Probes:** Are critical actions mid-list? Is destructive action where habit-clicks land? Is the key onboarding step buried?

---

## Von Restorff (Isolation) Effect — distinctiveness

Among similar items, the distinct one draws attention and memory.

**Probes:** Is the primary CTA the most distinct peer? Or is secondary/ad chrome winning?

**Owns when:** **Relative distinctiveness** among peers is wrong.  
**Defer:** General clutter → H8.

---

## Zeigarnik Effect — incomplete tasks

Unfinished tasks occupy memory more than finished ones.

**Probes:** Can users resume? Is progress persisted? Is “done” unambiguous?

**Owns when:** Resume / open-loop closure is the gap.  
**Defer:** Live status chrome → H1.

---

## Goal-Gradient Effect — near-goal motivation

Motivation rises as the goal nears.

**Probes:** Does progress move early? Is distance-to-done honest? False progress?

**Owns when:** Progress **shape** demotivates.  
**Defer:** Missing progress UI → H1.

---

## Tesler's Law — conservation of complexity

Irreducible complexity must be absorbed by someone — prefer system/designer over user when possible.

**Probes:** Are users formatting, copying IDs, or re-entering known data the product could handle?

**Owns when:** Product decision is **who carries complexity**.  
**Defer:** Memory/recall symptoms → H6; missing power tools → H7.

---

## Postel's Law — accept liberally, emit conservatively

Tolerate messy real-world input; normalize clean outputs.

**Probes:** Rejecting paste, spaces, punctuation? Pedantic parsers?

**Owns when:** **Input tolerance** is the point.  
**Defer:** Over-strict prevention UX copy → H5 neighbor; still prefer Postel when acceptance is the principle.

---

## Gestalt grouping

Proximity, Similarity, Common Region, Uniform Connectedness, Prägnanz — perception groups and simplifies.

**Probes:** Related controls apart? Unrelated items carded together? False relationships from lines/boxes?

**Owns when:** **Perceptual grouping** is wrong despite otherwise consistent components.  
**Defer:** Inconsistent patterns → H4; signal-vs-noise clutter → H8.

---

## Aesthetic-Usability Effect — caution only

Attractive UI is often *perceived* as more usable — which can hide debt.

**Never score as a win.** Optionally note in Strengths/Out of scope: polish must not substitute for task success.
