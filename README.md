# Tsuchibue · 5-Hole Ocarina Fingering Maker

五孔土笛指法生成器。点击音符生成指法图，支持播放、转调、休止、半孔、全屏、自动保存和 JSON 导入导出。

**Live:** https://tsuchibue.web.app

## Features

- 17 UI languages. The first visit picks one from the browser language; after that, the language menu choice is saved. `?lang=ja` forces a language.
- A single static page with no build step: `public/index.html` + `public/i18n.js`.
- Google Analytics 4 (`G-QH1E2W14T5`). It stays off for `file://` and localhost. Custom events: `play_sequence`, `export_sequence`, `import_sequence`, `language_change`.

## Adding a language

Add a new block to `public/i18n.js` keyed by a BCP 47 code, copying every key from `en`. Set `_dir: "rtl"` for right-to-left scripts.

## Examples

`examples/` holds sample sequences you can load with the Import button.

## Deploy

Every push to `main` deploys to Firebase Hosting (project `tsuchibue`) through GitHub Actions. The workflow authenticates with Workload Identity Federation, so the repo stores no keys.

Manual deploy:

```sh
firebase deploy --only hosting --project tsuchibue
```

Local preview:

```sh
npx serve public
```
