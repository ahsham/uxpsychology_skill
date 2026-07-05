# Decision-Making, Action & Error for Interface Design

Distilled from the judgment & decision-making and action/error literatures
(dual-process theory, heuristics and biases, slips vs. mistakes — as covered
in Eysenck & Keane and Sternberg). Plus the ethics line: these mechanisms
persuade and they exploit; the difference matters.

## 1. Dual-process cognition: design for System 1, support System 2

Most interface behavior is fast, associative, and effortless (System 1);
deliberate reasoning (System 2) is slow, lazy, and engaged only when
necessary. Users satisfice — they pick the first acceptable option, not the
best one — and they muddle through rather than read.

**Design consequences**
- The default path must be correct for the majority, because most users take
  it without deliberation.
- Don't demand System 2 for routine actions (comparisons, mental math,
  reading dense terms). Do *invite* System 2 for consequential ones: slow the
  user down at irreversible or expensive decisions (summaries, explicit
  consequences, brief friction).
- Microcopy is read by System 1: first words, verbs on buttons ("Save
  changes", not "OK"), one idea per sentence.

## 2. Heuristics and biases you are designing with (or against)

- **Anchoring** — the first number seen shapes all later judgments. Original
  price next to sale price; highest tier shown first. Anchors work even when
  known to be arbitrary.
- **Defaults / status-quo bias** — defaults are the most powerful choice
  instrument in UI; most users keep them. Set defaults to the choice most
  users would make *for themselves* when informed (that's the ethical test).
- **Framing & loss aversion** — losses loom about twice as large as gains.
  "Don't lose your progress" outmotivates "keep your progress". Trial-ending
  and cancellation flows are inherently loss-framed; use with restraint.
- **Availability** — recent/vivid examples dominate probability judgments.
  Testimonials and recent-activity feeds ("3 people booked today") work
  through availability; false ones are manipulation.
- **Social proof** — under uncertainty, people copy others. Ratings, "most
  popular" badges. Honest when real, dark when fabricated.
- **Choice overload** — beyond a handful of options, satisfaction and
  conversion drop even as attraction to variety rises. Curate; recommend
  one; make differences meaningful rather than numerous (see Hick's Law).
- **Sunk cost / commitment** — progress shown (profile 60% complete,
  streaks) motivates completion. Endowed progress (start the bar at 20%)
  measurably increases follow-through.
- **Scarcity/urgency** — effective and the most abused pattern in
  e-commerce. Real deadlines and real stock levels only.

## 3. Choice architecture in practice

- One recommended option, visibly justified ("Most teams choose Pro"),
  reduces both decision time and post-choice anxiety.
- Order matters: primacy in lists, "good–better–best" pricing with the
  target tier in the middle-right, decoy tiers make the target look
  rational — know that you're doing it.
- Show consequences at the point of decision: price *with* tax and shipping
  before the final step (drip pricing is a dark pattern and a trust killer),
  "renews 5 Aug at €12/mo" on the subscribe button.

## 4. Action: gulfs of execution and evaluation

Two gaps to close on every screen: can the user figure out *what to do* to
achieve their goal (execution), and can they tell *what happened* after
acting (evaluation)?

- **Execution:** controls must signal their function (perceived
  affordances — buttons look pressable, links look clickable, draggables
  show grip). Flat design's chronic failure is affordance removal: test
  whether interactive and static elements are visually distinguishable.
- **Mapping:** controls should spatially/logically correspond to their
  effects (volume slider horizontal → louder rightward; arrangement of
  controls mirrors arrangement of the things controlled).
- **Evaluation:** every action gets immediate, located feedback (see
  Doherty threshold; change blindness). State changes must be visible:
  saved/unsaved, on/off, syncing/synced. A toggle whose state is ambiguous
  ("does blue mean on?") fails evaluation — pair state with a label.

## 5. Errors: slips vs. mistakes (they need opposite fixes)

- **Slips** — right intention, wrong execution (fat finger, autopilot,
  adjacent-button hit). Users *know* what they wanted. Fix with:
  constraints (disable invalid options rather than erroring after),
  spacing/size (Fitts), confirmation only for rare destructive acts,
  and above all **undo**. Undo beats confirmation: confirmations get
  automatized (see automaticity), undo works after the fact.
- **Mistakes** — wrong intention from a wrong mental model (user believes
  the system works differently). Confirmation dialogs don't help — the user
  confirms confidently. Fix with: better system visibility, previews of
  consequences ("this will email 2,400 people"), clearer conceptual model,
  and education at the decision point.

**Error message contract** (every error, no exceptions): say *what
happened*, in human language; *why / which input*, located at the source;
*how to fix it*, specifically; and preserve everything the user entered.
Blame the system, not the user ("We couldn't process the card" not "You
entered an invalid card").

**Forgiveness stack, strongest first:** prevent (constraints, good
defaults) → tolerate (Postel: accept variant input) → warn before
consequence (preview) → undo after → and only then, confirm.

## 6. The ethics line: persuasion vs. dark patterns

Every mechanism above is dual-use. The working test: **does the design help
users do what *they* want efficiently, or trick them into what the business
wants against their interest?** Would the design survive the user's fully
informed hindsight?

Recognize and refuse to produce (offer honest alternatives instead):
- **Forced continuity / roach motel** — easy in, obstructed out. Cancellation
  must be as easy as signup.
- **Confirmshaming** — decline options worded to humiliate ("No thanks, I
  hate saving money").
- **Sneak into basket / drip pricing** — added items or fees revealed late.
- **Fake scarcity/urgency/social proof** — invented countdowns, stock, or
  activity.
- **Misdirection** — visual emphasis on the business-preferred choice while
  the user-preferred one is disguised (grey "decline" link styled as
  disabled).
- **Privacy zuckering / bad defaults** — defaults that maximize data
  extraction rather than user intent.
- **Nagging & obstruction** — repeated interruptions until consent.

When a user's request drifts here, name it, explain the trust/retention/legal
cost (GDPR and consumer-protection regimes increasingly prohibit these), and
propose the persuasive-but-honest version: real social proof, genuine
urgency, loss-framing of *true* losses, excellent defaults.

## Quick audit questions (decision, action, error)

1. What's the default at every choice point, and is it what an informed user
   would pick?
2. Is any pricing, consequence, or commitment revealed later than the
   decision it belongs to?
3. Can every interactive element be identified as interactive at a glance?
4. Does every action produce immediate feedback where the user is looking?
5. For each destructive action: is there undo? Is confirmation automatizable?
6. Do error messages locate, explain, and preserve input?
7. Would each persuasion element survive the user's informed hindsight?
