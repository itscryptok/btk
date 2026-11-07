# BTK Synergy Works

Static website for **BTK Synergyworks LLC** — network infrastructure installation
and IT support, serving Dallas–Fort Worth and surrounding areas.

Live: https://btk.onrender.com/

## What this is

A faithful rebuild of https://www.btksynergywork.com as a multimedia static site:
single page (hero carousel, services, about, process, quote banner, contact form),
plus a password-only admin panel at `/admini`.

- **Hero carousel** — four cinematic images (`assets/hero-*.jpg`), auto-advance,
  dots/arrows, swipe, keyboard support.
- **Contact / quote form** — the site's only form. Submissions are saved in the
  visitor's browser (`localStorage`, key `btk_submissions`) and shown in a popup
  above the form. Nothing is emailed. Server-side submission handling comes with
  the later webapp phase.
- **Admin panel (`/admini`)** — password-only. Shows all form submissions stored
  in that browser (list, search/filter, mark New/Contacted, delete, CSV export).
  Until the server phase, submissions are visible only in the browser they were
  made in.

## Admin password

Set `ADMIN_PASSWORD_HASH` in `admini/index.html` to the SHA-256 hex of the chosen
password (the login checks via `crypto.subtle`, never plaintext). While the hash
is empty, the panel shows "Admin password not set yet" and nothing else.

## Deploy

Render static site `btk` (Cryp's workspace), auto-deploys from `main` in this repo.
Publish directory is the repo root; no build command.

## Branding

Logo: `assets/btk-logo.jpg` (blue globe + RJ45 plug, "GLOBAL CONNECTION.
LOCAL EXCELLENCE."). Colours: dark navy + royal blue + sky-blue accents.
