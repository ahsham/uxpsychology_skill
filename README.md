# ux-psychology — a Claude Skill

Apply cognitive psychology and the Laws of UX when designing or reviewing
user interfaces with Claude. Every recommendation is traceable to a
cognitive mechanism: *what the mind does → what the interface should do*.

Grounded in the frameworks from:

- Jon Yablonski, *Laws of UX* (O'Reilly)
- Eysenck & Keane, *Cognitive Psychology: A Student's Handbook*
- Sternberg, *Cognitive Psychology* (6th ed.)

> The skill contains original-wording distillations of these frameworks,
> not text from the books.

## What it does

- **Design mode** — applies perception, attention, memory, decision, and
  motor principles proactively while Claude builds UIs, with brief
  justifications for the consequential choices.
- **Review mode** — runs a structured 8-pass audit (perceive → attend →
  comprehend → remember → decide → act → recover → feel), delivering
  findings as *finding → mechanism → fix*, prioritized by impact.
- **Ethics guardrail** — recognizes dark patterns (confirmshaming, drip
  pricing, roach motels, fake scarcity…) and proposes honest alternatives.

## Structure

```
ux-psychology/
├── SKILL.md                          # routing + core reasoning loop
└── references/                       # loaded on demand (progressive disclosure)
    ├── laws-of-ux.md                 # the 10 laws + how they conflict
    ├── perception-attention.md       # Gestalt, preattentive, scanning, visual search
    ├── memory-cognitive-load.md      # working memory, chunking, recognition, load
    ├── decision-action-error.md      # biases, choice architecture, slips/mistakes, ethics
    └── review-protocol.md            # the audit procedure
```

## Install

**Claude.ai / Claude Desktop:** Settings → Capabilities → Skills → upload
the packaged `.skill` file (or upload `SKILL.md` in a chat and click
*Save skill*).

**Claude Code:** copy the `ux-psychology/` folder into `~/.claude/skills/`
(personal) or `.claude/skills/` in your project.

**Claude API:** upload via the Skills API / `skills` beta, or bundle the
folder in your agent's skills directory.

## Usage

No invocation needed — the skill triggers automatically on prompts like:

- "Build me a pricing page for my SaaS"
- "Review this checkout flow" (+ screenshot)
- "Why does my settings page feel so cluttered?"
- "Audit this dashboard for usability issues"

## License

MIT for the skill text. The underlying books are copyrighted by their
respective authors/publishers; this skill references their frameworks and
does not reproduce their content.
