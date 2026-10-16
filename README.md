# SPACElogic Maker Space Arcade

Open `index.html` on the TV (serve it over https, e.g. GitHub Pages) and pick a game.

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

## Escape Protocol (finger pinch)
A 2D escape room controlled with one hand: pinch thumb and index finger to press, keep pinching to drag.
Pick one of three missions: **Orbital** (stop a space-station reactor), **Nexus Lab** (escape a rogue AI's lockdown) or **Abyss-7** (get out of a flooding deep-sea base).
Each mission has four puzzles in five minutes: sweep a UV scanner to find the code, rewire the circuit, tune a signal, then type the code and pull the lever.
Wrong moves cost time. Stand about 1 to 1.5 m from the camera so it can see your fingers. The narrator speaks; press **V** to mute. No camera? Use the mouse (click and drag).

## After every game
A short "Welcome to SPACElogic, presented by MAKER SPACE" screen with the Maker Space sign (`makerspace.jpg`) plays before the results.

## Wi-Fi QR in the racers lobby
Press **W** in the Circuit Racers lobby to enter the Wi-Fi name and password. A second QR code then appears so phones can join your network first.
It is saved only in that browser (localStorage), not in the repo, so the password is never published.
