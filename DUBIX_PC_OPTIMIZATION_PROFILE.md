# DUBIX PC-Specific Processing Profile

This profile is tuned for the user's Windows 11 laptop:
- CPU: Intel Core i5-10210U (low-power 4-core/8-thread class)
- RAM: 8 GB; keep DUBIX working set under ~6 GB where possible
- GPU: no dedicated GPU; CPU-only processing
- Storage: ~238 GB
- FFmpeg installed

## Recommended defaults
- Whisper: use small/CPU model by default; do not load multiple models simultaneously.
- Keep RAM target below 6 GB; unload speech/OCR models before video encode if practical.
- Limit FFmpeg threads to 2–4 (configurable); prefer fast presets to avoid thermal throttling.
- Source FPS: preserve source FPS by default. 60 FPS interpolation is optional and off by default on CPU-only hardware.
- 4K: optional upscale profile; default output should be source resolution or 1080p. 4K is export/upscale only and may be slow.
- Avoid GPU-only enhancement and heavy AI deblur/denoise dependencies as defaults.
- Audio fitting: cap voice speed to 1.10x; never speed video to fit speech.
- Subtitle crop: preview and subject-safe; no stretching, black bars, or blurred covers.
- Mirror: optional toggle, default off.
- Gold-blue cinematic border: optional toggle, default off, adjustable thickness.
- Colour: restrained exposure/contrast/saturation/white balance; default profile 'Natural Clean'. Avoid strong teal-orange LUT and over-sharpening.
- Denoise/sharpen: light filters only, optional and previewable.
- Export: H.264 MP4; CRF around 20–23, preset 'veryfast' default, AAC audio; ensure source duration unchanged.
- If 4K or 60fps jobs are slow, show progress and allow cancellation; don't freeze UI.
- Save presets and logs; check output dimensions/FPS/duration with FFprobe.
## Performance reality
4K upscale and 60fps interpolation on CPU-only i5-10210U can be very slow and may generate interpolation artifacts. Do not promise realtime or DSLR-original detail. 60fps interpolation remains opt-in; prefer native frame-rate output for a clean stable render.
