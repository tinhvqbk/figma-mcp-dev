# Privacy policy: MCP Bridge for Figma

Last updated: 2026-10-15

MCP Bridge for Figma is a Chrome extension that connects Figma in your browser to the figma-mcp-dev server running on
your own computer, so that an AI coding assistant you run locally (such as Claude Code) can read the design you have
open.

## What the extension reads

On `www.figma.com` file pages only, and only when your local server asks for it:

- the text shown in Figma's right-hand properties panel and left-hand pages/layers panel;
- the URL and title of the Figma tab;
- an image of a design element, produced by Figma's own Export feature, when export is allowed for that file.

It does not read your cookies, passwords, or Figma account data, and it does not call Figma's APIs.

## Where the data goes

Only to `ws://localhost:3056`, a server on your own computer that you installed and run yourself. The extension does
not send any data to the developer or to any other remote server, and contains no analytics or tracking.

## What is stored

On your computer only, never synced or sent anywhere:

- the pairing token you paste into the popup and the popup settings (on/off, server port), in `chrome.storage.local`;
  remove the token with "Forget" in the popup, or everything by uninstalling the extension;
- the pinned tab and a list of the last 20 requests (time, kind, node id, result), in `chrome.storage.session`,
  cleared when the browser quits or with "Clear" in the popup.

## Contact

Questions: kyle.vqt@gmail.com
