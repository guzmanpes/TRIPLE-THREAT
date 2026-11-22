# TRIPLE THREAT: NEXUS — Game Design Document

## Creative direction
- Genre: three-player cooperative side-scrolling arcade beat-'em-up.
- Platform: mobile Safari, three iPhones, one host and two joiners; static GitHub Pages hosting.
- Art: 16-bit retro arcade pixel art, bold silhouettes, limited palettes, animated impact effects and layered scrolling environments.
- Tone: wild, absurd comedy. Visual jokes and short dialogue should never interrupt combat.
- Identity: The Unlikely Heroes — three ordinary people accidentally become the city's only hope.
- Difficulty: classic arcade; challenging but fair.
- Orientation: landscape.
- Heroes: Jack Hammer, Zip, and Pixel.

## Premise
NEXUS Corporation launches THE PERFECT CITY 3000, promising to eliminate crime, traffic, bad manners, wasted time, and unnecessary happiness. A catastrophic system failure is accidentally triggered by three strangers trying to get free promotional merchandise. NEXUS labels them the three most wanted people in the city. They fight back.

## Heroes
1. Jack Hammer — former mechanic and heavy hitter. Oversized wrench. Slow movement, high damage, powerful knockback. Special: Wrecking Ball.
2. Zip — reckless delivery courier and speed fighter. Skateboard. Fast movement and combo chains. Special: Delivery Express.
3. Pixel — eccentric inventor and gadget specialist. Experimental backpack. Crowd control and status effects. Special: Glitch Grenade.

## Campaign
1. Downtown Disaster — NEXUS street patrols; boss: The Manager, a corporate middle manager in a powered office chair.
2. Subway of Doom — ticket bots, commuter drones and train hazards; boss: The Conductor.
3. Factory of Fools — conveyor belts and productivity machines; boss: HR-9000.
4. The Mall of Misery — shopping cart racers, mutant mascots and automated food courts; boss: The Brand Ambassador.
5. NEXUS Headquarters — elite security and experimental technology; final boss: Director Vex and the Perfect City control machine.

## Core gameplay
Move through a scrolling stage, fight waves, build combos, collect temporary power-ups, defeat a boss, and advance. Each hero has a distinct combat identity. Players share objectives while retaining individual health and score contribution.

## Combat pillars
- Horizontal movement and depth-lane movement.
- Punch combos, kicks, jump attacks, grabs / throws, knockback and hit feedback.
- Character-specific specials with cooldown or meter.
- Readable enemy telegraphs and multi-phase bosses.
- A cooperative Triple Threat finisher that rewards coordinated play.
- Clear feedback for damage, invulnerability, low health, joins and disconnects.

## Comedy
A robot displays “YOUR FEEDBACK IS IMPORTANT TO US” after being punched. Defeated managers drop performance reviews. Vending machines dispense weapons. Bosses call mandatory breaks. Director Vex shouts about quarterly earnings.

## Presentation
Title screen → character selection → opening story panels → stage → boss intro → results → next stage → ending. HUD includes three player health indicators, team score, stage title, combo counter, and boss health.

## Technical constraints
- Static GitHub Pages hosting.
- PeerJS/WebRTC for browser multiplayer; internet required for signaling.
- No offline LAN claim.
- Must be tested on three physical iPhones in Safari before release.
- Landscape-first responsive interface with safe-area handling and touch controls.

## Production roadmap
1. Visual identity and front-end foundation.
2. Three distinct heroes, animation sets, and mobile combat controls.
3. Reliable three-device multiplayer and character selection.
4. Complete Downtown vertical slice and The Manager boss.
5. Remaining four stages and bosses.
6. Audio, story sequences, performance, accessibility, and real-device QA.

## Status
This document defines the approved target. A feature is not considered complete until it is implemented, committed, and tested.
