 Overlay Extension

Lightweight React-based Chrome extension popup for launching and managing favorite AI tools.

- Core UI & logic: [`App`](App.tsx)  
- Tool definitions: [`AI_TOOLS`](constants.ts), [`STORAGE_KEY`](constants.ts), [`ACCENT_COLORS`](constants.ts)  
- Types: [`AITool`](types.ts), [`ToolCategory`](types.ts)

Files
- [.env.local](.env.local)
- [.gitignore](.gitignore)
- [App.tsx](App.tsx)
- [constants.ts](constants.ts)
- [index.html](index.html)
- [index.tsx](index.tsx)
- [manifest.json](manifest.json)
- [metadata.json](metadata.json)
- [package.json](package.json)
- [README.md](README.md)
- [tsconfig.json](tsconfig.json)
- [types.ts](types.ts)
- [vite.config.ts](vite.config.ts)

Features
- Quick-launch list of AI tools with categories and drag-and-drop ordering (powered by @dnd-kit).
- Persisted settings (enabled tools, order, accent color, collapsed categories) using the storage key [`STORAGE_KEY`](constants.ts).
- Master power toggle and "Launch Selected" action that opens tools in popup windows.
- Accent color picker using the values in [`ACCENT_COLORS`](constants.ts).

Getting started (local dev)
1. Install dependencies:
   ```bash
   npm install
   ```
2. Start the dev server:
   ```bash
   npm run dev
   ```
3. Open the extension popup during development by loading the `dist` build into Chrome (see Build below) or run the app in a browser via Vite and open [index.html](index.html).

Build & package
- Build the production bundle:
  ```bash
  npm run build
  ```
- The build output can be packaged into a Chrome extension. The extension's metadata is in [manifest.json](manifest.json) and [metadata.json](metadata.json).

Project layout
- App entry: [index.tsx](index.tsx) mounts the [`App`](App.tsx) component.
- UI: [App.tsx](App.tsx) — components, modal, settings, and Drag & Drop behavior.
- Tool list & constants: [constants.ts](constants.ts).
- Types: [types.ts](types.ts).
- Vite config: [vite.config.ts](vite.config.ts).
- Static popup: [index.html](index.html).

Notes & tips
- Chrome extension permissions required are listed in [manifest.json](manifest.json). The UI expects to run in an extension environment but falls back to window.open for non-extension testing.
- Settings persist to chrome.storage.local when available, otherwise to localStorage under the key defined by [`STORAGE_KEY`](constants.ts).
- To change environment variables for builds, use `vite.config.ts` and `.env.local`.

Contributing
- Fork, create a feature branch, add tests and docs, then open a pull request.
- Keep UI behavior consistent with the patterns in [App.tsx](App.tsx) and update [`AI_TOOLS`](constants.ts) when adding/removing tools.


