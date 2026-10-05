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
