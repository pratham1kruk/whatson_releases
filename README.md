<div align="center">

<img src="assets/icon.png" alt="Whatson Logo" width="96" height="96" />

# whatson?

**Offline AI context generator for codebases.**  
100% local · No cloud · No API keys · No telemetry

[![License: MIT](https://img.shields.io/badge/License-MIT-7c6dfa.svg?style=flat-square)](LICENSE)
[![Version](https://img.shields.io/badge/version-0.1.0-4fc3a1.svg?style=flat-square)](https://github.com/pratham1kruk/whatson/releases)
[![Platform](https://img.shields.io/badge/platform-Windows%20%7C%20Linux-f0883e.svg?style=flat-square)](#platform-support)
[![Powered by](https://img.shields.io/badge/model-qwen2.5--coder:1.5b-blue.svg?style=flat-square)](https://ollama.com)

</div>

---

Whatson scans your codebase and generates a `context.md` with a project overview, full file tree, and per-file analysis — powered by **`qwen2.5-coder:1.5b`** via [Ollama](https://ollama.com). Everything runs on your machine.

---

## How it works

```
  You run a command in VS Code
           │
           ▼
  Extension detects your OS
     ├── Windows → engine/whatson.exe
     └── Linux   → engine/whatson
           │
           ▼
  Checks for Ollama → installs if missing (asks first)
           │
           ▼
  Pulls qwen2.5-coder:1.5b → one-time ~1 GB download
           │
           ▼
  Scans codebase → analyzes each file → writes context.md
```

---

## Installation

### Windows

```
1. Download  →  whatson-installer.exe
2. Run the installer
3. Follow the setup wizard
```

> Installs the Whatson binary to `Program Files\Whatson` and auto-installs the VS Code extension.

### Linux (Debian / Ubuntu)

```bash
sudo dpkg -i whatson_0.1.0_amd64.deb

# Fix missing dependencies if needed
sudo apt-get install -f
```

### What gets installed

- Whatson binary (standalone executable)
- VS Code extension (`.vsix` installed via `code --install-extension`)

---

## Quick Start

**1. Install the extension**
```bash
code --install-extension whatson-0.1.0.vsix
```

**2. Open a project in VS Code**
```
File → Open Folder → select your project
```

**3. Run**
```
Ctrl+Shift+P → getparent
```

`context.md` will appear in your project root. Done.

---

## Commands

| Command | What it does |
|---|---|
| `whatson?` | Activate extension for current workspace |
| `getparent` | Generate `context.md` for the entire workspace |
| `getson <path>` | Generate `context.md` for a subfolder |
| `getdaughter <path>` | Generate `context.md` for any folder anywhere |
| `showstatus` | Show usage log with timestamps |
| `wsleep` | Deactivate extension |

**Optional flags**

| Flag | What it does |
|---|---|
| `--optional` | Also generate `architecture<i>.md`, `api_map<i>.md`, `dependency_graph<i>.md` |
| `--quiet` | Suppress per-file output |

---

## CLI Usage

Use the engine directly, without the VS Code extension:

```bash
# Windows
whatson.exe getparent
whatson.exe getson src/components
whatson.exe getdaughter C:\other-project
whatson.exe showstatus
whatson.exe wsleep

# Linux
./whatson getparent
./whatson getson src/components
./whatson getdaughter /home/user/other-project
```

> Add `--optional` to any generation command for extra docs.

---

## Platform Support

| OS | Status |
|---|---|
| Windows 10+ | ✅ Supported |
| Ubuntu / Debian | ✅ Supported |
| Fedora / Arch | ✅ Supported |
| macOS | 🔜 Coming soon |

---

## Requirements

- Windows 10+ or Linux (Debian/Ubuntu/Fedora/Arch)
- VS Code (for the extension)
- Internet connection for the initial Ollama + model setup (first run only)

---

## 🔒 Privacy

> **Your code never leaves your machine.**

- All analysis runs **100% locally** via Ollama
- No code, filenames, or metadata is ever transmitted
- No telemetry, no accounts, no API keys required
- Fully offline after the initial model download

---

## License

MIT — see [LICENSE](https://github.com/pratham1kruk/whatson_releases/blob/main/LICENSE)

---

<div align="center">

Made by [Pratham Kumar Uikey](https://github.com/pratham1kruk) &nbsp;·&nbsp; `v0.1.0`

</div>
