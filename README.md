# Retro-82 VS Code Theme Extension

VS Code theme extension for `Retro '82`.

## Install

Install from the VS Code Marketplace:

```bash
code --install-extension oldjobobo.retro-82-theme
```

Or install a local `.vsix` directly:

```bash
code --install-extension ./retro-82-theme-*.vsix
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
