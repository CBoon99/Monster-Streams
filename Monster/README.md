# Monster Streams Landing Page

Marketing-grade single-page site for the Monster Streams IPTV service. It mixes a neon sci-fi aesthetic with conversion-focused content (hero, features, pricing, setup guides, legal copy, and dual Netlify forms) so you can capture trials and support enquiries straight from static hosting.

## ✨ Highlights
- **Hero + CTA**: Animated hero with particle background, floating mascot, and instant jump links to pricing/trial.
- **Feature storytelling**: Grid of cards, accordions for multi-device setup guides, and tiered pricing tabs (1–12 month plans).
- **Conversion flows**: Two Netlify-ready forms (`trial`, `contact`) with honeypots, custom validation, and JS fallbacks for graceful submission alerts.
- **Trust copy**: Terms, VPN notice, contact grid, and footer anchor links for policy compliance.
- **Performance-aware visuals**: Lazy-loaded hero/footer logos, scroll-triggered animations, and CSS-only glow effects (no external JS bundles).
- **Production SEO**: Canonical, OG/Twitter cards, Organization + Product JSON-LD, CSP enforcement, referrer policy, and mobile-first meta viewport.

## 🗂 Project Structure
```
Monster/
├─ index.html        # Full landing page (HTML + CSS + vanilla JS)
└─ Logo/
   └─ Logo.png       # Brand mark used throughout the site
```

Everything is inlined for single-file deployment. Swap `Logo/Logo.png` for your own transparent PNG while keeping the same filename to avoid editing markup.

## 🚀 Getting Started

| Action | Steps |
| --- | --- |
| **Preview locally** | 1. Open `index.html` in any modern browser. <br>2. Scroll through sections or use the nav buttons (smooth scroll is built-in). |
| **Deploy to Netlify (recommended)** | 1. Push this folder to a Git repository. <br>2. In Netlify, create a new site from Git → build command not required → publish directory is the repo root. <br>3. Enable “Forms” in Netlify dashboard to view submissions for the `trial` and `contact` forms. |
| **Deploy elsewhere** | Upload the contents of `Monster/` to any static host (S3, Vercel, Cloudflare Pages, etc.). Ensure HTTPS so CSP `upgrade-insecure-requests` works as intended. |

## ⚙️ Customization Guide

- **Branding**: Update the logo PNG, adjust neon colors in the `:root` block, and tweak copy directly in `index.html`.
- **Pricing tiers**: Each plan card lives under the relevant `pricing-grid`. Duplicate or remove cards while keeping the same structure.
- **Setup accordion**: Expand by cloning `.accordion-item` blocks; the JS auto-handles open/close states.
- **Forms**:
  - `trial` form posts to Netlify with hidden `form-name=trial` and honeypot `bot-field`.
  - `contact` form posts similarly with `form-name=contact` and `contact-bot-field`.
  - The helper `encodeFormData` plus fetch() handles success/failure alerts if JavaScript is enabled; Netlify still captures submissions if JS is disabled.
- **SEO assets**: Update `/assets/og-monsterstreams.jpg` path if you change the Open Graph image location, and keep canonical/JSON-LD URLs aligned with your production domain.

## ✅ Production Checklist

- [ ] Replace marketing copy/plan pricing with your current offers.
- [ ] Swap `mailto:` addresses under the contact section with active inboxes.
- [ ] Run the page through [PageSpeed Insights](https://developers.google.com/speed/pagespeed/insights/) after hosting to confirm CLS/LCP remain green.
- [ ] Test both forms from the deployed domain and verify entries appear in the Netlify dashboard.
- [ ] Re-run Google’s [Rich Results Test](https://search.google.com/test/rich-results) to confirm both Organization and Product JSON-LD blocks validate once you finalize copy.

## 🧩 Tech Stack

| Layer | Details |
| --- | --- |
| Markup | Hand-crafted HTML5 with semantic sections (`hero`, `features`, `setup`, `pricing`, `trial`, `terms`, `contact`, `footer`). |
| Styling | Pure CSS inside `<style>`: CSS variables, grid/flex layouts, responsive breakpoints at 1024/768/480px, custom animations. |
| Behavior | Vanilla JS for particles, scroll animations, accordion, pricing tabs, smooth-scroll nav, form submissions, and scroll-to-top control. |
| Integrations | Netlify Forms (no backend code), SEO metadata, JSON-LD (Organization + Product), CSP + referrer policies. |

## 🤝 Contributing / Maintenance
Because the project is purpose-built for a specific brand, changes typically happen on forks. If you clone this repo:

1. Create a new branch for each feature tweak (`git checkout -b feature/short-description`).
2. Keep HTML readable (no minification) to make future copy edits easy.
3. Use a formatter/HTML linter before committing if your editor is configured for it.
4. Deploy from `main` only after manual QA across desktop + mobile.

## 📬 Support
Need help extending the page (multi-language, CMS hooks, analytics, etc.)? Open an issue in your repo or contact your web team with this README so they understand the build.

Happy streaming! 🚀



