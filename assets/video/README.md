# Prep videos

| File | Where it appears | Source name |
| --- | --- | --- |
| `hot.mp4` | Left card — "Hot · The Morning Ritual" | `Vertical_Caliente (2).mp4` |
| `iced.mp4` | Right card — "Iced · The Afternoon Reset" | `Vertical_Frío (2).mp4` |

Renamed from the uploaded filenames because spaces and accented characters
have to be percent-encoded in URLs and break inconsistently across browsers.

## These files are "faststart"

The `moov` atom (the index a player needs before it can render a single frame)
was at the **end** of both uploads. That forces a browser to download all ~23 MB
before playback begins — on cellular, a blank player for 30+ seconds, which is
exactly how people arrive here after scanning a business card.

Both files were remuxed so `moov` sits before `mdat`. This is lossless: the
media payload is byte-for-byte identical and the file size is unchanged, only
the index moved and the chunk offsets were rebased.

**If you re-export these videos, re-apply it** — most editors write `moov` last
by default:

```sh
ffmpeg -i input.mp4 -c copy -movflags +faststart output.mp4
```

## Format

- **Codec:** H.264 + AAC in `.mp4` — plays everywhere including iOS Safari.
- **Aspect ratio:** 9:16 vertical. The frames are built for it, so the same cut
  used for Reels/TikTok drops straight in.
- **Size:** ~23 MB each. They stream fine now, but re-encoding to 5–8 MB would
  noticeably improve start time on mobile data. Worth doing when there's an
  editor to hand.
- **Audio:** the steps are written beside each video, so the clips work muted.
  Don't rely on voiceover to carry the instructions.
