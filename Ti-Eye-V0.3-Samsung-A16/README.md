# Ti-Eye V0.3 — AI Football Camera Prototype

Ti-Eye is a low-cost phone-first football camera prototype. The first physical prototype uses only a Samsung Galaxy A16 and a stable stand.

## What this version does
- Uses the rear phone camera.
- Targets 1080p/30 capture for Samsung A16.
- Runs lightweight AI analysis on a smaller 640×360 frame.
- Detects a `sports ball` with COCO-SSD.
- Smooths ball position and estimates movement.
- Predicts a short-horizon ball position.
- Creates a digital AI Follow crop while the phone stays fixed.
- Supports Full Pitch recording for comparison.
- Keeps score, clock, goals, cards, fouls, substitutions, chances and highlights.
- Stores match metadata locally using IndexedDB with localStorage fallback.
- Keeps the phone screen awake while a match is recording when Wake Lock is available.
- Supports PWA installation to the phone home screen.
- Includes manual digital framing controls for future physical pan/tilt work.

## Important: this is a phone-first prototype
Do not buy motors, an ESP32, a ball sensor or a Raspberry Pi yet. First prove that the phone can detect and follow the football digitally from a fixed stand.

## Samsung A16 profile
The app detects the A16 family where the browser exposes the device model and uses a balanced profile:
- 1920×1080/30fps camera target
- 640×360 AI analysis
- around 190 ms minimum detection interval
- 1280×720 AI Follow output
- around 6 Mbps recording target

The A16's rear camera is officially specified for FHD 1920×1080 at 30fps.

See `A16_READY.md` for the first field-test procedure and installation notes.

## Secure camera access
Camera access requires a secure context. Use HTTPS or localhost. Do not expect `file://` opened directly from the phone's file manager to provide camera access.

## AI model
Current detector: COCO-SSD `lite_mobilenet_v2` with the `sports ball` class. The model is a prototype detector and should later be replaced with a football-specific lightweight model trained on real match footage.

The TensorFlow.js and COCO-SSD scripts are loaded from CDN and may require one internet-connected launch before the browser can cache the assets.

## Future hardware path
Phone AI → ESP32 → pan motor → pan/tilt mount.

The current app already contains the digital framing logic and manual controls needed to test the control concept before physical hardware is added.
