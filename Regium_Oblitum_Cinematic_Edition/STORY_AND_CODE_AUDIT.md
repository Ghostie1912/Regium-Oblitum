# Story and code audit — Regium Oblitum

Source: original ten-chapter manuscript supplied by the author. No additional canon is assumed.

## What was wrong in the previous versions

- The normal cave automatically advanced on a timer and did not allow Velvid to investigate the footprints herself.
- The original maze entrance/reveal was missing or was handled in dialogue rather than a separate scene.
- The sealed entrance came too quickly without first showing the footprints and a decision to turn around.
- Story thoughts appeared under Velvid's character portrait instead of being visually distinct, speakerless narration.
- The group split, Ashlyn crying, the watcher shifts, and the other team's marks were heavily condensed.
- Velvid and Levi's watch conversation occurred without visual continuity: Evelyn and Astra appeared upright instead of sleeping on the vines.
- Choices were positioned at moments without meaningful relationship to the action; some previous choices demanded emotional decisions immediately after a death, which wasn't in the story.
- The game added collecting constellation fragments, an objective not present in the original sea chapter.
- Key scenes reused generic maze backgrounds, and visual flashback panels did not evolve with the story.
- The old code mixed story advancement, rendering, and dialogue callbacks with fragile state-dependent background logic. The revised build has separate scene entry functions, world rendering, interaction state and dialogue/choice overlays.

## Manuscript-to-game map

| Chapter | Source events | Playable / staged implementation |
|---|---|---|
| 1 · To You 100 Years Later | Velvid narrates Aurevullem legend, expedition | Audio-only prologue; optional guild exploration introduced as game framing, rather than asserted as original canon |
| 2 · Going Underground | Three days later; normal cave; footprints; impossible maze; retreat | Arrive after three days; walk cave, examine clues, discover and follow prints, explore a deeper passage, inspect enormous walls |
| 3 · The Lost Ways | Missing entrance; debate; rest; argument over splitting | Sealed entrance, all key characters, long dialogue, Welt's suggestion to mark routes |
| 4 · Maze Runner | Two groups; Ashlyn crying; enormous spider; vine hiding; night watch; Levi exchange; trail marks | Visual team split, Ashlyn interaction, maze walk, chase, hiding, separate night-camp with sleeping sprites, Levi dialogue, inspect trail |
| 5 · The lost team | Aaron/Welt return; Astra's suspicion; Aaron's wound; Ashlyn missing | Reunion staging with knife and wound, group dialogue, follow markings |
| 6 · The Spark That Ran Out of Time | Ashlyn's death; field of flowers; burial; inscription | Dedicated discovery, walk to flowers, gravestone, 'seven came, six left' |
| 7 · The Exit | Staircase down; Aaron fears creature; Welt scouts and returns to ruined camp | Staircase scene and playable visual memory beats with text, shoulder check |
| 8 · The Sea of Constellation | Luminescent subterranean sea; empty boats; teams board separately | Dedicated scene, top-down two-boat navigation with original passengers |
| 9 · Everyone's Crazy | Knife-handed monster hints; memories reflected; family references; narwhal cry | Conversation and different water-vision staging, boat exploration |
| 10 · Sir Neighs-a-Lot | Narwhal appears; boat stops; Aaron jokes | Dedicated narwhal scene; canonical cliffhanger, no invented ending |

## Canon / design distinction

The guild's layout and optional early character conversations, cave props, visual design, and small staircase preparation choice are game adaptations to support interaction. They are *not* presented as missing lines from the manuscript. The game's actual timeline remains in the order of the chapters. The author has only written two major environments so far (maze and sea), and three remaining major levels and multiple endings cannot be faithfully scripted yet.

## Testing

- Node.js syntax check on `game.js`.
- JavaScript VM smoke test rendering 18 scene states and invoking their scene initialization handlers.
- ZIP archive integrity check.
- Browser-level screenshot testing was attempted but blocked by the execution environment. Real-user browser QA is still recommended.
