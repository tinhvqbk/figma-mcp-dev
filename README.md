# figma-mcp-dev

Lets **Claude Code read the Figma design you have open in Chrome**, including files you can only view: the
properties of a node (layout, sizing, padding, gap, borders, colors), the pages and layers, and a PNG export.

Two pieces work together: a small MCP server (`figma-mcp-dev`, one binary) and the Chrome extension
**MCP Bridge for Figma**. This repository hosts the releases; the source is private.

## Install (macOS, Apple silicon or Intel)

1. **Install the server.** In Claude Code, ask it to run this (or run it in a terminal):

   ```sh
   curl -fsSL https://github.com/tinhvqbk/figma-mcp-dev/releases/latest/download/install.sh | sh
   ```

   It downloads the binary for your Mac, checks its SHA-256, installs it to `~/.local/bin/figma-mcp-dev`, registers
   it with Claude Code, and prints a **pairing token**.

2. **Install the Chrome extension** [MCP Bridge for Figma](https://chromewebstore.google.com/detail/mcgjkaemfnihcknhmcldlpaidpiokhmf) from the Chrome Web Store, click its
   toolbar icon, paste the token, and click **Save**.

3. Start a **new** Claude Code session, open a design on figma.com in Chrome, and ask Claude:
   "call figma_web_status".

Update: run the same command again. Show the token again: `figma-mcp-dev token`.

## What Claude can do

| Tool | Purpose |
|---|---|
| `figma_web_status` | whether the extension is connected, which Figma tab it acts on, the selection |
| `figma_web_inspect` | properties panel of a node (by node id, or the current selection) |
| `figma_web_layers` | pages and the layer rows currently shown in the left panel |
| `figma_web_export` | PNG of a node via Figma's Export section (only if the file allows export) |

It reads only what Figma's web UI already shows you. Nothing leaves your computer: the extension talks only to the
server on `localhost`, and the server only to Claude Code. Privacy policy: [PRIVACY.md](PRIVACY.md).

## Uninstall

```sh
claude mcp remove figma-mcp-dev -s user
rm ~/.local/bin/figma-mcp-dev
rm -rf ~/.config/figma-mcp-dev
```

Then remove the extension in Chrome.
