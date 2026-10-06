# Ti-Eye V0.3 — Change Log

## Samsung Galaxy A16 readiness
- Added A16-aware balanced performance profile.
- Targets the A16 rear camera at 1920×1080/30fps, with fallback to 1280×720 if necessary.
- Runs AI detection on a 640×360 analysis frame instead of full-resolution video frames.
- Reduced AI detection workload and recording bitrate for the phone-first prototype.
- Default tracking zoom changed to 1.15× for a wider safety margin.
- Added device profile and network telemetry.
- Added screen Wake Lock support to reduce accidental screen sleep during recording.
- Added landscape/fullscreen preparation for the match-recording screen.
- Added install-to-home-screen handling for supported mobile browsers.

## Tracking improvements
- Ball detector output is mapped back from the low-resolution AI frame to the full camera frame.
- Smoothed position estimation and short-horizon motion prediction retained for digital Auto Frame.
- Added more robust lost-ball handling and tracking telemetry.
- Preserved manual digital pan/tilt controls as a bridge to the future ESP32 motor system.

## Prototype boundary
- No ESP32, motors or ball-mounted sensor required.
- Physical camera movement is intentionally deferred.
- COCO-SSD remains a general-purpose `sports ball` detector and is not yet a football-specific trained model.
