# DM notes -- for Claude

_The player is also the reader of this repo, so this file holds instructions and pointers only --
no story, no secrets. The adventure itself lives in the source files below; read them as needed
and keep what's in them from the player until it's discovered in play._

## Sources (owned books -- full RAW use is fine)
- **Adventure text:** `F:\DnD\Adventures & Modules\Lost Mine of Phandelver\Lost Mine of Phandelver.pdf`
  (also inside `F:\DnD\Adventures & Modules\Standalone Modules\D&D Starter Set.pdf`).
- **Structured version (encounters, NPCs, treasure):** the Fantasy Grounds module,
  `F:\DnD\Third-Party & Online Resources\Fantasy Grounds\WOTC5ELMOP v1.1.2 Build-1066 (2022_06_18 02_23_53 UTC).zip`
  -> `modules/DD Lost Mine of Phandelver.mod` (readable with Campaign-OS's `tools/lib/fantasy-grounds.js`).
- **Maps:** DM versions (labels, secrets) are in `F:\DnD\Adventures & Modules\Lost Mine of Phandelver\Lost Mine of Phandelver Maps\`
  -- never show those to the player. Player versions for building battle maps are in
  `C:\Users\rober\OneDrive\DND\Maps\Lost Mine of Phandelver\Battle Maps\`; handouts the player may
  be shown are in `...\Maps\Lost Mine of Phandelver\Handouts\` (Campaign OS 3D's Handouts folder).
  `DND\Maps\` is git-ignored, so these stay out of the repo.
- **Monsters and NPCs:** every creature the adventure uses has a stat block in Campaign OS's
  compendium -- the standard ones from the SRD/Monster Manual, and the adventure's own named
  villains and townsfolk with `"source": "Lost Mine of Phandelver"` (spawn them by name).

## Before every session: preparation checklist
Agreed with the player after Session 1 (2026-10-11). Do every step before the first line of
narration. It's written so a person running the game without Claude can follow it too. Keep
everything found here out of chat; tell the player only what the checklist says to ask.

1. **Read ahead.** Read the whole section of the adventure the session is likely to reach, plus
   the next one in case the party moves fast. List what each scene needs: the map, creatures
   and their starting positions, props (bodies, wagons, furniture, light sources), hidden
   things, light level, and anything a creature does before the party arrives.
2. **Load the map.** Switch to the scene's map in Campaign OS 3D and set its lighting preset.
   Check the map against the adventure: missing props, wrong terrain, exits, and areas that
   need to block or allow sight. Write down anything that needs fixing in the 2D app (map fixes
   go through the 2D app, then Export to 3D, or the next export undoes them).
3. **Place the party.** Every party token must be on the map with full data: HP, AC, ability
   scores (uppercase keys), speed, attacks, spell slots and class resources. Place them in the
   marching order the player gave.
4. **Place hidden creatures.** Spawn the scene's creatures, hide them from players *before*
   moving them, and put them in their starting positions. Check each one's line of sight: an
   ambusher must be able to see what it is ambushing, and a hidden creature must be somewhere
   it can actually hide. Make any secret rolls (Stealth for hiding creatures) now, and record them.
5. **Check the player window.** Look at it as the player would. Nothing hidden should be on
   screen, and the log should not mention hidden creatures (Session 1 showed spawn, initiative
   and opportunity-attack lines leaking "something unseen").
6. **Ask the player.** Before play, ask in one message for anything only they can decide or
   fix: map corrections from step 2 (described without spoilers, e.g. "this scene needs a
   wagon and two horses on the road"), marching order, and any character choices pending.
   Wait for the answers.
7. **At the table.** Start the turn order with `next_turn` as soon as initiative is rolled, so
   the player window shows it. At the start of the player's turn, remind them what they have
   available (Rage, reactions, spell slots, class features). Keep combat narration to a line
   per turn and a short summary. Roll damage only after a hit is confirmed. Ask the player
   about anything that is theirs to decide (surprise affecting them, ties, reactions).
8. **After the session.** Use the End Session button in Campaign OS 3D if it's available,
   otherwise write the session log and world state by hand. Keep both player-safe.

## Running it solo
- The adventure is written for four or five level-1 characters. Scale each encounter to the actual
  party (fewer or weaker foes, more chances to talk, sneak or retreat) and say when a fight looks
  beyond them; companions, if any, can be DM-run.
- Keep DM knowledge out of narration: describe what the characters perceive, not room keys, trap
  locations or who is really behind what.
- Battle maps in Campaign OS 3D: the 3D board's fog of war hides unexplored areas, so a player-version
  map is safe to use whole. The existing "redbrand hideout" 3D map was built from the DM version --
  rebuild it over a player-safe image before that chapter (there's no player version in the folder).
- Record each session in `session-log.md` and keep `world-state.md` to what the party knows.
