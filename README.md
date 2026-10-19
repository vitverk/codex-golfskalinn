# Skálinn

This package connects only to https://skalinn.golfskalinn.com/mcp. It contains workflow skills and public packaging
metadata, never credentials, private company context, operational data or permissions.
Set up, review connected clients, change permissions or revoke at https://skalinn.golfskalinn.com/external-access/mcp.
Each instance has a distinct plugin, server and catalog name that stays stable across updates.

## Claude

Install it on your Claude account, at https://claude.ai/customize/plugins (in the desktop app: **Customize** in the
chat, not the Code tab): choose **Add marketplace**, add https://github.com/vitverk-plugins/ai-plugins-golfskalinn, and install **Skálinn**.
On its **Connectors** tab choose **Connect**, keep the dialog's defaults and choose **Add**; choose
**Connect** again if the sign-in page does not open. Sign in to https://skalinn.golfskalinn.com: the page asks you to
authorize **Claude**, not Claude Code. Review permissions and choose **Connect**. The plugin then
also loads in Claude Code as a synced plugin, so don't install a second copy there. Then ask
`/skalinn` or **Set up my Skálinn connection** in a new chat.

For Claude Code without claude.ai, run `/plugin marketplace add` with https://github.com/vitverk-plugins/ai-plugins-golfskalinn, then
`/plugin install skalinn@skalinn`, and authenticate the server in `/mcp`. Without a repository,
upload this instance's single-plugin ZIP in **Customize → Plugins**, or keep this extracted folder and
run `claude plugin marketplace add . --scope user` and `claude plugin install skalinn@skalinn --scope user`.
Connection help: https://skalinn.golfskalinn.com/external-access/mcp/connect?client=claude

## Codex

Copy https://github.com/vitverk-plugins/ai-plugins-golfskalinn, open **Plugins → Add marketplace** and paste it. On the **Personal** tab, install
**Skálinn**, then run its setup skill. If connecting needs help, open https://skalinn.golfskalinn.com/external-access/mcp/connect, choose **Copy setup prompt**
and send it in a Codex chat, or use https://skalinn.golfskalinn.com/external-access/mcp/connect?method=manual for the Settings steps.
An agent with Node.js and the Codex CLI can check the connection with
`node plugins/skalinn/scripts/connect-codex.mjs --check`, and only after `authentication_required`
start one sign-in with `--login`. Account sign-in and permission review stay with you.

Without a repository, keep this extracted folder and run `codex plugin marketplace add .` and
`codex plugin add skalinn@skalinn`, or open **Install Codex.command** / **Install Codex.cmd**.
For an existing separately configured server at this exact origin, the DCR fallback is
`codex mcp login skalinn --oauth-client-registration dcr`.

## Permissions

Consent separately to workspace discovery, company context, business reads, development, outputs,
automation, commerce and delivery. Existing gadget access grants none of these automatically, and
consent never changes staff roles or bypasses approvals, review or promotion controls. Refresh tools
or start a new chat after permission changes. Returned data leaves Skálinn's sandbox.
