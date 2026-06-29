---
name: skill-editor
description: Audit and tighten existing AI skill.md files. Use when editing or improving a
  skill that already exists, especially to remove AI-speak (em dashes, "X, not Y" pairings,
  banned filler words) and bloat. Different from skill-creator, which is for building new skills
  from scratch.
---

# Skill Editor

Audit and tighten existing SKILL.md files. Goal: same meaning, fewer words, no AI tics.

Target: ~150 lines of prose instruction. Templates and examples don't count against that the same way. Hard ceiling is 500 lines total. Go longer only when the content genuinely earns it.

Work in three phases. Don't jump to wording fixes before structural ones.

---

## Phase 1: Pre-edit health check

Structural problems matter more than wording. Answer these 5 questions before hunting for AI-speak:

1. **What is the actual job, in one sentence?** If you can't write it cleanly, fix that first.
2. **Does the description name when to trigger, not just what the skill does?** Good triggers describe a moment ("stuck on a decision," "cleaning a messy spreadsheet"). Bad triggers describe an action ("for use with X").
3. **Does the skill specify what context or input it needs before it can work?** Most skills need an artifact. If that's missing, flag it.
4. **Does it explain the why for non-obvious rules?** ALL CAPS and rigid MUSTs usually signal a rule that lacks a reason. Reframe as "do X because Y."
5. **Would a smart model follow this and produce good results without asking mid-task?** If the skill leaves obvious gaps, wording edits won't fix them.

If any answer is no, propose structural changes first.

---

## Phase 2: Progressive disclosure check

Skills load in three levels: name/description (always in context), SKILL.md body (when triggered), bundled files (on demand). Check that the skill uses these levels well:

- **Length:** Cut bloat and redundancy to stay near 150 lines. Split into a reference file only when content isn't needed on every run — never just to hide length.
- **Long inline reference material:** Style guides, schemas, templates that aren't always needed belong in `references/` with a one-liner pointing to them.
- **Repeated helper work:** If the model writes the same script every run, bundle it in `scripts/` and have the skill call it.
- **Domain forks:** Skills handling multiple variants (AWS vs. GCP, Python vs. JS) often work better as a thin SKILL.md plus per-variant reference files.

---

## Phase 3: Wording and style

### Description format

`[One line of what the skill is]. Use when the user [concrete trigger moments].`

- First sentence: what the skill is, plainly.
- Second sentence: starts with "Use when" and names situations the user would actually be in.

Example: `Personal life advisor that gives honest advice based on your personal plan. Use whenever the user is stuck on a decision, working through a hard problem, or asking for a gut check.`

Flag:
- Vague descriptions that won't fire reliably
- Descriptions that assume the user already has the artifact

### AI-speak fixes

**Em dashes** — Replace em dashes used for dramatic pauses or tacked-on details with a period, comma, or conjunction.

**"X, not Y" pairings** — State the primary point directly. Drop the negative contrast.

**Banned filler words** — See `references/ai-speak-banned-filler-words.md` for the full list. The main categories:

- Cliché openers: *delve into, let's dive in, navigate the landscape, embark on a journey*
- Hype verbs: *leverage, utilize, streamline, revolutionize, empower, harness*
- Transition overload: *moreover, furthermore, notably, subsequently, as previously mentioned*
- Soft qualifiers: *it's worth mentioning, generally speaking, it goes without saying, undeniably*
- Empty adjectives: *robust, seamless, comprehensive, cutting-edge, game-changing, pivotal*
- Metaphor fluff: *tapestry, testament, catalyst, beacon, cornerstone, paradigm, plethora*
- Conclusion signposts: *in conclusion, in summary, ultimately, that being said, moving forward*

Write conversationally. Cut every word that doesn't pull its weight.

---

## Output format

Present edits in two parts:

1. **Health check findings** — one line per question, flag anything that needs structural work.
2. **Revised skill** — full rewritten SKILL.md, ready to drop in.

If structural changes are needed, present those first and confirm before rewriting prose.
