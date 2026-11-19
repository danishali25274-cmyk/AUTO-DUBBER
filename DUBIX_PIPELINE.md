# DUBIX pipeline

Windows desktop video dubbing pipeline based on Python, FFmpeg, Faster-Whisper, and Kokoro.

- Input: local video or yt-dlp-supported URL.
- Whisper translates source speech into English with timestamps.
- Translation review is recommended.
- Kokoro synthesizes selected English voice.
- Fit stage has a 1.10x maximum speed; lines that remain too long stop export rather than cut off.
- Original video is not sped up; export is bounded to source duration.
- English SRT is saved; optional burn-in is supported.
- Bottom subtitle strip crop defaults to 15%, zooming remaining frame; no black cover.
- Natural, cinematic warm, cool clean, and off grading options.
- Optional horizontal mirror; source/1080p/4K output selections.
- OCR inpainting is optional and can leave artifacts.

Current automated tests pass in Linux synthetic testing. Windows runtime, all Kokoro voices, real video workflows, long videos, OCR, and 4K on target hardware still need end-to-end verification.