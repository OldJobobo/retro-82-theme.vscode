# Publishing And Updating Retro '82

This guide is for publishing updates to the VS Code extension:
`oldjobobo.retro-82-theme`.

## Prerequisites

- You have a VS Marketplace publisher: `oldjobobo`
- You have a valid PAT with `Marketplace -> Manage`
- You are in Node LTS (recommended: Node 22 via `mise`)

## One-Time Login

```bash
npm i -g @vscode/vsce
vsce login oldjobobo
```

## Update Workflow

1. Make your theme/metadata changes.
2. Run a local package build.
3. Verify package contents.
4. Publish version bump (`patch`, `minor`, or `major`).

### 1) Package

```bash
npm run package
```

### 2) Verify VSIX Contents

```bash
unzip -l retro-82-theme-*.vsix
```

Expected: includes extension files such as:
- `extension/package.json`
- `extension/themes/base16-retro-82-color-theme.json`

If you only see manifest files, stop and fix your Node/vsce environment before publishing.

### 3) Publish Update

Use one of:

```bash
vsce publish patch
vsce publish minor
vsce publish major
```

Or publish exact version:

```bash
vsce publish 0.0.2
```

## Post-Publish Checks

1. Confirm listing opens:
   - `https://marketplace.visualstudio.com/items?itemName=oldjobobo.retro-82-theme`
2. In VS Code, verify the theme appears as:
   - `Retro '82`

## Notes

- Run all `vsce` commands from the repository root.
- Keep extension ID stable: `oldjobobo.retro-82-theme`.
- Keep `package.json` theme contribution aligned with:
  - `"label": "Retro '82"`
  - `"path": "./themes/base16-retro-82-color-theme.json"`

## Versioning Workflow (Recommended)

Use npm scripts to keep SemVer + Git tags consistent:

```bash
npm run version:patch   # or version:minor / version:major
```

For one command that versions and builds:

```bash
npm run release:patch   # or release:minor / release:major
```

After bumping, update `CHANGELOG.md`, then publish with `vsce publish <version|patch|minor|major>`.
