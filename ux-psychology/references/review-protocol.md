# UI Review Protocol

A structured pass for auditing any screen, flow, or prototype. Works on
screenshots, live URLs, code, or descriptions. The order mirrors how a user
processes the interface (perceive → attend → understand → decide → act →
recover), so run it in order.

## Step 0 — Establish context first

A review without task context is decoration critique. Determine (ask if not
given, or state your assumptions explicitly):

- **Primary user & primary task** — what does success look like, for whom?
- **Frequency** — first-time/rare use (optimize learnability, recognition)
  vs. daily expert use (optimize efficiency, stability, density)?
- **Device & context** — touch targets and one-handed reach matter on
  mobile; data density norms differ for pro tools.
- **Stakes** — consumer checkout vs. medical dashboard changes every
  trade-off, especially error handling.

## Step 1 — The eight passes

For each pass: findings must state **principle → mechanism → specific fix**.
Skip passes that don't apply; don't pad.

1. **First glance (perception).** Squint test: does visual weight match task
   importance? Does grouping match meaning (Gestalt)? Is hierarchy carried by
   deliberate contrast (von Restorff) or is everything shouting?
2. **Scan path (attention).** Follow the F/Z path — is the primary action on
   it? Anything critical placed where banner blindness or change blindness
   will eat it? Any motion/animation stealing attention from the task?
3. **Comprehension (mental models).** Would a user of three competitor
   products operate this unaided (Jakob)? Icons labeled? Terminology
   consistent with the user's world, and identical across screens?
4. **Memory demands.** Anything carried across steps that could be shown?
   Recall that could be recognition? Comparisons requiring back-and-forth
   navigation? Placeholder-only labels?
5. **Decisions.** Count real choices per screen (Hick). Defaults present and
   user-aligned? Costs/consequences visible at the decision point? Any choice
   overload a recommendation would fix?
6. **Action mechanics.** Target sizes/spacing (Fitts; ~44 px touch).
   Primary action large and near the work. Interactive elements visually
   distinguishable from static ones. Feedback within ~400 ms (Doherty), in
   the locus of attention.
7. **Error & forgiveness.** Input tolerance (Postel). Slips: spacing, undo,
   constraints. Mistakes: previews of consequence. Error messages: located,
   human, actionable, input preserved. Destructive actions protected by
   non-automatable friction.
8. **Emotional arc & ethics.** Where are the peak and the ending of this flow
   (peak–end) — are they designed or accidental? Best design on the worst
   moments (errors, empty states, failures)? Any dark patterns (see
   decision-action-error.md §6) — flag them even if unprompted.

## Step 2 — Prioritize by impact, not count

Group findings into three tiers:

- **Task-blocking / trust-damaging** — user fails, errors, is deceived, or
  abandons. Fix first. Dark patterns always land here.
- **Friction** — user succeeds but pays in time, load, or confidence.
- **Polish** — measurable but minor; batch for later.

A review's value is its top three findings. Resist listing twenty
equal-weight nitpicks — that's the reviewer's version of choice overload.

## Step 3 — Deliver

Format (adapt to the user's ask, but default to):

1. **One-paragraph verdict** — overall assessment plus the single highest-
   impact change.
2. **Findings by tier** — each as *finding → mechanism → fix*, with the
   principle named once, concretely ("Swap the button order and make
   'Delete' the outlined secondary — right now the destructive action sits
   where the habitual confirm lands, and habits don't read labels").
3. **What's working** — genuinely, briefly; it tells the user what to
   preserve in the redesign. Skip if nothing stands out; don't invent praise.
4. **Trade-offs surfaced** — where principles conflicted and which side you
   took, so the user can overrule with context you lack.

If you're reviewing your own just-generated UI, hold it to the same standard
— run at minimum passes 1, 5, 6, 7 before presenting.

## Calibration notes

- Prefix uncertainty honestly: heuristics predict *likely* problems; only
  testing with users confirms them. Frame findings as hypotheses with
  mechanisms, and suggest what an A/B test or 5-user test would check when
  stakes warrant it.
- Beware the aesthetic–usability effect in your own judgment: a beautiful
  screenshot earns unearned charity. Run the passes anyway.
- Pro-tool density is not a violation: expert users with automatized
  workflows benefit from density and stability. Judge against the actual
  user, not consumer-app conventions.
