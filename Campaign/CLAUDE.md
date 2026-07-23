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
- `characters/<name>.md` -- one sheet per PC/major NPC, mechanically precise (5e rules-accurate
  ability scores, saves, features, current HP/conditions).
- `campaigns/_template/` and `characters/_template.md` are blank templates, not real content.

## Paired tool: Campaign-OS

Tactical combat and live-session play for this campaign often run through **Campaign-OS**
(https://github.com/rmcneill2828-art/Campaign-OS), a separate battle-map/VTT app. It imports
from this repo read-only, except for one write path: its "End Session" feature can append a new
`## Session N` entry to session-log.md and update world-state.md directly, using a real Claude
Code call scoped to this repo (Read/Write/Edit only -- it never runs git, never commits).

If a session-log.md entry or world-state.md update shows up that nobody manually wrote with
Claude Code in this repo, that's expected -- it likely came from Campaign-OS's write-back, not
an error or something to overwrite. Match its established style when adding to it by hand.

## Conventions
- Keep session-log.md narrative and specific -- named beats, real dialogue/decisions, not
  generic summaries.
- world-state.md should stay short enough to scan quickly; if a section is getting long, that's
  a sign the content belongs in session-log.md instead.
- Ability scores, saves, and combat math in character sheets should be 5e-rules-accurate --
  verify against the PHB tables (proficiency bonus by level, spell slots by class/level) rather
  than guessing.
