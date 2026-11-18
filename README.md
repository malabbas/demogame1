# Pizza Rush — Playable Campaign Concept

A retro arcade game and interactive marketing concept by **Mahmood Alabbas**. Collect pizzas while dodging moving traffic, with a handheld-console look, sound effects, and controls for desktop and touch screens.

**[Play Pizza Rush](https://demogame1.pages.dev/)** · [Source code](https://github.com/malabbas/demogame1)

The demo link is the existing Cloudflare Pages deployment referenced by the Makoplay landing page. The local preview below works without a hosting account.

## The idea

Turn a campaign message into a small, playable experience: a short challenge, immediate feedback, and a memorable replay prompt. The pizza theme demonstrates how a brand could use a browser game as an engagement touchpoint.

This is an independent portfolio concept, not a commissioned campaign or an official Domino's Pizza product. The win message is part of the demo; there is no real prize or redemption process. The earlier “AI campaign” name describes the creative concept, not an AI service running inside the game.

## What this project demonstrates

- A complete game loop with start, play, win, lose, and retry states.
- HTML Canvas rendering, a pixel sprite, collision detection, and randomized obstacles and collectibles.
- Keyboard and touch input, responsive sizing, and coordinated sound effects.
- Campaign storytelling through the challenge, reward message, and branded retry phrase.
- A small, dependency-free front end that can be hosted as a static site.

## How to play

| Action | Controls / rule |
| --- | --- |
| Start | Press Enter or Space, or click/tap the game screen. |
| Move | Arrow keys, WASD, or the on-screen directional buttons. |
| Win | Collect 10 pizzas. Traffic speeds up as the score increases. |
| Avoid | Eight moving traffic obstacles. A collision returns the player to the starting position. |
| Lose | Five traffic collisions end the round. |
| Retry after losing | Type `Pizza Pizaa` exactly as shown, then press Enter or Submit. The spelling is intentional and case-sensitive. |
| Replay after winning | Press Enter/Space or select Play Again. |

## Run locally

No package installation, API key, or build step is needed. From a cloned checkout:

```bash
git clone https://github.com/malabbas/demogame1.git
cd demogame1
python3 -m http.server 8080 --bind 127.0.0.1
```

Open [http://localhost:8080](http://localhost:8080). Stop the preview with **Ctrl+C**. A current browser and Python 3 are sufficient; any equivalent static-file server also works.

## Implementation

Everything is in [`index.html`](index.html): page markup, responsive CSS, and plain JavaScript. A `requestAnimationFrame` loop updates movement and renders the 320 × 288 canvas. Axis-aligned collision checks handle traffic and pizza collection. Separate keyboard and touch state allow both input methods to drive the same player.

The game has no application backend, account system, analytics integration, persistent scores, or runtime AI dependency. Scores and progress reset when the page reloads.

## Assets and current limits

- Google Fonts supplies **Press Start 2P**; a monospace fallback is configured.
- The favicon, pizza image, brand reference image, music, and sound effects load from public Supabase Storage URLs. These URLs are public asset addresses, not API credentials. Availability and permission to reuse those assets are separate from the game code.
- Some browsers restrict audio until the first interaction. Blocked audio does not prevent gameplay.
- This is an early canvas prototype. The page exposes text instructions and labeled controls, but the game itself is visual and does not yet provide a full screen-reader experience, pause control, or saved progress.
- Brand imagery and externally hosted audio are concept references; this repository does not grant rights to those third-party assets.

## Publish the demo

The current public demo is hosted on [Cloudflare Pages](https://demogame1.pages.dev/). Deploy this directory as a static site with no build command and the repository root as the output directory. An alternative is GitHub **Settings → Pages → Deploy from a branch**, choosing the branch containing `index.html` and **/ (root)** as the folder; use the resulting Pages URL in your portfolio.

No secrets are needed to publish this project. Keep environment files and local tool output out of commits using the included [`.gitignore`](.gitignore).
