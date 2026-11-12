# Privacy site (local draft, not published)

Static pages for GitHub Pages, no external scripts. Target addresses:

- https://bekircannns.github.io/privacy/ -> `index.html` (game list)
- https://bekircannns.github.io/privacy/<game>/ -> `<game>/index.html` for arrow-carousel, mek-knife, mek-fold, mek-scale, sort-trial, mek-crane, mek-paint
- https://bekircannns.github.io/privacy/terms/ -> `terms/index.html` (shared Terms of Use)

Note: the brief says ".../privacy/<g>/ and /terms/". The links between pages are relative, so the folder works both as the
repo root and under `/privacy/`. If terms must live at `https://bekircannns.github.io/terms/` instead, move `terms/` and fix the
two `../terms/` footer links.

## Placeholders to fill (search and replace in all 9 HTML files)

| Placeholder | Meaning |
|---|---|
| `[[YER_TUTUCU_YAYINCI_ADI]]` | Publisher name as in Play Console |
| `[[YER_TUTUCU_EPOSTA]]` | Contact e-mail (same as the Play listing) |
| `[[YER_TUTUCU_ADRES]]` | Postal address (or remove it if Play Console does not require it for your account type) |
| `[[YER_TUTUCU_YURURLUK_TARIHI]]` | Effective date |
| `[[YER_TUTUCU_HEDEF_KITLE_CUMLESI]]` | Audience sentence (e.g. "It is intended for players aged 13 and older."), per docs/store/audience-and-rating.md |
| `[[YER_TUTUCU_YANIT_SURESI_GUN]]` | Reply time in days for data requests (e.g. 30) |
| `[[YER_TUTUCU_UYGULANACAK_HUKUK]]` | Governing law in Terms (e.g. "the laws of the Republic of Turkey") |

## What the text assumes (closed-test build, 2026-11-12)

- `ads.off: true` in every app.json: no ads configured or requested; GMA Next-Gen + UMP still in Gradle, and the generated
  Data safety form declares the 4 ad-SDK types (approx. location, app interactions, diagnostics, device IDs). Text says both.
- `privacy.age_gate: false`: no age question.
- `beyin.edge_url: null` and `services.base_url: null`: the Beyin client is not created, nothing goes to our servers.
- Play Billing 9.1.0 and Install Referrer 2.2 (template default on unless `motor.install_referrer=false`).
- No Firebase/Crashlytics.

When any of these changes (ads on, edge_url set, age gate on), the policy must be updated before that build ships.
Legal review is Bekir's (not legal advice).
