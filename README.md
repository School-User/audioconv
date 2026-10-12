# audioconv

Convert audio files — or whole folders of mixed formats — to one format. A small bash wrapper around [ffmpeg](https://ffmpeg.org). Everything runs locally; nothing is uploaded.

## Install

Needs `ffmpeg` (e.g. `sudo pacman -S ffmpeg` / `sudo apt install ffmpeg` / `brew install ffmpeg`).

```bash
curl -o ~/.local/bin/audioconv https://raw.githubusercontent.com/School-User/audioconv/main/audioconv
chmod +x ~/.local/bin/audioconv
```

## Usage

```bash
audioconv mp3 song.flac           # -> song.mp3
audioconv flac *.wav              # several files
audioconv mp3 ~/Music/mixed       # whole folder, recursive, any mix of formats
audioconv m4a video.mp4           # pull the audio out of a video
```

- Output is written next to each source as `name.FORMAT`; originals are kept.
- Existing files are never overwritten, so re-running only converts what's new.
- In folders, files already in the target format and non-audio files (cover art, text) are skipped.
- Any format ffmpeg can write works: mp3, wav, flac, ogg, opus, m4a, …
