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

Tactical combat now runs through **Campaign-OS** (https://github.com/rmcneill2828-art/
Campaign-OS), a separate battle-map/VTT app, as the standard workflow -- not just an occasional
option. The DM (Claude, in this repo's chat) still narrates and decides everything; the user is
the DM's hands on the app. See this repo's root `CLAUDE.md` ("Running the game" -> "Tactical
combat runs in Campaign-OS") for the full turn-by-turn workflow.

Campaign-OS imports from this repo read-only, except for two write paths:
- **"End Session"** appends a new `## Session N` entry to session-log.md and updates
  world-state.md directly, using a real (separate, stateless) Claude Code call scoped to this
  repo (Read/Write/Edit only -- it never runs git, never commits). **Not used under the current
  chat-driven combat workflow** -- the DM (this chat) writes session-log.md/world-state.md
  itself, informed by Campaign-OS's "Copy Session Report" (a plain-text, non-AI transcript +
  final-token-state dump the user pastes into the chat as a factual check). End Session is for a
  different mode (Campaign-OS running a session unsupervised, no chat DM involved) -- if either
  file shows an update nobody manually wrote in this chat, that's what happened; match its
  established style when adding to it by hand rather than treating it as an error.
- **Create Character** writes a new `characters/<name>.md` file directly (deterministic, no
  Claude call) when built from Campaign-OS's Character Creator panel.

## Conventions
- Keep session-log.md narrative and specific -- named beats, real dialogue/decisions, not
  generic summaries.
- world-state.md should stay short enough to scan quickly; if a section is getting long, that's
  a sign the content belongs in session-log.md instead.
- Ability scores, saves, and combat math in character sheets should be 5e-rules-accurate --
  verify against the PHB tables (proficiency bonus by level, spell slots by class/level) rather
  than guessing.
