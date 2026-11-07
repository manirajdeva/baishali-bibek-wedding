# Baishali & Bibek — Wedding Invitation Website

Live site: https://baishalibibek.online/

A static, mobile-first wedding invitation site (plain HTML/CSS/JS, no build step), hosted on GitHub Pages with a custom domain.

## Pages

| Page | File | Purpose |
|---|---|---|
| Cover | `index.html` | Landing / cover page |
| Main invitation | `invitation.html` | Intro animation, countdown, six-day timeline, quotes, accommodation, venues, RSVP |
| Mangalacharan | `mangalacharan.html` | Blessings and Beginnings (Wed 9 Dec 2026, Infinity Hall, Mayflower Hotel) |
| Mehendi | `mehendi.html` | The Henna Hangout (Fri 11 Dec 2026, Rooftop, Mayflower Hotel, Panbazar, Guwahati) |
| Sangeet | `sangeet.html` | The Musical Mehfil (Fri 11 Dec 2026, Rooftop, Mayflower Hotel) |
| Pre-Wedding | `prewedding.html` | Pre-wedding rituals at home (Sat 12 Dec 2026) |
| Haldi | `haldi.html` | Shades of Sunshine (Sun 13 Dec 2026, Opera De Augusta, Dhirenpara) |
| Wedding | `wedding.html` | Wedding ceremony (Sun 13 Dec 2026, 6:00 PM, Opera De Augusta) |
| Vidai | `vidai.html` | Vidai ceremony (Mon 14 Dec 2026, evening, from home) |
| Reception | `reception.html` | The Royal Rendezvous (Fri 18 Dec 2026, 7:00 PM onwards, Regal Gardeni) |

Event pages have a Back button that returns to the previous page and restores the exact scroll position. Each event page starts its music fresh when opened.

## Music

Audio lives in `audio/`. Each page plays its own looping track:
`invitation-music.mp3` (also Mangalacharan for now), `mehendi-music-from52.mp3`, `sangeet-music-from17.mp3`, `prewedding-music.mp3`, `haldi-music.mp3`, `wedding-music-from1m30.mp3`, `vidai-music.mp3`, `reception-music.mp3`.

## Release v1.1.0

Adds the full 9 – 18 December schedule, three new pages and a round of polish.

### Added
- **Mangalacharan, Vidai and Reception pages** with countdowns, step-by-step programme, venue, FAQ and calendar (Google / .ics) links, linked from new buttons on the invitation timeline.
- **Six-day timeline**: new Day One (9 Dec Mangalacharan) and Day Six (18 Dec Reception) with a dining-table Reception scene and new medal artwork.
- **Venue updates**: Rooftop at Mayflower Hotel (Mehendi, Sangeet), Infinity Hall (Mangalacharan), Opera De Augusta (Haldi, Wedding) and Regal Gardeni (Reception), including a third "Where We Gather" venue card.
- **Taglines** in a new gold small-caps style on the Mehendi, Sangeet, Haldi and Reception pages.
- **Two wedding quotes** on the invitation page and a **back-to-top** button.
- **Animated details**: rolling countdown digits, number-to-icon hover on the programme steps, animated Sangeet and Mehendi timelines.
- **Smooth page-to-page transitions** on web and mobile (with a fade fallback and reduced-motion support).
- **New music** for Haldi, Vidai and Reception.
- Credit line "Designed by @Deva" in the invitation footer.

### Changed
- Date range is now 9 – 18 December 2026 everywhere; every page has its own tab title.
- Event pages always start their music from the beginning.
- Removed the Back button from the main invitation page.

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
