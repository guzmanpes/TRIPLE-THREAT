# TRIPLE THREAT — Asset Manifest

This is the source-of-truth inventory for production assets. Items are planned until an asset file is committed and reviewed.

## Heroes
| Asset | Jack Hammer | Zip | Pixel |
|---|---:|---:|---:|
| Character concept / turnaround | Planned | Planned | Planned |
| Idle animation | Planned | Planned | Planned |
| Walk animation | Planned | Planned | Planned |
| Run animation | Planned | Planned | Planned |
| Jump / landing | Planned | Planned | Planned |
| Punch combo | Planned | Planned | Planned |
| Kick | Planned | Planned | Planned |
| Special move | Planned | Planned | Planned |
| Damage / knockdown | Planned | Planned | Planned |
| Victory / defeat | Planned | Planned | Planned |
| Character portrait | Planned | Planned | Planned |

## Enemies
- Security Bot — idle, walk, attack, hit, defeat
- Middle Manager — idle, walk, clipboard attack, call reinforcements, hit, defeat
- Ticket Bot — scan beam, charge, hit, defeat
- Commuter Drone — hover, projectile, hit, defeat
- Defective Bot — malfunction, roll, self-destruct
- Factory Guard — idle, walk, punch, hit, defeat
- Corporate Mascot — heavy walk, body slam, hit, defeat
- Shopping Cart Racer — charge, turn, crash
- Elite Security — block, combo attack, hit, defeat
- Prototype Battle Bot — multi-pattern attack, hit, defeat

## Bosses
1. The Manager — office-chair charge, clipboard slam, paperwork barrage, defeat
2. The Conductor — whistle stun, train hazard, ticket punch attack, defeat
3. HR-9000 — performance-review projectile, stapler volley, overtime phase, defeat
4. The Brand Ambassador — mascot spin, foam-hand slam, confetti blast, defeat
5. Director Vex — CEO phase, exosuit transformation, multi-phase attacks, ending

## Environments
- Downtown: skyline, storefronts, road, sidewalks, NEXUS advertisements, parking meters
- Subway: platforms, tracks, trains, turnstiles, signs
- Factory: assembly lines, conveyors, presses, machinery, warning lights
- Mall: storefronts, food court, escalators, kiosks, mascot displays
- NEXUS Tower: lobby, offices, laboratory, executive arena

Each environment needs distant, middle, and foreground layers, stage props, hazards, and transition art.

## Effects and UI
- Punch / kick impact, dust, jump landing, hit flash, knockback trail
- Explosions, gadget effects, projectiles, screen shake
- Triple Threat team finisher
- Title logo, menu panels, character select portraits
- Player HUD, boss HUD, combo counter, score, pause, results, game over
- Stage cards, story panels, ending and credits

## Audio
- Main menu theme
- Five stage themes and boss variations
- Punch, kick, jump, landing, hit, defeat, special, explosion
- Hero callouts, boss introductions, boss defeat stingers
- UI confirm / cancel, victory, game over

## Export standards
- Final sprites and UI: transparent PNG.
- Sprite sheets: consistent frame dimensions, aligned feet / pivots, documented frame order.
- Backgrounds: separate parallax layers.
- Audio: web-friendly compressed formats with source masters retained.
- All third-party assets must have documented licenses.


## First vertical-slice implementation note
Downtown currently uses procedural placeholder canvas graphics for heroes, NEXUS patrols, ticket bots, managers, and the boss. The asset entries above remain planned until final authored pixel-art files are added and reviewed. The Manager's boss presentation currently has a distinct larger silhouette and health bar, but still needs final sprite animation and audio.
