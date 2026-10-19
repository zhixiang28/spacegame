# SPACElogic Maker Space Arcade

Open `index.html` on the TV (serve it over https, e.g. GitHub Pages). Staff press **Start the experience** once; after that visitors run everything themselves.

## Controls for visitors (made for 1 to 2 metres from the screen)
- **Point and hold still.** Raise one hand and point at the screen; hold it still on a button for about a second to select it (a ring fills). No finger detail is needed, so it works at normal standing distance.
- **One player is locked in.** The camera may see several people, but it locks onto the person standing closest to the middle (and close enough, about 3 m or less) and keeps following that same person, so people walking past or watching are ignored. They show dimmed in the camera preview. If the player leaves for about 2.5 s the lock is released; the welcome screen always starts fresh.
- **One hand points, and it stays the same hand.** The raised hand is used; the other must be clearly higher for 0.7 s to take over, so left and right do not flicker. The preview shows which hand is active.
- In Escape Protocol puzzles: *tap* = hold on a target; *grab* = hold on a handle, move it, hold still again to let go; some puzzles need no click at all (circle a wheel, sweep a sonar, move your hand up and down to pump).
- The pose model is the accurate "full" one and switches to the fast "lite" model by itself on slow computers (see `CFG.model`).
- A welcome screen invites people in; after 45 s with nobody around the menu returns to it. The mouse always works.

## Circuit Racers (phones as steering wheels)
1. Pick **Circuit Racers** on the TV. A QR code appears in the lobby.
2. Each player scans it with their phone camera, taps **Enable steering**, and holds the phone sideways like a wheel.
3. Tilt to steer. Left pedal = brake, right pedal = gas (auto-gas is on by default), **NITRO** button for a boost.
4. Player 1 can press **START RACE** on their phone, or use the TV (hand cursor / mouse / Enter).

- Up to 4 phones, split-screen on the TV. Empty seats are filled by CPU racers (6 cars total).
- Pick up gears to refill nitro. Toolboxes slow you down.
- No phone? Keyboard: arrows/WASD to drive, space for nitro.
- Phone to TV link is peer-to-peer (WebRTC via the free PeerJS relay). Both need internet access.
  To use your own relay add `?signal=host:port` (or `host:port:s` for https) to the TV URL.
- Phone settings (gear icon): auto-gas, invert steering, touch wheel fallback, re-centre.

## Filament Slice (hand tracking)
One player at a time: the camera follows whoever stands in the middle of its view and ignores friends watching at the sides. Swipe both hands (or the mouse) fast through flying filament spools (+10) and circuit boards (+15). Keep a combo going for up to x5.
Avoid the red-hot nozzles: each one you slice costs a power cell (3 lives). A shift lasts 75 s.

Files: `index.html` (TV: menu, Maker Run, Circuit Racers), `controller.html` (phone).

## Full screen and install
- The TV page goes full screen when you press **Start the station** (press **F** to toggle).
- In Chrome or Edge, use **Install as an app** on the start screen (or the install icon in the address bar) to get a desktop icon that opens full screen with no browser bars. Needs https.

## Escape Protocol (point, hold and move)
A 2D escape room controlled with one pointing hand and your body (see the controls above).
Pick one of three missions: **Orbital** (stop a space-station reactor), **Nexus Lab** (escape a rogue AI's lockdown) or **Abyss-7** (get out of a flooding deep-sea base).
Each mission has its own five puzzles in seven minutes, mixing a pointing hand with full-body moves (seven minutes):
- **Orbital**: UV scanner search for the code, rotate pipe tiles to route coolant, **lean your body** to keep the spinning station in the green, flip mirrors to aim a laser into the core, then keypad + lever.
- **Nexus Lab**: repeat NOVA's light sequence, rewire the bio-lock, **copy NOVA's body-scan poses** (arms up, arms out, one arm up), draw the leaked unlock pattern, then hold the override charge while dodging NOVA's scanner beam.
- **Abyss-7**: turn three valve wheels shut, ping the sonar to find the code buoys, **swim with big arm strokes** to the airlock, tune the rescue frequency, then keypad + pump the release.
Wrong moves cost time. Stand about 1 to 1.5 m from the camera so it can see your fingers. The narrator speaks; press **V** to mute. No camera? Use the mouse (click and drag).

## After every game
A short "Welcome to SPACElogic, presented by MAKER SPACE" screen with the MAKER SPACE logo (drawn in code, no image file) plays before the results.

## Wi-Fi QR in the racers lobby
Press **W** in the Circuit Racers lobby to enter the Wi-Fi name and password. A second QR code then appears so phones can join your network first.
It is saved only in that browser (localStorage), not in the repo, so the password is never published.
