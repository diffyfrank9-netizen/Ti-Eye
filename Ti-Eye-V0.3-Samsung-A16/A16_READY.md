# Ti-Eye V0.3 — Samsung Galaxy A16 Ready

This version is tuned for the Samsung Galaxy A16 family as the first phone-only prototype.

## Recommended first setup
- Phone: Samsung Galaxy A16 4G or 5G
- Camera: rear/main camera
- Capture target: 1920×1080 at 30 fps
- AI analysis: 640×360 lightweight analysis frame
- Recording in AI Follow: 1280×720 at about 6 Mbps
- Tracking: digital auto-framing only (phone remains fixed on the stand)
- Hardware: no ESP32, motors, or ball sensor required yet

## Why this profile
The A16 family supports FHD 1920×1080 video at 30 fps. The app therefore does not request 4K. AI analysis is intentionally performed on a smaller frame so the camera can record separately without making the phone do full-resolution object detection on every frame.

## Install on the Samsung A16
1. Host this folder on an HTTPS website, or use a secure local development address.
2. Open the site in Chrome or Samsung Internet on the A16.
3. Grant camera and microphone permissions.
4. Use the browser's Add to Home screen / Install option. The app also shows an Install button when the browser exposes the install prompt.
5. Turn the phone to landscape and mount it firmly on the stand.

Do not open `index.html` directly from Downloads/File Manager. Camera access normally requires a secure context such as HTTPS or localhost.

## First field test
Start with a 10–15 minute training session rather than a full match.

1. Set the stand at a stable elevated position with as much of the pitch visible as possible.
2. Create a new match.
3. Confirm the preview says `1920×1080 · 30fps` (or a lower fallback if the browser cannot provide it).
4. Select `AI Follow`.
5. Start Half 1.
6. Watch `LOCK`, confidence and direction telemetry.
7. Compare the exported AI Follow video with the Full Pitch version.

## Current prototype limitations
- The ball model is still COCO-SSD general-purpose `sports ball` detection. It is not yet a football-specific model.
- AI Follow is digital cropping. The phone does not physically move.
- Video files are downloaded at the end of each completed segment and are not permanently stored inside the app database.
- Live streaming to the Tisini platform is not yet implemented.
- ESP32 pan/tilt control is intentionally deferred until phone-only tracking is proven.

## Next development target
The next major improvement should be a football-specific lightweight detector plus stronger tracking/prediction. After that, add ESP32 pan control as the first physical movement stage.
