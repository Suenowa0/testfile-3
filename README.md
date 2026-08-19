# Her Little Universe — A Birthday Website

A two-page, password-protected birthday website:

- **Page 1 (`/`)** — a cinematic hero: a starfield sky, her name in lights, a
  typewriter message, her portrait, and a "Begin the Journey" button.
- **Page 2 (`/experience`)** — a password-locked full experience: a living
  countdown since her birth date, a memory timeline, a photo gallery, a
  letter in an envelope, reasons she's loved, a memory quiz, a prize wheel,
  a wishes wall, a virtual cake with candles, gift boxes, and a finale.

Built with Next.js 14 (App Router), TypeScript, Tailwind CSS, and Framer
Motion.

## 1. Install and run

```bash
npm install
npm run dev
```

Then open `http://localhost:3000`.

## 2. Personalize it

Everything you're likely to change lives in **one file**:
`lib/site-config.ts`. Open it and edit:

| Field | What it controls |
|---|---|
| `sisterName` | Her name, shown on both pages |
| `password` | The word she types to unlock page 2 |
| `birthDate` | Powers the "you've been making the world brighter for..." counter |
| `heroLine` | The typed line under the headline on page 1 |
| `letter` | The full text inside the envelope on page 2 |
| `portraitSrc` | The photo on page 1 |
| `musicSrc` | Optional path to a background music file |
| `galleryPhotos`, `timeline`, `reasons`, `quizQuestions`, `wheelPrizes`, `giftSurprises` | The content of each section on page 2 |

**To use your own photos:** drop image files into `public/assets/images/`
and point `portraitSrc` / `galleryPhotos[].src` at `/assets/images/your-file.jpg`.

**To add real music:** drop an MP3 into `public/assets/audio/` and set
`musicSrc` to `/assets/audio/your-song.mp3`. Leave it empty to keep the
built-in gentle synth melody — no file needed.

## 3. Deploy it

The simplest path is [Vercel](https://vercel.com), the creators of Next.js:

1. Push this folder to a GitHub repository.
2. Import the repository at vercel.com/new.
3. Deploy — no configuration needed.

Any host that supports Next.js (Netlify, Render, your own server via
`npm run build && npm run start`) works too.

## 4. A note on the password lock

`password` in `lib/site-config.ts` is a light "just for her" gate, not real
security — anyone who views the page's source code can find it. That's fine
for a private gift link you send directly to one person; don't rely on it to
protect sensitive information.

## Project structure

```
app/
  page.tsx              → Page 1 route (Hero)
  experience/page.tsx    → Page 2 route (BirthdayExperience)
  layout.tsx              Root layout, fonts, metadata
  globals.css              All styling for both pages
components/
  Hero.tsx, AnimatedBackground.tsx, Portrait.tsx, Typewriter.tsx,
  ContinueButton.tsx, MusicToggle.tsx  → Page 1 pieces
  BirthdayExperience.tsx                → Page 2, all sections
lib/
  site-config.ts          → Every piece of personal content, in one place
```
