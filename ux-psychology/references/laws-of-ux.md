# The Laws of UX (after Yablonski)

Ten psychological principles, each stated as: mechanism → design application →
common violations. These are heuristics grounded in cognitive research, not
physics — when two conflict, reason from the user's primary task.

## 1. Jakob's Law

**Mechanism.** Users spend most of their time on *other* products, so they
arrive with transfer expectations: mental models built elsewhere. Interfaces
that match those models feel "intuitive"; the feeling of intuitiveness is
mostly familiarity.

**Apply.** Follow platform and category conventions by default: logo top-left
links home, cart top-right, search magnifier, underlined links, hamburger on
mobile, settings gear. Spend your innovation budget on the product's core
differentiator, not on reinventing navigation. When you must change a familiar
pattern, ease the transition (allow the old way temporarily, or onboard the
change explicitly).

**Violations.** Novel navigation metaphors, custom scroll behavior,
unconventional form layouts, mystery-meat icons without labels, "creative"
checkout flows. Test: could a first-time visitor who has used three competitor
products operate this screen without instruction?

## 2. Fitts's Law

**Mechanism.** Time to acquire a target grows with distance to it and shrinks
with its size. Pointing is a closed-loop motor task; small/far targets force
slower, corrective movements.

**Apply.** Make primary actions large and near the user's current focus (e.g.,
submit button adjacent to the last form field). On touch, minimum ~44–48 px
targets with spacing between adjacent tappables. Exploit screen edges and
corners on desktop — they are "infinitely deep" targets you can't overshoot.
Place related controls close to the objects they act on.

**Violations.** Tiny close buttons on modals, link-only actions in dense
tables, primary CTA far from the completed task, adjacent destructive and safe
buttons with no spacing.

## 3. Hick's Law

**Mechanism.** Decision time grows with the number and complexity of options.
Each added choice inflates the comparison the user must run before acting.

**Apply.** One primary action per screen; demote the rest visually. Break
complex tasks into steps (wizard/checkout stages). Categorize long lists.
Use smart defaults so most users decide nothing. Highlight a recommended
option in pricing tiers. Onboarding: ask only what's needed now.

**Violations.** Mega-menus with 40 undifferentiated links, settings pages as
flat alphabetical dumps, five equally-weighted buttons, forms asking for
everything upfront. Caveat: don't oversimplify by *removing* needed
capability — that trades decision time for task failure. Reduce *perceived*
complexity (grouping, staging, defaults), not necessarily functionality.

## 4. Miller's Law

**Mechanism.** Working memory holds only a few items (classically 7±2; modern
estimates ~4 chunks). The usable insight is not a magic number but
**chunking**: organizing information into meaningful units multiplies
effective capacity.

**Apply.** Chunk phone/card/IBAN inputs with spacing. Group navigation into
5±2 labeled sections rather than 15 flat links. Break content with headings so
each section is one graspable unit. Keep anything the user must *carry* across
steps visible (persistent order summary in checkout).

**Violations.** Unformatted 16-digit inputs, comparison flows that force
memorizing option A while reading option B, instructions given on step 1 that
are needed on step 4.

## 5. Postel's Law (robustness principle)

**Mechanism.** "Be liberal in what you accept, conservative in what you send."
Human input is variable; rigid systems transfer the machine's needs onto the
user as friction and errors.

**Apply.** Accept phone numbers with/without spaces, dashes, country codes;
parse dates in several formats; trim whitespace; make email case-insensitive;
autocorrect common typos ("gamil.com" → suggest "gmail.com"). Support multiple
input modes (paste, autofill, camera scan). Meanwhile be conservative in
output: clear, specific, minimal interface responses.

**Violations.** "Invalid format" errors for inputs a human finds obviously
valid, forms that clear all fields on one error, rejecting pasted 2FA codes
with spaces, password fields that block paste.

## 6. Peak–End Rule

**Mechanism.** People judge an experience by its most intense moment and its
ending, not the average of every moment (duration neglect). Retrospective
memory — which drives reviews, retention, word of mouth — is built from peaks
and endings.

