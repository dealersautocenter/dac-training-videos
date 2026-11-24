# Dealers Auto Center training videos
Public folder for finished dealer training videos. Demo data only (made-up 'Demo Motors'). Never put code, secrets, real dealer or customer data here.

## Rules
- main = LIVE. The Dealers Auto Center server reads manifest.json on main every few minutes and shows new or changed videos to dealers.
- Nobody pushes to main directly. Open a pull request from a branch codex/<slug>. A review merges it when it passes.
- videos/<guide-id>.en.mp4 and videos/<guide-id>.es.mp4 : H.264 + AAC MP4, 1280x720, at most 25 MB each, 'faststart' (moov atom first).
- sheets/<guide-id>.<lang>.jpg : one contact sheet per video (a grid of about 12 frames with timestamps) so a reviewer can check the screens without playing it.
- scripts/<guide-id>.<lang>.txt : the narration text spoken in the video.
- manifest.json : one entry per guide id, see below. ver goes up by 1 every time that file changes.

## manifest.json shape
{ "add-inventory": { "title": "Adding a vehicle", "secs": 104, "ver": 1, "file": "videos/add-inventory.en.mp4", "sha256": "<hex>", "bytes": 12345678, "es": { "title": "Agregar un vehiculo", "secs": 110, "file": "videos/add-inventory.es.mp4", "sha256": "<hex>", "bytes": 12345678 } } }
