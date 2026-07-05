# Memory & Cognitive Load for Interface Design

Distilled from the memory literature (working memory, long-term memory,
recognition vs. recall, skill acquisition — as covered in Eysenck & Keane and
Sternberg) plus cognitive load theory. The theme: **the interface should be
the user's external memory.** Every item a design forces users to hold in
their head is capacity stolen from the actual task.

## 1. Working memory: small, fragile, already busy

Working memory holds roughly **4 chunks** for seconds, and is disrupted by
interruption, distraction, and any concurrent verbal task. Crucially, the
user's working memory is occupied by their *goal* — the interface competes
with the task itself for the same capacity.

**Design consequences**
- Never require carrying information across screens: keep the order summary
  visible through checkout; repeat the email address on the "check your
  inbox" screen; show the original value next to the field being edited.
- Comparison is the classic violation: choosing between plans/products by
  navigating back and forth forces memorization. Provide side-by-side
  comparison for anything users choose among.
- Interruptions destroy working-memory contents. A modal, a session timeout,
  or a permission prompt mid-task means the user returns having lost their
  place — restore context after any interruption (draft preserved, scroll
  position kept, step highlighted).
- Error messages must appear with the field and persist while being fixed —
  a toast that vanishes in 4 seconds asks working memory to do the
  interface's job.

## 2. Chunking: the multiplier

Capacity is counted in *chunks*, not items — meaningful grouping expands what
fits. Expertise is largely chunk-building: what's 12 items to a novice is 3
chunks to an expert.

**Design consequences**
- Format all long identifiers: `4111 1111 1111 1111`, `+372 5555 5555`,
  license keys in dashed groups. Accept unformatted input (Postel), display
  formatted output.
- Structure navigation as ~5 labeled groups rather than one flat list; the
  group labels become retrievable chunks.
- Progressive steps in a wizard are chunking applied to a process: each step
  should be one coherent chunk ("Shipping", "Payment"), not an arbitrary
  slice.

## 3. Recognition over recall

Recognition (seeing and identifying) is dramatically easier and more accurate
than recall (retrieving from memory with no cue). Most of "intuitive UI" is
replacing recall with recognition.

**Design consequences**
- Menus over command lines for non-experts; autocomplete over blank search
  boxes; recently-used and suggestions everywhere ("recent files", "search
  again for…", saved addresses at checkout).
- Show, don't ask: display the current plan when the user opens billing;
  show the applied filters as removable chips instead of expecting users to
  remember what they set.
- Date pickers, dropdowns of valid values, and inline examples
  (`name@example.com` as helper text, not placeholder-only) all convert
  recall to recognition.
- Placeholder-only labels are a recall trap: once the user types, the label
  is gone and they must remember what the field was. Use persistent labels
  (or floating labels).

## 4. Long-term memory: encoding, retrieval cues, spacing

- **Serial position:** first and last items in a list are remembered best;
  the middle sinks. Order menus and onboarding content accordingly.
- **Encoding specificity:** retrieval succeeds when cues at recall match cues
  at encoding. If the marketing site calls it "Workspace" and the app calls it
  "Project", the user's memory cue fails. Terminology consistency is a memory
  feature.
- **Depth of processing:** things processed for meaning are retained; things
  passively shown are not. Onboarding that has users *do* the action beats a
  tour that shows it. Assume tooltips-tour content is forgotten by tomorrow.
- **Spacing & reinstatement:** infrequent tasks (annual renewal, rare
  settings) will always be re-learned from scratch — design them for
  first-time users every time, no matter how experienced the user is
  elsewhere in the product.

## 5. Prospective memory: remembering to do things

Remembering to perform a future action is the most failure-prone memory task
("verify your email later", "come back and finish"). Interfaces that depend
on the user remembering to return, save, or complete will leak users.

**Design consequences**
- Auto-save drafts; never depend on "remember to save".
- Resumable flows with re-entry cues (email links straight back into the
  half-done state).
- Visible pending-state indicators (badge on the incomplete profile) act as
  environmental cues, which is how humans actually manage prospective memory.

## 6. Cognitive load: intrinsic, extraneous, germane

Total load = **intrinsic** (the task's real difficulty) + **extraneous**
(difficulty added by presentation) + **germane** (effort building
understanding). Design can't remove intrinsic load (Tesler's Law) but is
fully responsible for extraneous load.

**Extraneous load sources to hunt in reviews**
- Visual noise: decorative variation, boxes-in-boxes, gratuitous color.
- **Split attention:** related information presented apart (legend far from
  chart, error summary far from fields, instructions on a previous step).
  Integrate at the point of need.
- **Redundancy:** the same information presented twice simultaneously in
  full (long text + person reading the same text aloud; label + tooltip
  repeating label) adds load rather than helping.
- Jargon and system-oriented language ("Error 40122: transaction context
  invalid") — translation is load transferred to the user.
- Inconsistency: every deviation in layout/wording between similar screens
  must be re-processed.

**Managing intrinsic load**
- Stage it: progressive disclosure, sensible defaults, wizards. Complexity
  per moment is what overwhelms, not total complexity.
- Offload computation: show totals, differences, and consequences ("this
  will charge €14 today") instead of making users derive them.

## 7. Automaticity and skilled use

With practice, action sequences become automatic — fast, effortless, and
*not consciously monitored*. This is why frequent users fly through your UI,
and why two things break them badly:

- **Moving things.** Rearranging menu items or buttons between releases
  breaks automatized motor sequences; experienced users mis-click for weeks.
  Layout stability is a feature for your best users. If reorganization is
  necessary, do it rarely and all at once, not continuously.
- **Habit-adjacent destructive actions.** An "OK" confirmation clicked 50
  times a day is automatic — it no longer protects anything. Protect rare
  destructive actions with *non-automatable* friction (type the project
  name), and never place them where a habitual action lands.

## Quick audit questions (memory & load)

1. What must the user hold in working memory at each step? Can the interface
   display it instead?
2. Is anything recall that could be recognition (blank inputs → suggestions,
   remembered settings)?
3. Do labels/terms match across marketing, app, emails, and docs?
4. Are related pieces of information visually integrated, or does the layout
   split attention?
5. What happens after an interruption — is the user's context restored?
6. Would a returning-after-a-year user succeed on the rare flows?
7. Does anything rely on the user remembering to come back?
