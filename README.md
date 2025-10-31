# No Breaks

Small static demo that encourages sending complete messages (avoid sending one line at a time). It displays a short chat
preview with a "bad" and a "good" example and includes a language selector, an audio prompt and responsive layout
tweaks.

Live demo

- https://nobreaks.net

Technologies

- Static HTML
- Tailwind CSS via CDN
- Vue 3 (global build via CDN)

Quick status

- Single-file demo: `index.html` contains markup, styles and the small Vue script that runs the demo and translations.

Highlights / Features

- Chat preview that emits messages sequentially
- Toggle between a "bad" and a "good" example
- Language selector (Português, English, Español, Français, Deutsch)
- Initial prompt to enable message sound (persisted in localStorage)
- Improved responsiveness for mobile (button wrapping, stacked modal buttons)

Get started (local)

1. Clone or download the repo and open the project folder.

2. Run a static server from the project folder (recommended):

With Python 3 (built-in):

```bash
python3 -m http.server 8000
# open http://localhost:8000
```

Or with Node `serve` (global):

```bash
npm install -g serve
serve .
```

You can open `index.html` directly in a browser, but a local server provides a more realistic environment (and avoids
some browser restrictions).

Audio prompt & behavior

- On first load the app may show a small modal asking the user to enable message sound. This is intentional: the demo
  will NOT start until the user accepts or dismisses the prompt (prevents autoplay audio).
- The sound preference is saved in localStorage under the key `nb-audio-allowed`.
- The demo uses the Web Audio API to play a short beep for each incoming message. Browsers may still block audio until a
  user gesture occurs; clicking the modal's "Enable sound" or any other button usually grants the required gesture.

Internationalization (i18n)

- Translations are embedded in `index.html` inside the `translations` object. Add or edit languages there and update
  `langOptions` if necessary.

Customization

- Edit example messages: change `messagesBad` and `messagesGood` under each language in `translations`.
- Change UI text: update the translation strings in the same object.
- Audio: audio logic is implemented with `ensureAudioCtx`, `playBeep` and `setAudioPreference` in the script inside
  `index.html`.

Development tips

- Live reload: use `live-server`, `serve` or a tiny dev server to expedite development.
- Linting: this is a minimal demo without build tools. If you want to add linting or a bundler, consider extracting the
  script into modules and using a small toolchain (Vite recommended).

Contributing

Contributions are welcome. Suggested workflow:

- Fork the repository and create a branch for your change.
- Keep changes small and focused (e.g. translation improvements, minor UI tweaks).
- Open a pull request with a clear description and screenshots if the change affects the UI.

Troubleshooting

- No audio on first try: browser blocked autoplay — click any button (for example the modal) to provide a user gesture.
- CDN blocked: if Tailwind or Vue fails to load (offline environment), the page may not render correctly — consider
  serving libraries locally or adding a build step.

Contact

- Author: Jonatas — https://www.linkedin.com/in/jonatas-costa-dev/
- Live site: https://nobreaks.net

Thank you for trying No Breaks — feel free to open an issue or PR with suggestions or fixes.
