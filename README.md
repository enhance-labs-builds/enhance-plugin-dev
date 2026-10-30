# Enhance for agents

Enhance gives Claude Code, Codex, Cursor and agents run through Conductor a shared visual canvas for product design, feedback and interactive prototypes.

This repository is the **development** channel. Its catalogue name is `enhance-dev` and its exact plugin version is `1.0.35-dev.sha-723971c4de28.e546f641be2f`.

Install **Enhance** from your agent's plugin marketplace for your user account. The plugin starts its pinned MCP runtime. After restarting, ask your agent to sign you in; the agent calls `connection_connect` to open the browser, then checks `connection_status` and a read such as `canvas_find`. You do not need a token, project file, separate CLI install, or terminal setup. If a marketplace listing is not yet available, copy the setup prompt from [Enhance](https://enhance3.karunalabs.ai/docs) and let the host configure its supported user-level MCP connection.

If a legacy development entry shares production credentials, replace it with **Enhance Development / enhance-dev**, whose bundled runtime is `enhance-dev-mcp` and whose store is `~/.config/enhance-development`. The standalone package is `@enhance-eng/enhance-dev`; renaming a production executable does not isolate it. Preserve the working credential and relevant host configuration locally. Preserve and validate any occupied destination first; transfer only a verified development credential into an empty destination, otherwise use ordinary browser sign-in with consent. Disable the old shared-store entry and reload the host before reconnecting production. Verify both actual MCP connections with `connection_status` and an authorized read; `doctor` alone does not prove authentication. Record actual replacement versions and reload results without secrets. Rollback must preserve credentials and unrelated settings and leave the unsafe entry disabled. A new release cannot patch an old cached process. If the repair does not complete, contact Enhance through [Support and recovery](https://enhance3.karunalabs.ai/docs/support) and include the recorded versions and connection results, never credentials.

For a direct catalogue install, Claude Code uses `claude plugin install enhance-dev@enhance-dev --scope user`; Codex uses `codex plugin add enhance-dev@enhance-dev`. Use the host's plugin update action (Claude `plugin update`, Codex marketplace upgrade, or Cursor Customize) to refresh the immutable cached version. Uninstall through that same native plugin surface. If cached bytes are missing or corrupt, uninstall and reinstall the same version; browser credentials are owned by the MCP runtime and remain separate.

For Claude Desktop, download [the extension bundle](https://github.com/enhance-labs-builds/enhance-plugin-dev/releases/download/plugin-v1.0.35-dev.sha-723971c4de28.e546f641be2f/enhance.mcpb) and [its SHA-256 checksum](https://github.com/enhance-labs-builds/enhance-plugin-dev/releases/download/plugin-v1.0.35-dev.sha-723971c4de28.e546f641be2f/enhance.mcpb.sha256) from this exact release. Open the bundle in Claude Desktop and complete the native installation. It includes the same runtime and four workflows. Ask Claude to connect Enhance, complete browser sign-in, and verify a canvas read. Manage updates and removal in Claude's extension settings. The development and stable bundles have separate identities and credentials.

After connecting, try one of these:

- Design a product screen on my Enhance canvas.
- Publish and visually verify this prototype.
- Apply the actionable feedback on my canvas.
- Reconcile this canvas design into my prototype source.

Conductor uses the plugin and MCP support of the Claude Code or Codex agent selected for the workspace. Provider setup, recovery and update instructions are maintained at [https://enhance3.karunalabs.ai/docs](https://enhance3.karunalabs.ai/docs).

## Trust and support

The generated plugin contains provider manifests, four workflow skills, its bundled MCP runtime, launch configuration and brand assets. It stores no credential. Enhance authentication happens in the browser and the local runtime owns its user credential.

- [Documentation](https://enhance3.karunalabs.ai/docs)
- [Privacy](https://enhance3.karunalabs.ai/privacy-policy)
- [Terms](https://enhance3.karunalabs.ai/docs/terms)
- [Support](https://enhance3.karunalabs.ai/docs/support)
