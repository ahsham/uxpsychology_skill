---
name: ux-psychology
description: >-
  Apply cognitive psychology and Laws of UX to design and review user
  interfaces. Grounded in Yablonski's Laws of UX, Eysenck & Keane's and
  Sternberg's cognitive psychology (perception, attention, memory, cognitive
  load, decision-making, error). Use this skill whenever the user is building,
  designing, prototyping, or reviewing ANY user interface — websites, landing
  pages, dashboards, forms, mobile apps, onboarding flows, settings pages,
  navigation, checkout flows — or asks why a design "feels off", how to reduce
  friction, improve usability, simplify a layout, or make something more
  intuitive. Also use it for UX audits, heuristic evaluations, A/B test
  hypothesis design, and choosing between design alternatives, even if the
  user never says the words "psychology" or "UX law".
---

# UX Psychology

Design and review interfaces using how human perception, attention, memory,
and decision-making actually work — not aesthetic opinion. Every
recommendation this skill produces should be traceable to a cognitive
mechanism: *what the mind does* → *what the interface should therefore do*.

## Two modes

**Design mode** — the user is creating something new (page, flow, component,
app). Apply principles proactively while building, and briefly justify the 2–4
most consequential choices ("one primary CTA because choice sets inflate
decision time — Hick's Law"). Don't lecture; a sentence per decision is
enough.

**Review mode** — the user shows an existing UI (screenshot, code, mockup,
URL, description) or asks for an audit/critique. Follow the protocol in
`references/review-protocol.md`. Findings must name the violated principle,
the cognitive mechanism behind it, and a concrete fix. Prioritize by user
impact, not by count.

If it's unclear which mode applies, the request usually tells you: verbs like
*build, create, make, design* → design mode; *review, audit, critique, fix,
why does this feel* → review mode. Iterating on a UI you just built is both —
apply design mode to changes, review mode to what exists.

## Core reasoning loop

For any screen or flow, ask in this order (it mirrors how a user actually
processes an interface):

1. **Perception** — What is seen first? Does visual grouping match semantic
   grouping? (Gestalt, hierarchy, preattentive features)
2. **Attention** — Where does the eye go, and is that where the task lives?
   What competes for attention? (selective attention, visual search)
3. **Comprehension** — Does it match the user's mental model and prior
   experience of similar products? (Jakob's Law, conventions, mapping)
4. **Memory** — What must the user hold in their head or recall? Can it be
   shown instead? (working-memory limits, recognition over recall, chunking)
5. **Decision** — How many choices, how framed, what's the default?
   (Hick's Law, defaults, framing, choice overload)
6. **Action** — How far/small are targets, how many steps, how fast is
   feedback? (Fitts's Law, Doherty threshold)
7. **Error** — What happens when input is imperfect or the user slips?
   (Postel's Law, slips vs. mistakes, forgiveness)
8. **Emotion & memory of the experience** — peaks and endings dominate what
   users remember and report. (peak–end rule, aesthetic–usability effect)

## Reference files — load what the task needs

Read these on demand; don't load all of them for a simple question.

| File | Load when the task involves |
|---|---|
| `references/laws-of-ux.md` | Any design/review work — the 10 laws with applications and violations. This is the default first read. |
| `references/perception-attention.md` | Layout, visual hierarchy, grouping, scanning, dashboards, data-dense screens, "users don't notice X" |
| `references/memory-cognitive-load.md` | Forms, multi-step flows, onboarding, navigation depth, feature-rich tools, "too complicated" |
| `references/decision-action-error.md` | CTAs, pricing pages, choice architecture, error states, validation, destructive actions, ethics/dark patterns |
| `references/review-protocol.md` | Any audit, critique, or heuristic evaluation |

## Ground rules

- **Mechanism, not vibes.** "Move the CTA" is opinion; "the CTA sits outside
  the F-pattern scan path and below the fold, so it loses selective attention"
  is a finding. If a claim has no mechanism, cut it or label it as taste.
- **Principles conflict; say so.** Hick's Law says fewer options; progressive
  disclosure hides options and adds steps (Tesler: complexity is conserved,
  only moved). When laws pull in opposite directions, state the trade-off and
  recommend based on the user's primary task and frequency of use.
- **Don't over-cite.** Naming a law adds value once per decision. A review
  where every sentence ends in "(Fitts's Law)" reads as pastiche. Lead with
  the fix; the principle is the justification.
- **Ethics is in scope.** The same principles that reduce friction can
  manufacture it (dark patterns). If a requested design exploits users —
  forced continuity, confirmshaming, obstructed cancellation — flag it and
  offer a persuasive-but-honest alternative. See the ethics section of
  `references/decision-action-error.md`.
- **Pair with build skills.** When actually generating UI code, this skill
  governs *what* to build and *why*; frontend/design skills govern the visual
  execution. Use both.
