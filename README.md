<div align="center">

<picture>
  <img src="docs/media/banner.svg" alt="PriceBook legal pages: the privacy policy for the Android price-tracking app, in five languages" width="100%">
</picture>

**The public privacy policy for PriceBook, the Android app that scans a barcode, logs the price and tells you if it is a real deal.**

<img src="docs/media/badges/site.svg" alt="site: GitHub Pages" height="24">
<img src="docs/media/badges/stack.svg" alt="stack: static HTML and CSS" height="24">
<img src="docs/media/badges/languages.svg" alt="languages: 5" height="24">
<img src="docs/media/badges/app.svg" alt="app: Android" height="24">
<img src="docs/media/badges/gdpr.svg" alt="law: GDPR (Belgium)" height="24">
<img src="docs/media/badges/updated.svg" alt="policy effective 2026-09-29" height="24">
<img src="docs/media/badges/data.svg" alt="app data: stays on device" height="24">
<img src="docs/media/badges/license.svg" alt="license: all rights reserved" height="24">

[**Live site**](https://ruicodex-dev.github.io/pricebook-legal/) &nbsp;·&nbsp;
[**Privacy policy**](https://ruicodex-dev.github.io/pricebook-legal/privacy.html) &nbsp;·&nbsp;
[**Pages and languages**](#pages-and-languages) &nbsp;·&nbsp;
[**Edit a policy**](#getting-started) &nbsp;·&nbsp;
[**Rui Codex**](https://ruicodex.com)

</div>

<br>

<p align="center">
  <img src="docs/media/site-desktop.jpg" alt="The PriceBook legal home page in light mode and the English privacy policy summary in dark mode, in browser windows" width="100%">
</p>

## What this is

This repository is the source of the **PriceBook legal site**, served by GitHub Pages straight from the `main` branch.
It holds the privacy policy for the PriceBook Android app (`com.ruicodex.pricebook`): scan, log the price, see if it's a
real deal, and track your own inflation. The policy is written once in English and published in four more languages.
There is no build step, no script and no tracking: six hand-written HTML files with inline CSS that follow the reader's
light or dark system theme.

<table>
<tr>
<td width="33%" valign="top">

**🔒 Device-first, stated plainly**<br>
Prices, items and history stay in the app's private storage. No account, and no Rui Codex server receives anything.

</td>
<td width="33%" valign="top">

**📷 Camera, explained**<br>
Barcodes are read on the device with Google ML Kit. No photo is stored and no image leaves the phone.

</td>
<td width="33%" valign="top">

**🥫 Opt-in product lookup**<br>
Off by default. When switched on, only the barcode number of a new product goes to Open Food Facts.

</td>
</tr>
<tr>
<td valign="top">

**🌍 Five languages**<br>
English, Türkçe, Deutsch, Español and Français, each with a language bar so readers can switch in one tap.

</td>
<td valign="top">

**⚖️ Written for the GDPR**<br>
Controller in Belgium, legal bases by article, the Belgian Data Protection Authority, KVKK notes for Türkiye.

</td>
<td valign="top">

**🪶 Zero dependencies**<br>
No JavaScript, no external fonts, no cookies, no analytics. `.nojekyll` makes Pages serve the files exactly as written.

</td>
</tr>
</table>

## What the policy says

A short, faithful digest of the English policy (effective **2026-09-29**). The policy itself is the reference; read it in full on the [live site](https://ruicodex-dev.github.io/pricebook-legal/privacy.html).

| Topic | In short |
| --- | --- |
| Account | None. The app never asks for a name, email address or phone number. |
| Your data | Settings, history and everything you enter stay in the app's private storage on your device. No server receives them. |
| Camera | Asked for only when you open the scanner. Google ML Kit reads the barcode on the device; no photo or video is stored or sent. You can also type the barcode. |
| Product-name lookup | Optional and off by default. Sends only the barcode number of a newly scanned product to Open Food Facts (EU-hosted). No prices or store names. Consent can be withdrawn by switching it off. |
| Advertising | Google AdMob, with Google's consent form (UMP) for the EEA, UK and Switzerland before any ad request. Choices can be changed under "Privacy options" in settings. |
| Purchases | Handled by Google Play Billing. Payment details are never seen by Rui Codex. |
| Notifications | Reminders are scheduled locally; nothing is sent from a server. |
| Analytics | No own analytics or crash reporting. A few on-device counters only decide when to show a tip or the review prompt. |
| Feedback | "Send feedback" opens your e-mail app with a pre-filled message; nothing is sent unless you send it. |
| Children | Intended for users aged 13 and over; ads are limited to "G" content. |
| Deletion | Reset in the app, clear storage in Android Settings, or uninstall. |

## Pages and languages

<p align="center">
  <img src="docs/media/site-languages.gif" alt="The privacy policy header cycling through English, Turkish, German, Spanish and French" width="720">
</p>

| Page | File | Live |
| --- | --- | --- |
| Home (links to every language) | [`index.html`](index.html) | [open](https://ruicodex-dev.github.io/pricebook-legal/) |
| Privacy Policy (English, reference text) | [`privacy.html`](privacy.html) | [open](https://ruicodex-dev.github.io/pricebook-legal/privacy.html) |
| Gizlilik Politikası (Türkçe) | [`privacy.tr.html`](privacy.tr.html) | [open](https://ruicodex-dev.github.io/pricebook-legal/privacy.tr.html) |
| Datenschutzerklärung (Deutsch) | [`privacy.de.html`](privacy.de.html) | [open](https://ruicodex-dev.github.io/pricebook-legal/privacy.de.html) |
| Política de privacidad (Español) | [`privacy.es.html`](privacy.es.html) | [open](https://ruicodex-dev.github.io/pricebook-legal/privacy.es.html) |
| Politique de confidentialité (Français) | [`privacy.fr.html`](privacy.fr.html) | [open](https://ruicodex-dev.github.io/pricebook-legal/privacy.fr.html) |

Each translation carries a note that the English version prevails where the texts differ, unless mandatory law says otherwise.

<p align="center">
  <img src="docs/media/site-mobile.jpg" alt="The home page and the privacy policy on phones, in light and dark mode" width="100%">
</p>

## How it works

The site itself is a handful of linked static pages:

```mermaid
flowchart LR
    R["Reader<br/>(app user, store visitor, web)"] --> H["index.html<br/>home"]
    R --> P
    H --> P["privacy.html<br/>English reference"]
    H --> T["privacy.tr / .de / .es / .fr<br/>translations"]
    P <-- "language bar" --> T
    subgraph GH["GitHub Pages · branch main · root /"]
      H
      P
      T
    end
```

And this is the data flow the policy describes for the app:

```mermaid
flowchart LR
    S["Scanner<br/>(camera, on device)"] -->|"barcode number"| A["PriceBook app<br/>private storage"]
    A -->|"barcode number only<br/>(opt-in, off by default)"| O["Open Food Facts"]
    A -->|"ad requests after consent (UMP)"| G["Google AdMob"]
    A -->|"purchases"| B["Google Play Billing"]
    A -.->|"never"| X["Rui Codex server<br/>(none exists)"]
```

A push to `main` is all it takes to update the site: Pages publishes the repository root as is (`.nojekyll` turns off Jekyll processing).

## Tech stack

| Layer | Choice |
| --- | --- |
| Pages | Hand-written HTML5, one file per page and language |
| Styling | Inline CSS with custom properties, `prefers-color-scheme` dark palette, system font stack |
| Hosting | GitHub Pages from `main`, root folder |
| Tooling | None needed. Any editor and any static file server |

## Getting started

**Preview locally** (any static server works):

```bash
git clone https://github.com/RuiCodex-dev/pricebook-legal.git
cd pricebook-legal
python -m http.server 8000
# open http://localhost:8000/
```

**Change the policy**

1. Edit the English reference, `privacy.html`, and update the effective date in its `.meta` line.
2. Carry the same change into `privacy.tr.html`, `privacy.de.html`, `privacy.es.html` and `privacy.fr.html`, so all five stay in step.
3. Check every page in light and dark mode and at phone width, then commit to `main`. Pages redeploys on its own.

<details>
<summary><b>Adding a language</b></summary>

<br>

1. Copy `privacy.html` to `privacy.<code>.html` (for example `privacy.nl.html`), set `<html lang="<code>">` and translate.
2. Add the translation note (the English version prevails) under the introduction, like the other translations.
3. Add the new language to the language bar (`<nav class="langs">`) in **every** privacy page.
4. Add it to the header links and the list in `index.html`, with a matching `hreflang`.

</details>

## Project structure

```text
pricebook-legal/
├── index.html          # home: app summary, links to every language, contact
├── privacy.html        # Privacy Policy (English, reference text)
├── privacy.tr.html     # Gizlilik Politikası
├── privacy.de.html     # Datenschutzerklärung
├── privacy.es.html     # Política de privacidad
├── privacy.fr.html     # Politique de confidentialité
├── .nojekyll           # serve files as is on GitHub Pages
└── docs/media/         # README banner, badges and captures
```

## FAQ

<details>
<summary><b>Which language version is binding?</b></summary>

<br>

The English text. Every translation states that it is provided for convenience and that the English version prevails where they differ, unless mandatory law requires otherwise.

</details>

<details>
<summary><b>Does PriceBook send my prices anywhere?</b></summary>

<br>

No. According to the policy, prices, store names and items stay on the device. The only product data that can leave the phone is the barcode number of a new product, and only if you switch the Open Food Facts lookup on.

</details>

<details>
<summary><b>Does this site track visitors?</b></summary>

<br>

The pages contain no scripts, cookies, external fonts or analytics. Hosting is GitHub Pages; GitHub's own server logging is covered by GitHub's terms.

</details>

<details>
<summary><b>Who do I contact about privacy?</b></summary>

<br>

Rui Codex, Belgium: info@ruicodex.com, with "Privacy – PriceBook" in the subject line. You can also complain to the Belgian Data Protection Authority or the authority where you live, as the policy explains.

</details>

---

<div align="center">

**All rights reserved, © 2026 Rui Codex.** The policy texts may not be reused for other products without permission.

Built by **[Rui Codex](https://ruicodex.com)** · Contact: info@ruicodex.com

<sub>Media credits: all screenshots and the language GIF are real captures of the live site; the banner (an illustration, not app UI) and badges are hand-built SVG. No generated imagery, narration or music is used in this README.</sub>

</div>
