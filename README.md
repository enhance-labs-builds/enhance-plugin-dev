# Enhance for agents

Enhance gives Claude Code, Codex, Cursor and agents run through Conductor a shared visual canvas for product design, feedback and interactive prototypes.

This repository is the **development** channel. Its catalogue name is `enhance-dev` and its exact plugin version is `1.0.0-dev.sha-f2b63710f195.f55d2a01aa4e`.

Install **Enhance** from your agent's plugin marketplace for your user account. The plugin starts its pinned MCP runtime and opens browser sign-in; it does not need a token, project file, separate CLI install, or terminal setup. If a marketplace listing is not yet available, copy the setup prompt from [Enhance](https://enhance3.karunalabs.ai/docs) and let the host configure its supported user-level MCP connection.

For a direct catalogue install, Claude Code uses `claude plugin install enhance-dev@enhance-dev --scope user`; Codex uses `codex plugin add enhance-dev@enhance-dev`. Use the host's plugin update action (Claude `plugin update`, Codex marketplace upgrade, or Cursor Customize) to refresh the immutable cached version. Uninstall through that same native plugin surface. If cached bytes are missing or corrupt, uninstall and reinstall the same version; browser credentials are owned by the MCP runtime and remain separate.

After connecting, try one of these:

- Design a product screen on my Enhance canvas.
- Publish and visually verify this prototype.
- Apply the actionable feedback on my canvas.
- Reconcile this canvas design into my prototype source.

Conductor uses the plugin and MCP support of the Claude Code or Codex agent selected for the workspace. Provider setup, recovery and update instructions are maintained at [https://enhance3.karunalabs.ai/docs](https://enhance3.karunalabs.ai/docs).

## Trust and support

The generated plugin contains only provider manifests, four workflow skills, launch configuration and brand assets. It stores no credential. Enhance authentication happens in the browser and the local runtime owns its user credential.

- [Documentation](https://enhance3.karunalabs.ai/docs)
- [Privacy](https://enhance3.karunalabs.ai/privacy-policy)
- [Terms](https://enhance3.karunalabs.ai/docs/terms)
- [Support](https://enhance3.karunalabs.ai/docs/support)