**Apply.** Engineer a positive peak at the moment of core value (first
successful result, order confirmation, "you're all set"). Invest in endings:
confirmation screens, offboarding, post-purchase. Blunt negative peaks: the
error page, the failed payment, the empty search result deserve your best
design, not your least. A delightful 404 or a helpful failure state converts
the likely worst moment.

**Violations.** Bare-bones confirmation pages after a polished funnel,
hostile cancellation flows (the ending users tell others about), error states
written by the backend team.

## 7. Aesthetic–Usability Effect

**Mechanism.** Visually pleasing designs are *perceived* as easier to use and
earn tolerance for minor flaws. Aesthetics build trust and positive affect,
which broadens patience.

**Apply.** Invest in visual craft — it is functional, not decoration. But
treat the effect as a mask during research: users report attractive designs as
usable even when they struggled. In usability testing, watch behavior
(hesitation, backtracking, errors), not just satisfaction ratings.

**Violations.** Assuming pretty = usable; shipping a beautiful redesign that
tests well on preference but hides task-failure regressions.

## 8. Von Restorff Effect (isolation effect)

**Mechanism.** Among similar items, the one that differs is noticed and
remembered. Contrast captures preattentive attention.

**Apply.** Make the primary action visually distinct from secondary ones
(color, weight, fill). Highlight the recommended pricing tier. Use accent
color sparingly and *only* for what matters. Distinctiveness is a budget: if
everything is highlighted, nothing is.

**Violations.** Three filled buttons of equal weight, red used both for errors
and for the brand, promotional badges on every product card, "NEW" tags that
never expire. Also: don't rely on color alone (accessibility) — pair with
shape, weight, or label.

## 9. Tesler's Law (conservation of complexity)

**Mechanism.** Every process has irreducible complexity. It can be moved —
from user to interface/system/developer — but not deleted. "Simplification"
that deletes necessary complexity just relocates it into the user's head or
into support tickets.

**Apply.** Absorb complexity on the system side: infer card type from the
number, prefill from context, remember prior choices, compute what can be
computed. When complexity must remain user-facing, stage it (progressive
disclosure) and default it. Ask "who pays for this complexity?" for each
design decision — the answer should rarely be "the user, every time."

**Violations.** Asking users for data the system already has, exposing raw
system state (IDs, jargon) in the UI, minimalist designs that hide essential
controls so thoroughly that users can't find them (over-application of
minimalism is itself a Tesler violation — the complexity moved into discovery).

## 10. Doherty Threshold

**Mechanism.** Interaction feels fluent when system response stays under
~400 ms; beyond that, attention drifts, flow breaks, and productivity drops.
Perceived speed matters as much as measured speed.

**Apply.** Target sub-400 ms feedback for interactions. When work is genuinely
slow, manage perception: optimistic UI (show success immediately, reconcile in
background), skeleton screens over spinners, progress indication for
multi-second tasks, meaningful progress text ("Analyzing 3 of 12 files…").
Counterintuitively, *too instant* can undermine trust for "weighty"
computations — a brief deliberate delay on e.g. a scan result can increase
perceived credibility; use sparingly and honestly.

**Violations.** No feedback on tap (user taps again → double submit), spinner
with no time information for 30-second jobs, blocking full-page loads for
partial updates.

## Using the laws together

- **Hick vs. Tesler:** removing options reduces decision time until it hides
  necessary function; then complexity re-emerges as search cost. Resolve by
  frequency: optimize for the common case, disclose the rest progressively.
- **Jakob vs. Von Restorff:** conventions make things findable; distinctiveness
  makes things noticed. Be conventional in structure, distinctive in emphasis.
- **Fitts vs. safety:** big-and-close is right for primary actions but wrong
  for destructive ones — deliberately add distance/confirmation friction to
  irreversible actions.
- **Aesthetic–usability vs. testing:** beauty buys forgiveness in production
  and lies to you in research.
