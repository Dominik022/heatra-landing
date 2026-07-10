# HEATRA Landing Page

Single-file static site (`index.html` — no build step, no dependencies). Goal: validate demand before spending on cartridges/prototypes. Collect name + email + "would buy" checkbox.

## 1. Connect the waitlist form (Formspree, ~5 min)

1. Go to https://formspree.io and create a free account.
2. Create a new form (any name, e.g. "HEATRA Waitlist").
3. Formspree gives you an endpoint like `https://formspree.io/f/abc12345`.
4. Open `index.html`, find `YOUR_FORM_ID` (search for it — appears once, in the `<form action="...">` line), and replace it with your real ID.
5. Save. Submissions will now show up in your Formspree dashboard and get emailed to you.

Free tier = 50 submissions/month, which is plenty for early validation. Upgrade later if needed.

## 2. Add real visuals

The page has 5 image placeholders (search `PLATZHALTER` in `index.html`):
- 1 hero shot (`.hero-visual` div)
- 4 lifestyle tiles below it (`.lifestyle-tile` divs — on the rock, hands opening the box, steaming food close-up, flat-lay of box + cartridges)

Replace each placeholder div's text content with an `<img src="...">` tag (or `<video>` for the hero), and drop the image files next to `index.html`. Even a rendered concept image or phone footage works for now — just don't present it as a finished, photographed product; a small "Konzept-Darstellung" caption under the hero keeps things honest while you're still in the prototype stage.

## 3. Deploy to GitHub Pages (free)

From a terminal, in the folder containing `index.html`:

```bash
git init
git add index.html README.md
git commit -m "HEATRA landing page v1"
```

Then on GitHub:
1. Create a new repository (e.g. `heatra-landing`), don't initialize it with a README.
2. Push your local repo:
```bash
git remote add origin https://github.com/<your-username>/heatra-landing.git
git branch -M main
git push -u origin main
```
3. On GitHub, go to the repo → **Settings → Pages**.
4. Under "Build and deployment", set **Source: Deploy from a branch**, branch: `main`, folder: `/ (root)`.
5. Save. Your site will be live within a minute or two at:
   `https://<your-username>.github.io/heatra-landing/`

### Custom domain (optional)
If you buy something like `heatra.ch`, add a `CNAME` file in the repo root containing just the domain, then point your DNS at GitHub Pages (A records or a CNAME record per GitHub's docs).

## 4. Drive traffic

Per the original plan — post in Swiss hiking/outdoor Facebook groups, r/Switzerland, Instagram/TikTok, and talk to people in person at outdoor stores/hiking meetups. Ask directly: "would you buy this over a stove you already own?" — that's the real question this page needs to answer.

## 5. What to watch

- **Signup rate**: visitors → email signups. Anything under ~2-3% suggests the headline/offer isn't landing.
- **"Ich würde kaufen" checkbox**: don't count signups that skip this — it's there specifically to filter curiosity clicks from real intent.
- **Where traffic converts best**: in-person conversations typically outperform social/ads for a physical product like this — track it by using different links per channel if possible (e.g. `?src=facebook`, `?src=instagram` in the URL, visible in Formspree submissions via referrer).

## Editing content

Everything is in one file (`index.html`) — headline, pricing, FAQ, form fields — plain HTML/CSS, no framework. Search for the German text you want to change and edit directly.
