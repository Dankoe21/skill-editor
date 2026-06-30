# Eval: skill-editor

Grade in a fresh subagent with a clean context (it sees only the original SKILL.md, the revised
SKILL.md, and this file). Pass = all boxes checked. Any fail = loop back to edit.

## Phase 1: Structural health check
- [ ] All 5 health-check questions were actually answered, not skipped
- [ ] Structural problems were flagged and addressed before any wording pass happened
- [ ] The one-sentence job statement is accurate to what the skill actually does
- [ ] Trigger description names moments ("stuck on X"), not actions ("for use with X")
- [ ] Required input/context is stated if the skill needs an artifact to function
- [ ] ALL CAPS / rigid MUST rules were reframed with a stated reason, or left alone with good cause

## Phase 2: Progressive disclosure
- [ ] Revised SKILL.md is near 150 lines of prose (templates/examples excluded), under the 500-line hard ceiling
- [ ] Reference material not needed every run was moved to `references/`, not left bloating the body
- [ ] Reference material *was* kept inline if the skill actually needs it on every run
- [ ] No split was made purely to hide length without a genuine on-demand reason

## Phase 3: Wording and style
- [ ] No em dashes remain
- [ ] No comma-bracketed asides or parentheticals were introduced as a disguised stand-in for a dash
- [ ] No "X, not Y" pairings remain; the primary point is stated directly
- [ ] No banned filler words remain (check against `references/ai-speak-banned-filler-words.md`)
- [ ] Voice and meaning are preserved, nothing was rewritten into a different instruction

## Output format
- [ ] Response had two clear parts: health check findings, then the full revised SKILL.md
- [ ] If structural changes were needed, they were presented and confirmed before the prose rewrite
- [ ] Revised file is genuinely ready to drop in, not a partial diff or a description of changes
