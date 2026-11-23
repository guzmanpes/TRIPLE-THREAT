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
- Floating left-side virtual joystick for movement and depth-lane positioning; joystick direction maps to clear digital movement thresholds.
- Three right-side touch actions: ATTACK (alternating punch/kick combo), JUMP, and character-specific SPECIAL.
- Multi-touch pointer handling with pointer capture and release cleanup for cancel/lost-capture/blur events; keyboard controls remain available for desktop testing.
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

## Vertical slice expansion — Subway of Doom

- Added a second playable campaign stage that unlocks after defeating The Manager. The host taps the game field (or presses Enter) on the Downtown clear screen to board the train; the stage change is synchronized through host snapshots to connected players.
- Added a dedicated subway station environment with route signage, platform edge, track pit, station lighting, and tunnel.
- Added three Subway enemy waves using commuter security, ticket bots, and transit drones.
- Added The Conductor as the Subway boss, with a distinct transit-official pixel-art silhouette and boss health bar.
- Added a repeating train hazard with an approach warning, moving train, collision damage, and jump-to-evade behavior.
- Added Subway clear and campaign-demo-complete states. Stages 3–5 are not implemented yet.
- JavaScript syntax validation passed. This update has not been tested on physical iPhones or with three simultaneous devices; multiplayer synchronization is implemented in snapshots but remains unverified in live play.


## Vertical slice expansion — Factory of Fools

- Added a third playable campaign stage that unlocks after defeating The Conductor. The host taps the game field (or presses Enter) on the Subway clear screen to enter the Factory; the stage change is synchronized through the existing host snapshots.
- Added a dedicated NEXUS Industries factory environment with industrial framing, overhead machinery, warning lights, conveyor markings, and a hydraulic press.
- Added three Factory enemy waves, reusing the shared 8-bit NEXUS trooper silhouette with the Factory's toxic-green palette.
- Added the hydraulic press hazard: a warning phase, timed press-down phase, collision damage to grounded players in the marked zone, and a clear timing cue.
- Added HR-9000 as the Factory boss, with a new chunky pixel-art robot design, a 58 HP boss bar, and a distinct green Human Resources label.
- Added Factory victory messaging and updated the stage HUD and campaign progression.
- JavaScript syntax validation passed after the update. The new stage has not been physically tested on iPhones or with three simultaneous devices; the multiplayer stage transition and hazard timing remain to be verified in live play.


## Touch control redesign — floating joystick

- Replaced the four-way D-pad with a floating left-side joystick that centers where the player's thumb first touches, then tracks within a bounded radius.
- Simplified the right-side action cluster to ATTACK, JUMP, and SPECIAL. ATTACK alternates between punch and kick animations to preserve combat variety without a fourth button.
- Kept movement mapped to the existing directional input model so host-authoritative movement and multiplayer input snapshots remain compatible.
- Added pointer capture and cleanup for pointer up/cancel/lost-capture and window blur. JavaScript syntax validation passed.
- Not yet verified on a physical iPhone: thumb ergonomics, simultaneous joystick-plus-action touches, and behavior across Safari versions still require device testing. If the joystick feels imprecise in play, the next adjustment should be threshold/radius tuning rather than assuming analog movement is better.


## Vertical slice expansion — The Mall of Misery

- Added a fourth playable campaign stage, unlocked after defeating HR-9000 in the Factory.
- Added a dedicated neon-lit NEXUS Mega-Mall environment with storefronts, food-court signage, and mall advertising.
- Added three Mall enemy waves: mall security troopers, aggressive shopping carts, and promotional mascots.
- Added the runaway shopping-cart stage hazard, with lane-based targeting, collision damage, and a jump-to-evade window.
- Added The Brand Ambassador as the fourth boss, with a distinct mascot-style pixel-art design, 68 HP, boss health bar, and customer-experience label.
- Added Mall victory messaging and campaign progression from Factory to Mall. The final Headquarters stage is still not implemented.
- Updated multiplayer snapshots to synchronize the active Mall hazard to joined players.
- JavaScript syntax validation passed after the update. Gameplay balance, visual rendering, and multiplayer synchronization remain unverified on physical iPhones.
