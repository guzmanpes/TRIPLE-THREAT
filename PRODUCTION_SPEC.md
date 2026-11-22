# TRIPLE THREAT — Production Specification

## Locked production decisions
- Identity: The Unlikely Heroes
- Art direction: 16-bit retro arcade pixel art
- Humor: Wild, absurd comedy
- Heroes: Original characters — Jack Hammer, Zip, Pixel
- Difficulty: Classic arcade
- Orientation: Landscape
- Players: Three-player cooperative
- Target: Mobile Safari, hosted on GitHub Pages

## Product vision
Three ordinary people accidentally disrupt NEXUS Corporation's Perfect City 3000 launch and become the city's most wanted troublemakers. They fight through five absurd environments to stop Director Vex.

## Heroes
| Hero | Role | Weapon / style | Special |
|---|---|---|---|
| Jack Hammer | Heavy hitter | Oversized wrench; slow, high damage | Wrecking Ball |
| Zip | Speed fighter | Skateboard; fast combos and movement | Delivery Express |
| Pixel | Gadget specialist | Experimental backpack; crowd control | Glitch Grenade |

## Campaign
1. Downtown Disaster — Boss: The Manager
2. Subway of Doom — Boss: The Conductor
3. Factory of Fools — Boss: HR-9000
4. The Mall of Misery — Boss: The Brand Ambassador
5. NEXUS Headquarters — Final boss: Director Vex

Each stage includes an introduction, enemy waves, a stage hazard, a boss encounter, and a results screen.

## Core gameplay
- Landscape side-scrolling beat-'em-up with depth-lane movement.
- Directional movement, jump, punch, kick, and character-specific special.
- Individual player health and score contribution; shared team objective.
- Combo scoring, knockback, hit feedback, temporary pickups.
- Signature cooperative Triple Threat finisher.
- Classic arcade difficulty with readable enemy telegraphs and fair attack windows.

## Multiplayer
- One host and up to two joiners, each on a separate phone.
- Host-authoritative simulation over PeerJS/WebRTC data channels.
- Each player chooses a distinct hero.
- Handle late joins, disconnects, slot reuse, host departure, and reconnect messaging.
- Internet is required for PeerJS signaling; this is not offline LAN multiplayer.

## Visual rules
- Consistent 16-bit pixel scale and limited stage palettes.
- Distinct silhouettes and readable hero colors.
- Transparent PNG sprite sheets for final production art.
- Separate parallax background layers.
- Animated impact effects, hit flashes, dust, explosions, and comic-style score callouts.
- No generic rectangle-bodied placeholder characters in the release build.

## Audio
Original or properly licensed music and effects: menu theme, stage tracks, boss stingers, punches, kicks, jumps, specials, impacts, UI, victory, and defeat.

## Technical architecture target
Engine, input, player, combat, enemy AI, boss, stage, multiplayer, audio, UI, and campaign systems should be separated into maintainable modules while retaining static GitHub Pages deployment.

## Milestones
1. Visual identity and front-end foundation.
2. Three distinct playable heroes and responsive controls.
3. Hardened three-device multiplayer.
4. Complete Downtown vertical slice including The Manager.
5. Remaining four campaign stages and bosses.
6. Audio, story sequences, accessibility, performance, and real-device QA.

## Release acceptance
- Three physical iPhones can connect and play together.
- Landscape layout and touch controls work across supported screen sizes.
- All three heroes have distinct movement, combat, and specials.
- Five stages and five bosses can be completed.
- No game-breaking stuck controls, synchronization failures, or progression blockers.
- Full campaign can be completed from title screen through ending.

## Current implementation status
This specification is the target. Prototype features should be described as implemented only after code is committed and tested. The browser game has not yet been validated on three physical iPhones.


## Vertical slice status — Downtown Disaster
- Implemented in the browser prototype: opening banner, three enemy waves, three enemy archetypes, The Manager boss encounter, boss health bar and attack wind-up, victory / defeat states.
- Implemented art is procedural canvas placeholder art. Final authored sprite sheets, background art, music and sound effects remain production tasks.
- Multiplayer state snapshots include wave, boss, banner, and clear-state information.
- JavaScript syntax has been checked. Real-device gameplay, three-phone synchronization, combat balance, and full stage completion remain unverified.

## Visual pass — Downtown arcade presentation

- Reworked the three playable heroes with layered pixel-art silhouettes, face details, clothing highlights, signature gear, health pips, stride animation, and attack/special effects.
- Rebuilt NEXUS patrol, ticket-bot, manager, and boss artwork with clearer silhouettes, suit/armor details, hit flashes, and attack wind-up telegraphs.
- Replaced the basic Downtown skyline with a layered sunset cityscape, NEXUS tower signage, lit windows, street furniture, sidewalk and road markings.
- Updated the game frame, scanline treatment, menu panels, and hero-selection cards to reinforce the retro arcade cabinet direction.
- JavaScript syntax validation passed after the visual changes.
- Still unverified: actual Safari rendering on an iPhone, performance on older devices, and three-phone multiplayer playtesting. Art is still procedurally drawn in Canvas rather than final authored sprite sheets.
