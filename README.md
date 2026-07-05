# Metrify marketing site (mockup)

Static pages — no build step. Just open `index.html` in a browser
(or `start website\index.html` from the repo root).

## Publishing (subtree)

This folder is mirrored to https://github.com/Verlin-Software-LLC/Metrify-Website
(same pattern as `src/api` → Metrify-Backend). After committing changes here:

```powershell
git subtree push --prefix=website org-website main
```

(remote: `org-website` = the Metrify-Website repo)

## Pages

- `index.html` — landing page
- `privacy.html` — Privacy Policy (converted from `src/mobile/FitnessApp/legal/PRIVACY_POLICY.md`, effective 2026-07-03)
- `terms.html` — Terms of Service (converted from `src/mobile/FitnessApp/legal/TERMS_OF_SERVICE.md`, effective 2026-07-03)

**Keep in sync:** the legal pages are manual conversions of the markdown docs in
`src/mobile/FitnessApp/legal/`. If those change, regenerate these pages.

## Typography

Archivo Black (display) + Archivo (body) loaded from Google Fonts — the one
external dependency. Falls back to Arial Black / Segoe UI offline. Self-host the
woff2 files before launch if you want zero third-party requests.

## Placeholders to swap for real assets

| Spot | Currently | Replace with |
|---|---|---|
| Hero phone | CSS-drawn chat mockup | Real chat screenshot or screen recording |
| Privacy section | Dashed box | Privacy illustration / data-flow graphic |
| "See it in action" | Dashed 16:9 box | 30–60s demo video |
| Screenshot gallery | 4 dashed 9:19 boxes | Chat / Progress / Workout Lab / Food detail screenshots |
| "Request beta access" button | `mailto:support@metrify.fit` | TestFlight / Play beta / signup form link |
| Store badges | Text mockups | Official App Store / Google Play badge art (once live) |

## Notes

- `metrify_logo.svg` is a copy of `src/mobile/FitnessApp/Resources/Images/metrify_logo.svg`
  (used in the nav + favicon). It's a ~144 KB traced SVG — worth optimizing
  (SVGO / re-export as clean vectors) before launch.
- Colors match the app: brand orange `#FF7A00` on dark (`Colors.xaml`).
- Contact email is `support@metrify.fit` (matches the legal docs).
- Pricing shown ($6.99/mo, $59.99/yr) mirrors current RevenueCat config — update here if store pricing changes.
- Copy claims worth double-checking before publishing: 447K-food catalog size, free-tier 3 chats/day, premium 75/day.
