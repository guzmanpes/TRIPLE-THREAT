# TRIPLE THREAT

A mobile-first, three-player co-op arcade beat-'em-up prototype for iPhone Safari.

## Play
1. Publish this repository with GitHub Pages (Settings → Pages → Deploy from a branch → main → /(root) → Save).
2. Open the published Pages URL on all three iPhones in Safari.
3. On the first phone, tap **HOST GAME** and share the six-character room code.
4. On the other two phones, tap **JOIN GAME**, enter the code, and connect.
5. Use the on-screen directional pad, JUMP, and PUNCH buttons. Keyboard controls also work.

## Networking notes
- Uses PeerJS with its public signaling service, so **internet access is required** to establish the room and connect peers. This is not an offline/LAN-only implementation.
- Gameplay data is sent over PeerJS/WebRTC data channels when the network allows a direct peer connection. Some restrictive networks may relay traffic.
- The host phone runs the game simulation. The host can accept two additional players.
- Keep the host Safari tab open while playing.

## Prototype status
This is a playable first build, not a native iOS app. It is designed for portrait/landscape Safari and touch controls. The visuals and combat are original simple arcade-style artwork drawn in Canvas.
