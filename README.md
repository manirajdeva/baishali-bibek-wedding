# Baishali & Bibek — Wedding Invitation Website

Live site: https://baishalibibek.online/

A static, mobile-first wedding invitation site (plain HTML/CSS/JS, no build step), hosted on GitHub Pages with a custom domain.

## Pages

| Page | File | Purpose |
|---|---|---|
| Cover | `index.html` | Landing / cover page |
| Main invitation | `invitation.html` | Intro animation, countdown, event timeline, accommodation, venue, RSVP |
| Mehendi | `mehendi.html` | Mehendi ceremony invitation (Fri 11 Dec 2026, Mayflower Hotel, Panbazar, Guwahati) |
| Sangeet | `sangeet.html` | Sangeet invitation |
| Pre-Wedding | `prewedding.html` | Pre-wedding invitation |
| Haldi | `haldi.html` | Haldi invitation |
| Wedding | `wedding.html` | Wedding ceremony invitation (Day Three, Sunday, 6:00 PM, Opera De Agusta, Dhirenpara) |

Every page has a Back button that returns to the previous page and restores the exact scroll position and music state.

## Music

Audio lives in `audio/`. Each page plays its own looping track:
`invitation-music.mp3`, `mehendi-music-from52.mp3`, `sangeet-music-from17.mp3`, `prewedding-music.mp3`, `haldi-music-from19.mp3`, `wedding-music-from1m30.mp3`.

## Release v1.0.0

First tagged release. Highlights of the latest changes:

### Added
- **Highlighted invitation links** on the main invitation page (Mehendi, Sangeet, Pre-Wedding, Haldi, Wedding): solid maroon buttons with gold text and border, a soft pulsing glow, so guests notice they can open each event's invitation. On the dark Wedding card the button stays gold for contrast.
- **Pointer arrow** outside each button, pointing at it, dark maroon (light gold on the Wedding card), with a gentle nudge animation.
- **Floral garland** along the arch of the Wedding Ceremony card: marigold, gold and rose flowers with leaves, plus small sprigs down both sides. Drawn by a small script in `invitation.html` and re-fitted on resize (works with the rounder mobile arch).
- **New invitation music**: "Ranjha" flute cover, extracted from video to MP3 (128 kbps) and trimmed to start at 0:05; it loops from that point.

### Earlier in this release line
- Back button on every page; returns to the exact scroll position (including in-app browsers and every iPhone/Safari version).
- Mobile polish: readable button on the dark Wedding card; string lights scroll with the page.
- Removed unused PNG images and audio files.
- Custom domain `baishalibibek.online` (see `CNAME`).
- Deployment through GitHub Actions (`.github/workflows/pages.yml`).

## Run locally

```bash
python -m http.server 8765 --directory .
# open http://localhost:8765/invitation.html
```

## Deploy

Pushing to `main` runs the **Deploy site to GitHub Pages** workflow, which publishes the site to https://baishalibibek.online/.

## Notes

- Browsers may cache the old audio and files; hard refresh (Ctrl+F5) after a deploy.
- Do not commit source video files (e.g. the `.mp4` used to extract the music).
