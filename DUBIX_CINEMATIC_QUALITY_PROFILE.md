# DUBIX Cinematic Visual Quality Profile

## Reference target
Use the user-provided lioness reference as a qualitative target: crisp subject detail (especially eyes/fur), naturally soft background bokeh, golden-hour highlights, rich but believable colors, and no muddy/pixelated/dirty appearance. This is a target style, not a guarantee that low-quality source footage can be reconstructed.

## Processing order
1. Probe source resolution, frame rate, aspect ratio, duration, and detect black/frozen frames.
2. Analyze sharpness/noise per scene; avoid applying deblur or aggressive sharpening to already sharp footage.
3. Crop bottom foreign-caption region only when subject-safe; no black bars, blur covers, or stretching. If crop would harm subject, require preview/manual crop adjustment.
4. Denoise conservatively to avoid plastic textures.
5. Apply scene-aware exposure, white balance, contrast, saturation, highlight/shadow balance. Keep skin/fur/greens plausible and avoid crushed blacks or clipped highlights.
6. Apply restrained sharpening only after denoise, with checks for halos, edge ringing, and artificial texture.
7. Optional upscaling to 3840x2160. Label upscale output clearly; do not imply recovered genuine source detail.
8. Optional frame interpolation to 60fps, only when the user chooses it and artifacts can be inspected. Preserve source playback speed; interpolation must not shorten duration. Reject ghosting, duplicate edges, warped moving subjects.
9. Render and verify metadata and sample frames. Reject quality settings that visibly degrade the source.

## Presets
- Reference/Cinematic: warm highlights, natural shadows, moderate contrast, rich but restrained saturation.
- Cool Clean: neutral/cool white balance with restrained teal, no cyan skin/fur.
- Natural: no stylized tint, balanced exposure and white balance.
- Off: no grading or enhancement.

## Quality checks
- Compare before/after frames at opening, midpoints, and ending.
- Inspect subject detail and motion artifacts at full-size.
- Verify 4K dimensions, target FPS (60 only if frame interpolation is enabled), original duration/speed, audio sync, subtitle-safe crop.
- Report source FPS, output FPS, and whether upscale/interpolation were used. If tests fail, do not claim final quality is verified.

## Honest limitations
Upscaling does not restore true details absent in the source. Deblur, denoise, sharpening, and interpolation can introduce artifacts; use conservative settings and provide preview/undo.
