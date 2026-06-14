# Amethyst AI Care — Website

A polished, fully static marketing site for **Amethyst AI Care** — AI-powered
fall prevention and continuous care for the aging population.

No build step, no backend. Just HTML, CSS, and a little vanilla JavaScript —
designed to deploy to **Cloudflare Pages** in seconds.

## Structure

```
.
├── index.html              # Single-page site (nav, hero, products, how-it-works, about, contact, footer)
├── styles.css              # All styling (amethyst palette, Apple-style polish, responsive)
├── script.js               # Sticky nav, mobile menu, scroll reveal, contact-form handling
├── assets/
│   ├── Logo.png            # Brand logo
│   └── hero-nurse-leaf.svg # Custom hero illustration: a nurse catching a falling autumn leaf
└── README.md
```

## Local preview

It's pure static — open `index.html` directly, or serve the folder:

```powershell
# Python
python -m http.server 8000

# or Node
npx serve .
```

Then visit http://localhost:8000.

## Contact form (no backend)

The form uses [Formspree](https://formspree.io) so there is **no server to run**.

1. Create a free form at https://formspree.io.
2. Copy your form ID (e.g. `xmyzabcd`).
3. In `index.html`, replace `YOUR_FORM_ID` in the form `action` URL:
   ```html
   <form ... action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
   ```

Until that ID is set, the form shows a friendly notice and points visitors to
the email address instead of failing silently.

Also update the contact email (`hello@amethystaicare.com`) in `index.html`
to your real inbox.

## Deploy to Cloudflare Pages

1. Push this repo to GitHub (already done).
2. In the Cloudflare dashboard: **Workers & Pages → Create → Pages → Connect to Git**.
3. Pick this repository.
4. Build settings:
   - **Framework preset:** `None`
   - **Build command:** *(leave empty)*
   - **Build output directory:** `/`
5. Deploy. Every push to the default branch redeploys automatically.

## Customising

- **Colours** live as CSS variables at the top of `styles.css` (`:root`).
- **Copy** is all in `index.html`.
- **Hero illustration** is an editable SVG in `assets/hero-nurse-leaf.svg`.
