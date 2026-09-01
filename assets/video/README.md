# Prep videos

Drop the two clips here with these exact filenames:

| File | Section |
| --- | --- |
| `hot.mp4` | Left card — "Hot · The Morning Ritual" |
| `iced.mp4` | Right card — "Iced · The Afternoon Reset" |

Until they exist, each card shows a branded "Video coming soon" panel instead
of a broken player. No code change is needed when you add them.

## Format

- **Codec:** H.264 video + AAC audio in an `.mp4` container (plays everywhere,
  including iOS Safari).
- **Aspect ratio:** 9:16 vertical — the frames are built for it, so the same
  cut used for Reels/TikTok drops straight in.
- **Size:** keep each under ~10 MB. These are served from the repo, and a heavy
  file is a slow page on mobile data, which is how most people arrive here
  (they scanned a business card).
- **Audio:** the steps are written beside each video, so the clips work fine
  muted. Don't rely on voiceover to carry the instructions.

If a clip has to exceed ~25 MB, host it on a CDN or Vimeo instead and swap the
`<source src="...">` in `index.html` rather than committing it.
