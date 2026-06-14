# ggwave (Tauri)

Desktop app for sending and receiving data over audio using [ggwave](https://github.com/ggerganov/ggwave).

## Prerequisites

- [Node.js](https://nodejs.org/)
- [Rust](https://www.rust-lang.org/tools/install)

## Development

```bash
npm install
npm run tauri dev
```

## Build

```bash
npm run tauri:build
```

On macOS, the app bundle is at:

`src-tauri/target/release/bundle/macos/ggwave.app`

## Releases

Pushing a version tag triggers GitHub Actions to build macOS (Apple Silicon + Intel) and Linux binaries and attach them to a GitHub release.

1. Bump `version` in `src-tauri/tauri.conf.json` (and `package.json` if you keep them in sync).
2. Commit and push.
3. Create and push a matching tag:

```bash
git tag v0.1.0
git push origin v0.1.0
```

You can also run the **release** workflow manually from the Actions tab.

Built artifacts include macOS `.dmg`/`.app` bundles and Linux `.AppImage`, `.deb`, and `.rpm` packages.

## Usage

1. Enter text in **Tx Data** and click **Send** to transmit it as audio.
2. Click **Start capturing** to listen via the microphone and decode incoming ggwave signals.
3. Decoded text appears in **Rx data**.

The app requests microphone access on first capture (required for receive).
