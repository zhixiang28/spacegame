# SPACElogic Makerspace Arcade

Open `index.html` on the TV (serve it over https, e.g. GitHub Pages). Staff press **Start the experience** once; after that visitors run everything themselves.

## Controls for visitors (big body movements, 1 to 2 metres from the screen)
- **Menus: lean and raise both arms.** Lean left or right to move the gold highlight, raise **both arms** above your head for about 0.7 s to select. The first arms-up just wakes the highlight. Keyboard arrows + Enter and the mouse also work; pointing a hand and holding still still works as a backup.
- **One player is locked in.** The camera may see several people, but it locks onto the person standing closest to the middle (about 3 m or less) and keeps following them, so people walking past or watching are ignored. They show dimmed in the preview. If the player leaves for about 2.5 s the lock is released.
- **Escape Protocol uses the whole body**: lean, squat, jump, arms up / out / one arm, swing arms, step into big floor zones. Poses are shown as stick-figure symbols, not finger gestures.
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

## Filament Slice (arm swipes)
One player at a time: the camera follows whoever stands in the middle of its view and ignores friends watching at the sides. Swipe both hands (or the mouse) fast through flying filament spools (+10) and circuit boards (+15). Keep a combo going for up to x5.
Avoid the red-hot nozzles: each one you slice costs a power cell (3 lives). A shift lasts 75 s.

Files: `index.html` (TV: menu, Maker Run, Circuit Racers), `controller.html` (phone).

## Full screen and install
- The TV page goes full screen when you press **Start the station** (press **F** to toggle).
- In Chrome or Edge, use **Install as an app** on the start screen (or the install icon in the address bar) to get a desktop icon that opens full screen with no browser bars. Needs https.

## Escape Protocol (big movements)
A 2D escape room played with your whole body (arms, lean, squat, jump). Pick one of three missions: **Orbital** (stop a space-station reactor), **Nexus Lab** (escape a rogue AI's lockdown) or **Abyss-7** (get out of a flooding deep-sea base). Each mission is 8 minutes with its own puzzles and a four-pose code made of stick-figure symbols (arm left / arm right / both arms up / T-pose).
Puzzles mix big-zone switches, aiming, pulling, move sequences (lean, squat, jump), corner cables, arm-drawn patterns, arm tuning, pumping and pose copying. Wrong moves cost time. The narrator speaks; press **V** to mute. No camera? Use the mouse or arrow keys.

## After every game
A short "Welcome to SPACElogic, presented by MAKERSPACE" screen with the MAKERSPACE logo (drawn in code, no image file) plays for about 2.5 seconds and then closes by itself, before the results.

## Wi-Fi QR in the racers lobby
Press **W** in the Circuit Racers lobby to enter the Wi-Fi name and password. A second QR code then appears so phones can join your network first.
It is saved only in that browser (localStorage), not in the repo, so the password is never published.
