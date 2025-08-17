# DM Tech Repair — Website

## ✨ Features

* **Modern UI**: glassmorphism cards, soft shadows, ripple interactions, smooth scrolling.
* **Responsive** layout with mobile menu (hamburger) and grid sections.
* **Appointment modal** ("Umów diagnozę") with:

  * Required fields validation (name, e‑mail, message)
  * **Automatic send via Web3Forms** (AJAX) + **mailto fallback**
  * Keyboard support (Esc to close, focus management)
* **Contact form** using the same Web3Forms backend + inline status messages.
* **Bilingual**: **PL/EN** i18n system with an SVG **flag toggle** (🇵🇱/🇬🇧), text stored in a single `I18N` dictionary.
* **Content filtering** for services (chips + search).
* **Testimonials slider**, **FAQ accordion**, **Back‑to‑top** helper.
* **Animated starfield** canvas background with reduced‑motion support.
* **SEO**: `<meta name="description">`, **Schema.org `ComputerRepair` JSON‑LD**, sitemap & manifest placeholders.
* **Accessibility**: ARIA attributes, sr‑only labels, color‑contrast aware palette.

---

## 📁 Project structure

The site is a single file for easy hosting. Assets like icons/manifest are optional but recommended.

```
/
├─ index.html          # Full site (UI, logic, i18n, Web3Forms)
├─ favicon.svg         # Site icon (customize)
├─ manifest.webmanifest# PWA/metadata (optional)
└─ sitemap.xml         # SEO (optional)
```

---

## 🚀 Quick start

1. **Clone**

   ```bash
   git clone https://github.com/<your-username>/dm-tech-repair-website.git
   cd dm-tech-repair-website
   ```
2. **Open locally**

   * Double‑click `index.html`, or
   * Serve with a tiny dev server for best results:

     ```bash
     # Python
     python -m http.server 5173
     # or Node
     npx serve .
     ```

   Visit `http://localhost:5173` (or the URL printed in the console).

---

## ⚙️ Configuration

### 1) E‑mail sending (Web3Forms)

* **Access key** is required. Get one at [web3forms.com](https://web3forms.com/).
* In `index.html`, search for `WEB3FORMS_KEY` and replace the placeholder with your key:

  ```js
  const WEB3FORMS_KEY = 'YOUR-ACCESS-KEY';
  ```
* Default recipient is set to **[dawidmalek80@gmail.com](mailto:dawidmalek80@gmail.com)**. To change it, search for `to: 'dawidmalek80@gmail.com'` in two places (modal + contact form) and replace with your address.
* If the API call fails, the app **falls back to `mailto:`** so you never lose a message.

### 2) Language & copy

* All copy lives in the `I18N` object at the end of `index.html`.
* To tweak any line, edit the string in `I18N.pl` or `I18N.en` with the same key.
* The current language is stored in `localStorage('lang')` and toggled with the flag button in the header.

### 3) Branding

* Update `favicon.svg`, `manifest.webmanifest`, and `meta[name="description"]`.
* JSON‑LD (`<script type="application/ld+json">`) contains business details (name, phone, hours) — update as needed.

---

## 🌐 Deployment

### GitHub Pages

1. Push repository to GitHub.
2. In repo **Settings → Pages**: Source = `main` / root.
3. Your site will be available at `https://<user>.github.io/dm-tech-repair-website/`.

### Netlify / Vercel

* **Netlify**: drag‑and‑drop the folder, or connect your Git repo (no build step).
* **Vercel**: import repo, framework = `Other`, output = root.

---

## 🧪 Checklist

* [ ] Replace `WEB3FORMS_KEY` with your production key
* [ ] Verify recipient e‑mail address
* [ ] Update business data in JSON‑LD
* [ ] Customize favicon and manifest
* [ ] Add a real `sitemap.xml` (optional)

---

## 🔐 Privacy & data

* Forms send minimal data to Web3Forms over HTTPS, stored per their policy.
* Client‑side validation prevents empty/invalid submissions.
* `mailto:` fallback uses the visitor’s default e‑mail client and never stores data on your server.

---

## 🤝 Contributing

This repository is tailored for a specific business. External PRs are not expected, but issues are welcome.

---

## 📄 License

No open‑source license is specified. All rights reserved by **Dawid Małek** unless a license is added. If you prefer open‑source, add an `MIT` or `Apache‑2.0` LICENSE file.

---

## 📬 Contact

**DM Tech Repair**
E‑mail: [dawidmalek80@gmail.com](mailto:dawidmalek80@gmail.com)
Location: Rzeszów, Poland

---

### Screenshots (optional)

Add a `/screenshots` folder and include UI previews in this README.

---

### Changelog (example)

* **v1.0.0** — Initial release: bilingual UI, appointment modal, Web3Forms integration, SEO, accessibility polish.
