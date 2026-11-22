# TRIPLE THREAT: NEXUS — Game Design Document

## Creative direction
- Genre: three-player cooperative side-scrolling arcade beat-'em-up.
- Platform: mobile Safari, three iPhones, one host and two joiners; static GitHub Pages hosting.
- Art: comic-book action, thick ink outlines, halftone textures, saturated pop-art colors, expressive faces, speed lines and impact lettering.
- Tone: funny, fast, ridiculous and energetic. Keep action readable on small phone screens.
- Story: NEXUS Corporation has bought the city. CEO Director Vex is converting public life into a corporate dystopia. Three heroes fight through the company's absurd security apparatus to expose Vex.

## Premise
NEXUS promised a brighter tomorrow. Now robots issue parking tickets, guards enforce mandatory fun, and every street corner has a subscription kiosk. Three heroes decide the city has had enough.

## Heroes
1. The Brawler — balanced close-range fighter; Ground Smash special. Broad silhouette, oversized gloves, warm yellow/orange palette.
2. The Speedster — fast movement and rapid combo chains; Lightning Rush special. Lean silhouette, cyan accents and motion streaks.
3. The Tank — slower, durable, heavy hits; Shockwave special. Stocky silhouette, magenta/red accents and oversized boots.
Names and final designs remain open for later selection.

## Five-stage campaign
1. Downtown — NEXUS street patrols; boss: The Franchise, a smug regional manager in powered armor.
2. The Subway — ticket scanners, turnstile bots and platform hazards; boss: The Conductor.
3. The Factory — conveyor belts and productivity machines; boss: HR-9000.
4. NEXUS Tower — executive security and office-floor hazards; boss: The Board.
5. Vex's Launch Party — a ridiculous product-launch arena; final boss: Director Vex and the NEXUS Prime exosuit.

## Core gameplay loop
Move through a scrolling stage, fight waves, earn score, collect temporary power-ups, defeat a stage boss, then advance. The team shares objectives; players retain individual health and score contribution.

## Combat pillars
- Responsive horizontal movement and depth-lane movement.
- Fast punch/kick chains, knockback, hit-stop, impact flashes and screen shake.
- Jump attacks, character-specific specials and cooperative combo finishers.
- Readable enemy telegraphs, varied enemy archetypes and multi-phase bosses.
- Clear feedback for damage, invulnerability, low health, joins and disconnects.

## Comedy and narrative
Short speech bubbles, fake corporate slogans, boss introductions, environmental jokes and punchy between-stage panels. Humor should be visual and brief so it never blocks combat.

## Presentation and progression
Title comic cover → character select → short story panel → stage → boss intro → results panel → next issue.
HUD: three distinct player health indicators, team score, stage title, boss health bar and special meter.
Sound direction: comic impacts, arcade percussion and short character callouts; add after core gameplay and mobile performance are stable.

## Development roadmap
### Milestone 1 — visual identity (in progress)
Comic-book palette, inked fighters/enemies, halftone city backdrop and NEXUS title/story introduction.
### Milestone 2 — hero identity and front end
Character selection, hero-specific stats/colors, story panels, stage title cards and persistent room-code display.
### Milestone 3 — combat feel
Combo chains, kick/jump attacks, hit-stop, knockback, special meters, power-ups and cooperative finishers.
### Milestone 4 — campaign systems
Scrolling stage camera, level boundaries, wave triggers, boss encounters, stage transitions and victory/defeat flow.
### Milestone 5 — multiplayer hardening
Reliable player identity and slot reuse, disconnect/reconnect handling, host-authoritative simulation, input throttling, latency feedback and three-device testing.
### Milestone 6 — polish
Sound, accessibility, pause/restart, onboarding, performance tuning and real-device QA.

## Technical constraints
- Keep the game deployable as static files on GitHub Pages.
- Browser multiplayer currently uses PeerJS signaling and WebRTC; internet is required for connection setup.
- Do not claim offline LAN support.
- Test on three physical iPhones in Safari before calling the build release-ready.

## Current status
This document defines the target game. The first visual/story code pass is next; the complete campaign, character selection, specials and boss fights are not yet implemented.
