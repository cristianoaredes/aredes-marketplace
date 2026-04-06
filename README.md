# Aredes Marketplace — Claude Code Plugins

> A curated collection of [Claude Code](https://claude.ai/code) plugins for iOS development, App Store automation, and prompt engineering — ready to install in one command.

[![Plugins](https://img.shields.io/badge/Plugins-2-green.svg)](#available-plugins)
[![Claude Code](https://img.shields.io/badge/Claude%20Code-Marketplace-blueviolet.svg)](https://claude.ai/code)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

---

## What Is This?

**Aredes Marketplace** is a Claude Code plugin marketplace maintained by [Cristiano Arêdes](https://github.com/cristianoaredes). It lets you install curated plugins directly through the `claude plugin` CLI — no npm, no manual file copying.

Once you add this marketplace, all listed plugins become available to install, update, and manage from your terminal.

---

## Quick Start

### 1. Add this marketplace to Claude Code

```bash
claude plugin marketplace add cristianoaredes/aredes-marketplace
```

### 2. Install a plugin

```bash
# Install a specific plugin from this marketplace
claude plugin install build-ios-apps@aredes-marketplace

# Or just by name if aredes-marketplace is the only source
claude plugin install build-ios-apps
```

### 3. Verify installation

```bash
claude plugin list
```

---

## Managing the Marketplace

```bash
# List all configured marketplaces
claude plugin marketplace list

# Update marketplace registry (check for new plugins)
claude plugin marketplace update aredes-marketplace

# Remove the marketplace
claude plugin marketplace remove aredes-marketplace
```

---

## Available Plugins

### `build-ios-apps`

**27 AI skills for iOS and App Store development.**

Covers the full iOS shipping lifecycle — from writing SwiftUI views to submitting to the App Store.

| Category | What's included |
|---|---|
| SwiftUI & iOS | Liquid Glass (iOS 26+), performance audits, UI patterns, view refactoring, simulator debugging |
| Builds & Releases | xcodebuild archive/export, build lifecycle, App Store submission, preflight checks |
| TestFlight | Beta groups, testers, crash triage, performance diagnostics |
| Signing | Bundle IDs, certificates, provisioning profiles |
| Metadata | App Store copy sync, What's New writer, ASO audit, multi-locale localization |
| Monetization | PPP pricing, RevenueCat catalog sync, IAP localization |
| Screenshots | Simulator capture pipeline, framing, upload |
| macOS | Developer ID notarization |

**Requires:** [XcodeBuildMCP](https://github.com/getsentry/XcodeBuildMCP) (for simulator skills) and [`asc` CLI](https://asccli.sh) (for App Store Connect skills).

```bash
claude plugin install build-ios-apps@aredes-marketplace
```

→ [Full documentation](https://github.com/cristianoaredes/build-ios-apps)

---

### `prompt-optimizer`

**Prompt sharpener and engineering standards for Claude Code.**

Reverse-engineered insights into how Claude processes prompts, with tuning profiles, CLAUDE.md templates, API injection controls, and agent-driven workflows.

| What's included |
|---|
| `/sharpen` — rewrite any prompt for clarity and precision |
| Tuning profiles (concise, verbose, technical, creative) |
| CLAUDE.md templates for project-specific instructions |
| Token budget controls and output format injection |
| Agent workflow patterns for multi-step tasks |

```bash
claude plugin install prompt-optimizer@aredes-marketplace
```

→ [Full documentation](https://github.com/cristianoaredes/claude-prompt-optimizer)

---

## Managing Installed Plugins

```bash
# List all installed plugins and their status
claude plugin list

# Disable a plugin temporarily
claude plugin disable build-ios-apps

# Re-enable it
claude plugin enable build-ios-apps

# Update a plugin to the latest version
claude plugin update build-ios-apps

# Uninstall completely
claude plugin uninstall build-ios-apps
```

---

## How Claude Code Plugin Marketplaces Work

A marketplace is a GitHub repository with a `.claude-plugin/marketplace.json` manifest that lists plugins and their sources. When you run `claude plugin marketplace add`, Claude Code registers the repo and can resolve plugin names to their install sources.

You can have multiple marketplaces active at once. To install from a specific one, use `plugin-name@marketplace-name`. Without the `@`, Claude Code searches all registered marketplaces in order.

```
~/.claude/plugins/
├── marketplaces/
│   └── aredes-marketplace/   ← registry cache
└── cache/
    └── aredes-marketplace/   ← installed plugin files
```

---

## License

MIT — see [LICENSE](LICENSE).
