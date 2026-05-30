# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Purpose

PlugginVault is a registry/vault for storing plugin manifests and metadata. The name "Pluggins" (with the double-g) is intentional and used throughout the codebase — preserve this spelling in all files, directory names, and identifiers.

## Repository Structure

- `Pluggins/` — directory for storing plugin files or subdirectories, one per plugin
- `registry.json` — top-level registry manifest listing all plugins (see format below)

## Registry Format

The `registry.json` file at the repo root describes the vault and its plugins:

```json
{
  "name": "<registry-name>",
  "description": "<registry description>",
  "owner": {
    "name": "...",
    "email": "..."
  },
  "plugins": [
    {
      "name": "<plugin-id>",
      "description": "...",
      "version": "<semver>",
      "source": "<relative path within Pluggins/>",
      "author": {
        "name": "...",
        "email": "..."
      }
    }
  ]
}
```

When adding a new plugin, create its directory under `Pluggins/` and add its entry to the `plugins` array in `registry.json`.

## Development

There is no build system, test runner, or linter configured yet. All work is file-based — editing JSON manifests and adding plugin source files.
