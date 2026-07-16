# Proofread

A single-file, no-signup grammar and style checker. Paste your text, get inline highlighted issues with one-click fixes — powered by any model on OpenRouter.

**Live: https://023b.github.io/grammar-checker/**

## What it does

- **Grammar, spelling, punctuation, style, and word-order checks**, filterable by category
- **Inline highlights** — click a flagged phrase to see the suggested fix and apply it
- **Auto-check** as you type, or manual Check on demand
- **Export** — `.txt`, `.md`, `.html`, or Word (paste method)
- **Dark/light theme**, persisted
- **Crash recovery** — autosaves as you type; a floating restore button (bottom-right) recovers your last draft even if the tab closes unexpectedly

## Why it's just one HTML file

No backend, no build step, no server. Open the file (or the GitHub Pages link) and it works. Your text stays in your browser's local storage — nothing is uploaded anywhere except what you explicitly send to OpenRouter to check.

## Setup

1. Open the [live link](https://023b.github.io/grammar-checker/) (or download `index.html` and open it locally).
2. Get a free API key at [openrouter.ai/keys](https://openrouter.ai/keys) — no card required.
3. Paste it in on first launch. Your key is stored only in your browser (`localStorage`) — there's no server for it to leak to.
4. Pick a model. The dropdown fetches OpenRouter's live model list and surfaces a free pick, a second free pick, and two paid options (useful when a free model misses tricky cases) — or type in any model ID yourself via "Custom model…".

## Running it locally

It's one HTML file. Download `index.html`, double-click it. Done.

```bash
git clone https://github.com/023b/grammar-checker.git
cd grammar-checker
python3 -m http.server 8000
```

## Privacy

Everything — your draft, your API key — lives in your browser's `localStorage`. The only outbound calls are:
- OpenRouter's `/models` endpoint (no key required, just fetches the current model list)
- OpenRouter's `/chat/completions` endpoint (your text + your key, direct to OpenRouter, when you run a Check)

## Known limitations

- `localStorage` is per-browser, per-device — no account system, no sync
- Free OpenRouter models have rate limits (typically 20 req/min) and the free lineup can shift — an OpenRouter-side constraint
- Word export uses a paste-into-Word method rather than a native `.docx` binary

## License

MIT.

## Feedback

Open an issue, or fork it and make it yours.
