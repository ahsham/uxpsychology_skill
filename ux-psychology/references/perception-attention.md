# Perception & Attention for Interface Design

Distilled from the perception and attention literatures (Gestalt organization,
visual search, selective attention — the material covered in Eysenck & Keane
and Sternberg). The interface is processed *before* it is read: layout
communicates structure in the first glance, prior to any comprehension.

## 1. Preattentive processing — what registers before attention

A small set of visual features is detected in parallel across the whole visual
field in under ~250 ms, effortlessly: **color/hue contrast, size, orientation,
motion, spatial position**. Anything else (reading, comparing, counting)
requires serial, effortful attention.

**Design consequences**
- Encode the single most important distinction preattentively: the one red
  value in a green table, the one filled button, the badge that moved.
- Motion is the strongest capture — and therefore the most costly when
  misused. Autoplaying carousels and animated ads steal attention from the
  task continuously. Use motion only for events the user must notice now.
- Preattentive features don't stack well: if color, size, AND icons all vary
  independently, search becomes serial ("conjunction search" — see below).

## 2. Gestalt organization — grouping is meaning

The visual system organizes elements into wholes automatically. Users read
the *grouping* as the *information architecture*, whether you intended it or
not.

- **Proximity** — near things belong together. The strongest and cheapest
  grouping tool: whitespace between sections should exceed whitespace within
  them. A label must sit closer to its own field than to the next field.
- **Similarity** — same-looking things are read as same-kind. All links should
  look alike; anything styled like a button will be treated as one.
- **Common region** — a border/background creates a group (cards, panels).
  Stronger than proximity; use when proximity alone is ambiguous.
- **Uniform connectedness** — an explicit line/connector beats everything
  (steppers, tree lines).
- **Continuity** — elements on a line/curve are read as a path; aligned edges
  create implied structure. Misalignment reads as unrelatedness (or
  sloppiness).
- **Closure** — the mind completes incomplete shapes; a partially visible card
  at the screen edge signals "scroll for more" better than an arrow.
- **Figure–ground** — users must instantly resolve what is content vs.
  backdrop; modals rely on dimming to force the figure.

**Design consequences**
- Audit rule: *visual grouping must equal semantic grouping*. The most common
  layout bug is proximity contradicting meaning (a label equidistant between
  two fields; a price nearer the wrong product).
- Prefer whitespace over boxes/dividers — every added line is visual noise;
  proximity often does the job silently.

## 3. Visual hierarchy and scanning

Users scan, they don't read. Scanning follows learned patterns:
**F-pattern** for text-dense pages (two horizontal sweeps near the top, then a
vertical skim of the left edge), **Z-pattern** for sparse layouts, and
**layer-cake** scanning when good headings exist (headings only, diving in on
match).

**Design consequences**
- Front-load: first two words of headings/links carry most scanning value.
- Put the primary action on the natural scan path, not in a corner the path
  never visits.
- Strong headings convert F-pattern skimming (which misses right-side content)
  into layer-cake scanning (which is far more accurate). Headings are a
  perception tool, not a formatting nicety.
- Users develop **banner blindness**: anything shaped/positioned like an ad —
  right rail, colorful boxes, large images with text overlay — is filtered out
  preattentively. Don't make critical content look promotional.

## 4. Visual search — feature vs. conjunction

Finding one item among many is fast ("pop-out") when a single feature
distinguishes it, and slow/serial when the target differs only by a
*combination* of features (conjunction search: "the blue circle among blue
squares and red circles").

**Design consequences**
- Design lists/tables so the likely search key is the visually dominant,
  left-aligned element in each row.
- If users must find "unpaid AND overdue" invoices, don't encode paid-status
  as color and urgency as an icon — provide a filter, or a single composite
  visual state. Conjunction search over a data table is a task failure.
- Search time grows with the number of distractors; pagination/filtering isn't
  aesthetic, it's a perceptual necessity in long lists.

## 5. Selective attention, change blindness, inattentional blindness

Attention is a narrow spotlight; almost everything outside it is not
processed. Two robust consequences:

- **Inattentional blindness** — users engaged in a task literally do not see
  unexpected elements, even salient ones. That toast notification during
  checkout was never seen.
- **Change blindness** — changes occurring outside the focus of attention
  (especially without motion, or during a page transition) go unnoticed. If
  clicking a filter silently updates a total elsewhere on the page, users miss
  it.

**Design consequences**
- Put feedback *where the user is looking*: inline validation next to the
  field, price update next to the changed option, not in a distant corner.
- If a change must be noticed at a distance, use motion/animation briefly to
  exploit preattentive capture (e.g., a subtle count-up or highlight-fade on
  the updated total).
- Never rely on the user having "seen" a passive message. Anything
  consequential (unsaved changes, errors, mode switches) needs either
  placement in the locus of attention or a blocking interaction.

## 6. Top-down perception, expectations, and context

Perception is expectation-driven: users see what context and experience
predict (which is why Jakob's Law works, and why typos in familiar words go
unseen). Ambiguous elements are resolved by surrounding context.

**Design consequences**
- Icons are ambiguous stimuli; context and labels disambiguate them. Icon +
  label beats either alone for anything non-universal.
- Users will "perceive" the button where convention predicts it. Fighting
  prediction costs a search every single visit.
- Skeleton screens work because they prime the perceptual system with the
  page's structure before content arrives — prediction is satisfied instead
  of violated.

## 7. Contrast, legibility, and low-level vision

- Reading is a foveal task; body text needs adequate size (16 px+ web
  baseline), line length (~45–75 characters), and luminance contrast
  (WCAG ≥ 4.5:1 for body text). Contrast is a perception requirement, not a
  compliance checkbox.
- Peripheral vision is low-acuity but motion/contrast sensitive — it decides
  where the fovea goes next. Thumbnails, headings, and blocks of contrast are
  what peripheral vision can "read" to plan the next fixation.
- ~8% of men have some color-vision deficiency: never encode meaning in hue
  alone; pair with icon/label/position/weight.

## Quick audit questions (perception & attention)

1. Squint test: with the screen blurred, does the visual weight land on the
   primary task?
2. Does every visual group correspond to a semantic group, and vice versa?
3. Is the key distinction on each screen carried by ONE preattentive feature?
4. Is any critical feedback rendered outside the user's current locus of
   attention?
5. Does anything important resemble an ad or decoration (banner blindness)?
6. Could the main "find X" task be a conjunction search? Provide a filter.
