# No Breaks

Small demo page encouraging complete messages (avoid sending one line at a time). It shows a chat demo with a "bad" and
a "good" example and allows manual language switching.

Technologies

- Static HTML + TailwindCSS via CDN
- Vue 3 via CDN (global build)

Status

- Simple single-file project: `index.html` contains the markup, styles and translations.

Features

- Chat demo that emits sequential messages automatically.
- Button to toggle between the "bad" and "good" example.
- Visible language selector as a set of buttons (Português, English, Español, Français, Deutsch).
- Translations embedded in the script (`translations` object).
- LinkedIn link for the author in the footer.

How to use

Live demo

- Visit the live site: https://nobreaks.net

Open locally

- Simply open `index.html` in your browser (double-click or `xdg-open` on Linux):

```bash
xdg-open index.html
```

Serve with a static server (recommended for more realistic testing)

With Python 3:

```bash
# from the project folder
python3 -m http.server 8000
# then open http://localhost:8000
```

With the `serve` package (Node.js):

```bash
npm install -g serve
serve .
```

File structure

- `index.html` — contains markup, Tailwind (via CDN) and the Vue script with demo logic.
    - `translations` — JS object holding the translations per language.
    - `langOptions` — list of languages shown as buttons.
    - `currentMessages` — reactive array used to render chat bubbles.

Quick customization

- Change texts/translations: edit the `translations` object inside `index.html`.
- Add a language: add a new key to `translations` and an item to `langOptions`.

Contact

- LinkedIn: https://www.linkedin.com/in/jonatas-costa-dev/
- Live site: https://nobreaks.net
