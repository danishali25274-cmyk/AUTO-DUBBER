# AutoDubber Kokoro / DUBIX

Windows desktop/video dubbing project based on Python, Whisper translation, Kokoro TTS, and FFmpeg.

## Project archive
The repository includes `AutoDubber_Kokoro_Ready_Complete.zip`. Extract it on Windows, then run `install.bat` followed by `start.bat`.

## Tests
The latest available project archive was syntax-checked and its included tests were run in a Linux container:
- Python compile checks: PASS
- Unit/integration tests: 8 passed

These checks are not a substitute for testing the full app and its models on Windows.

## Scope
Do not treat subtitle cropping, visual grading, mirror, 4K upscaling, or every GUI workflow as complete unless implemented and tested in the current code.
