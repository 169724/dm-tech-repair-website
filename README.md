# DM Tech Repair — Website / Strona WWW

[EN](#en) • [PL](#pl)

---

## <img width="16" height="11" alt="image" src="https://github.com/user-attachments/assets/31637c7c-c9cc-413e-98a5-a574fcceafaa" /> Strona WWW — opis (PL)

### ✨ Funkcje

* **Nowoczesny UI**: karty „glassmorphism”, miękkie cienie, efekt „ripple”, płynne przewijanie.
* **Responsywność** z mobilnym menu (**hamburger**) i siatką sekcji.
* **Modal rezerwacji** („Umów diagnozę”) z:

  * walidacją pól (imię, e‑mail, opis),
  * **automatyczną wysyłką przez Web3Forms** (AJAX) + **fallback `mailto:`**,
    *(klucz i adres e‑mail podmieniasz na swoje — w repo NIE umieszczaj danych prywatnych)*,
  * wsparciem klawiatury (Esc, fokus).
* **Formularz kontaktowy** korzystający z tego samego backendu Web3Forms + komunikaty inline.
* **Dwujęzyczność PL/EN**: system i18n w jednym obiekcie `I18N`, **przełącznik flag (SVG)** i **płynna zmiana języka** (fade).
* **Pasek progresu przewijania** na górze — pokazuje postęp czytania strony.
* **Filtrowanie oferty** (chipsy + wyszukiwarka).
* **Slider opinii**, **FAQ akordeon**, **przycisk powrotu na górę**.
* **Animowane tło gwiazd** z poszanowaniem `prefers-reduced-motion`.
* **SEO**: `<meta name="description">`, **Schema.org `ComputerRepair` JSON‑LD**, sitemap & manifest.
* **Dostępność**: ARIA, etykiety „sr-only”, kontrastowa paleta.

---

### 📁 Struktura

```
/
├─ index.html            # Cała strona (UI, logika, i18n, Web3Forms)
├─ favicon.svg           # Ikona strony (opcjonalnie do zmiany)
├─ manifest.webmanifest  # PWA/metadata (opcjonalnie)
└─ sitemap.xml           # SEO (opcjonalnie)
```

---

### 🚀 Szybki start

1. **Klonuj**

```bash
git clone https://github.com/<twoja-nazwa>/dm-tech-repair-website.git
cd dm-tech-repair-website
```

2. **Uruchom lokalnie**

* Otwórz `index.html` w przeglądarce **lub**
* uruchom prosty serwer (lepsze cache/ścieżki):

```bash
# Python
python -m http.server 5173
# lub Node
npx serve .
```

Wejdź na `http://localhost:5173` (lub adres z konsoli).

---

### ⚙️ Konfiguracja

#### 1) Wysyłka e‑mail (Web3Forms)

* Załóż konto i **zdobądź access key** na **web3forms.com**.
* W pliku `index.html`:

  * znajdź stałą `WEB3FORMS_KEY` i ustaw **swoją wartość**:

    ```js
    const WEB3FORMS_KEY = 'YOUR-WEB3FORMS-ACCESS-KEY';
    ```
  * (opcjonalnie) Zmień odbiorcę w polu `to: 'you@example.com'` w **dwóch miejscach** (modal + formularz kontaktu).
* **Uwaga bezpieczeństwo**: nie commituj prawdziwego klucza do publicznego repozytorium. Rozważ trzymanie klucza poza główną gałęzią lub użycie prywatnego repo.

#### 2) Język i treści

* Wszystkie treści są w obiekcie `I18N` na dole `index.html`.
* Edytuj pary klucz‑wartość w `I18N.pl` i `I18N.en` (ten sam klucz = ta sama treść w obu językach).
* Aktualny język jest w `localStorage('lang')`. Przycisk flagi w headerze przełącza PL/EN.

#### 3) Branding

* Zmień `favicon.svg`, `manifest.webmanifest` i `meta[name="description"]`.
* W JSON‑LD (`<script type="application/ld+json">`) podmień dane firmy (nazwa, telefon, godziny, linki). **Nie wstawiaj danych prywatnych do publicznego repo.**

---

### 🌐 Publikacja

**GitHub Pages**

1. Wypchnij repo do GitHub.
2. `Settings → Pages`: Source = `main` / root.
3. Strona pojawi się pod `https://<user>.github.io/dm-tech-repair-website/`.

**Netlify / Vercel**

* Netlify: przeciągnij‑upuść folder lub podłącz repo (brak kroku build).
* Vercel: import repo, framework = `Other`, output = root.

---

### 🧪 Lista kontrolna

* [ ] Podmień `WEB3FORMS_KEY` na własny (nie publikuj go!)
* [ ] Zaktualizuj adres e‑mail odbiorcy (`you@example.com`)
* [ ] Uzupełnij dane firmy w JSON‑LD (opcjonalnie)
* [ ] Dostosuj favicon i manifest
* [ ] Dodaj prawdziwy `sitemap.xml` (opcjonalnie)

---

### 🔐 Prywatność i dane

* Formularze wysyłają minimalny zestaw danych do Web3Forms przez HTTPS (patrz ich polityka).
* Walidacja po stronie klienta chroni przed pustymi/nieprawidłowymi zgłoszeniami.
* **Fallback `mailto:`** uruchamia domyślnego klienta poczty użytkownika i nie zapisuje danych na Twoim serwerze.

---

### 🤝 Kontrybucje

Projekt jest dopasowany do konkretnego biznesu. Zewnętrzne PR‑y nie są oczekiwane, ale zgłoszenia problemów są mile widziane.

---

### 📄 Licencja

Brak jawnej licencji open‑source. Wszelkie prawa zastrzeżone przez właściciela projektu.
Jeśli chcesz — dodaj plik `LICENSE` (np. `MIT` lub `Apache‑2.0`).

---

### 📬 Kontakt

> **Uwaga:** nie publikuj danych prywatnych w publicznym repo.
> Wstaw tutaj dane firmowe lub adres e‑mail aliasu, np.: `contact@example.com`.

---

### 🗒️ Changelog

* **v1.1.0** — Dodano **pasek progresu przewijania** (u góry), poprawiono mobilny hamburger, dopracowano przełącznik flag (SVG), drobne poprawki dostępności.
* **v1.0.0** — Wersja początkowa: dwujęzyczny UI, modal rezerwacji, integracja Web3Forms, SEO, dostępność.

---

## <img width="16" height="11" alt="image" src="https://github.com/user-attachments/assets/60978719-3730-4cb5-9830-5b246a50a0ca" /> Website — description (EN)

### ✨ Features

* **Modern UI**: glassmorphism cards, soft shadows, ripple effects, smooth scrolling.
* **Responsive** layout with mobile menu (**hamburger**) and grid sections.
* **Appointment modal** with:

  * required field validation (name, e‑mail, message),
  * **Web3Forms** AJAX sending + **`mailto:` fallback**,
    *(replace key & recipient with your own — do **not** commit private data)*,
  * keyboard support (Esc, focus).
* **Contact form** using the same Web3Forms backend + inline status messages.
* **Bilingual PL/EN**: single `I18N` dictionary, **SVG flag toggle**, **smooth language fade**.
* **Scroll progress bar** at the very top showing reading progress.
* **Service filtering** (chips + search).
* **Testimonials slider**, **FAQ accordion**, **Back‑to‑top** button.
* **Animated starfield** with `prefers-reduced-motion` support.
* **SEO**: `<meta name="description">`, **Schema.org `ComputerRepair` JSON‑LD**, sitemap & manifest.
* **Accessibility**: ARIA attributes, sr‑only labels, contrast‑aware palette.

---

### 📁 Project structure

```
/
├─ index.html            # Full site (UI, logic, i18n, Web3Forms)
├─ favicon.svg           # Site icon (customize)
├─ manifest.webmanifest  # PWA/metadata (optional)
└─ sitemap.xml           # SEO (optional)
```

---

### 🚀 Quick start

1. **Clone**

```bash
git clone https://github.com/<your-username>/dm-tech-repair-website.git
cd dm-tech-repair-website
```

2. **Open locally**

* Double‑click `index.html`, or
* serve with a tiny dev server for best results:

```bash
# Python
python -m http.server 5173
# or Node
npx serve .
```

Visit `http://localhost:5173` (or the URL printed in the console).

---

### ⚙️ Configuration

#### 1) E‑mail sending (Web3Forms)

* Create an account and get your **access key** at **web3forms.com**.
* In `index.html`:

  * search for `WEB3FORMS_KEY` and set **your value**:

    ```js
    const WEB3FORMS_KEY = 'YOUR-WEB3FORMS-ACCESS-KEY';
    ```
  * (optional) change the recipient in `to: 'you@example.com'` in **two places** (modal + contact form).
* **Security note**: avoid committing real keys to public repos. Consider a private repo or keeping the key off the default branch.

#### 2) Language & copy

* All copy lives in the `I18N` object (bottom of `index.html`).
* Edit strings in `I18N.pl` and `I18N.en` with matching keys.
* Current language is stored in `localStorage('lang')`; the flag button toggles PL/EN.

#### 3) Branding

* Update `favicon.svg`, `manifest.webmanifest`, and `meta[name="description"]`.
* In JSON‑LD (`<script type="application/ld+json">`), replace business details (name, phone, hours, links). **Avoid publishing private data.**

---

### 🌐 Deployment

**GitHub Pages**

1. Push the repo to GitHub.
2. `Settings → Pages`: Source = `main` / root.
3. Your site will be available at `https://<user>.github.io/dm-tech-repair-website/`.

**Netlify / Vercel**

* Netlify: drag‑and‑drop the folder, or connect your Git repo (no build step).
* Vercel: import repo, framework = `Other`, output = root.

---

### 🧪 Checklist

* [ ] Replace `WEB3FORMS_KEY` with your production key (do **not** publish it)
* [ ] Update recipient e‑mail (`you@example.com`)
* [ ] Update business data in JSON‑LD (optional)
* [ ] Customize favicon and manifest
* [ ] Add a real `sitemap.xml` (optional)

---

### 🔐 Privacy & data

* Forms send minimal data to Web3Forms over HTTPS (see their policy).
* Client‑side validation prevents empty/invalid submissions.
* **`mailto:` fallback** opens the visitor’s default e‑mail client and does not store data on your server.

---

### 🤝 Contributing

This repository is tailored for a specific business. External PRs are not expected, but issues are welcome.

---

### 📄 License

No open‑source license is specified. All rights reserved by the project owner.
If you prefer open‑source, add a `LICENSE` file (e.g., `MIT` or `Apache‑2.0`).

---

### 📬 Contact

> **Note:** don’t publish private details in a public repo.
> Put your public business contact here, e.g.: `contact@example.com`.

---

### 🗒️ Changelog

* **v1.1.0** — Added **scroll progress bar** (top), improved mobile hamburger, refined SVG flag toggle, minor a11y tweaks.
* **v1.0.0** — Initial release: bilingual UI, appointment modal, Web3Forms integration, SEO, accessibility polish.
