# Retro-82 VS Code Theme Extension

Local VS Code extension wrapper for `Retro-82`.
This extension is not published on the VS Code Marketplace.

## Install

Install the bundled `.vsix` directly:

```bash
code --install-extension ./retro-82-theme-0.0.1.vsix
```

## Rebuild VSIX (maintainers)

Requires `@vscode/vsce`.

```bash
npm run package
```

## Versioning

This project uses Semantic Versioning (`MAJOR.MINOR.PATCH`).

- `npm run version:patch`: backward-compatible fixes (`0.0.1` -> `0.0.2`)
- `npm run version:minor`: backward-compatible features (`0.0.1` -> `0.1.0`)
- `npm run version:major`: breaking changes (`0.0.1` -> `1.0.0`)

Each command updates `package.json`, creates a Git commit, and creates a Git tag.
Use `npm run release:patch|minor|major` to version and build the VSIX in one step.
