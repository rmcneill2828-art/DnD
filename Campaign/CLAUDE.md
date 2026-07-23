# DnD Campaign Notes

Markdown-based DM tracker for tabletop campaigns. Structure:
- `active.md` -- which campaign + character is currently active (campaign slug + character
  name). Update this and confirm with the user before switching.
- `campaigns/<slug>/overview.md` -- premise, tone, setting, factions. Rarely changes.
- `campaigns/<slug>/world-state.md` -- living tracker, active threads only (party status, quest
  log, NPCs, locations). Full history belongs in session-log.md, not here -- don't duplicate.
- `campaigns/<slug>/session-log.md` -- one file per campaign, all sessions appended as
  `## Session N -- date` sections in chronological order. Narrative prose in the campaign's
  established voice (character beats, thematic callbacks), not a mechanical log.
- `characters/<name>.md` -- one sheet per PC, mechanically precise (5e rules-accurate ability
  scores, saves, features, current HP/conditions).
- `npcs/<name>.md` -- same format/rigor as `characters/`, for major NPCs who might plausibly end
  up in a fight (an ally who could join combat, a recurring threat). Kept separate from
  `characters/` specifically because Campaign-OS's importer treats the two folders differently:
  an `npcs/` sheet imports as a "monster"-styled token (vs. "hero" for `characters/`), and if its
  `### Attacks` table has more than one row, every row folds into a Multiattack the token fires
  as one action -- `characters/` sheets keep the older "first row only" behavior since PCs use
  that same table shape to list weapon *options* (main-hand/off-hand/javelin), not a Multiattack.
  Minor one-off NPCs/mooks not worth a permanent file don't need a sheet -- just enter their
  stats directly into Campaign-OS's manual "Add Token" form when a fight starts.
- `campaigns/_template/` and `characters/_template.md` are blank templates, not real content.

## Paired tool: Campaign-OS

**Campaign-OS** (https://github.com/rmcneill2828-art/Campaign-OS) is a separate battle-map/VTT
app being actively built out alongside this campaign, but **not yet used for actual play** --
its combat engine only handles flat weapon attacks (to-hit, damage, crit, advantage,
Multiattack, movement). It has no concept of ability scores, saving throws, spell slots, or any
class feature/resource (Rage, Reckless Attack's downside, spellcasting entirely) -- everything
this party actually leans on beyond basic weapon swings. Decided together (2026-07-23) not to
force it into live play until it can actually cover that; keep improving it in parallel, not as
a blocker. Real combat stays running the normal way: DM narration in chat + PowerShell dice, per
the root `CLAUDE.md`.

It imports from this repo read-only, except for two write paths (not used under the current
workflow, since the DM writes session-log.md/world-state.md directly in chat): "End Session"
(appends a session entry / updates world-state.md via a separate, stateless Claude Code call)
and "Create Character" (writes a new characters/<name>.md directly, no Claude call). If either
file ever shows an update nobody manually wrote in chat, that's what happened -- match its
established style when adding to it by hand rather than treating it as an error.

## Conventions
- Keep session-log.md narrative and specific -- named beats, real dialogue/decisions, not
  generic summaries.
- world-state.md should stay short enough to scan quickly; if a section is getting long, that's
  a sign the content belongs in session-log.md instead.
- Ability scores, saves, and combat math in character sheets should be 5e-rules-accurate --
  verify against the PHB tables (proficiency bonus by level, spell slots by class/level) rather
  than guessing.
