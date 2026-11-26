# Unforgetter plugin for Antigravity

Unforgetter gives your AI assistant access to your saved project memory: current decisions, preferences, open questions and project context, with the source each one comes from. This is the Unforgetter plugin for Google Antigravity.

## What this plugin contains

- `plugin.json`: the plugin manifest.
- `mcp_config.json`: one remote MCP server, `unforgetter`, at https://app.unforgetter.com/mcp. You sign in with OAuth in your browser; the file holds no tokens, keys or headers.
- One skill (`skills/unforgetter-memory`): written guidance that tells the assistant when to load project context, how to show sources, and when to save a decision, rule, preference or correction that you stated.
- One always-on rule (`rules/AGENTS.md`): a short reminder to load project context before project work and to save what you state in the same turn.
- An icon.

It has no hooks and no scripts. It runs no code on your machine.

Add Unforgetter only once in any app. If its tools are missing, the skill and the rule tell the assistant to say so and not to claim that anything was saved.

## Saved updates

When you state a decision, preference or correction, the assistant can send it to Unforgetter as a proposed update, if the connection and the collection allow it. Unforgetter processes proposals automatically in the cloud. Each proposal is either accepted as current memory, which can replace an older entry, or deferred with a reason, and the assistant can check the outcome. The assistant confirms each save with a short "Saved to Unforgetter" line: the proposal has been received and stored. Until a proposal is accepted, it is not current memory.

## What is sent where

Unforgetter (app.unforgetter.com) only receives what the assistant sends in a tool call. It does not capture your conversations continuously. Unforgetter uses OpenAI to process proposed updates and to create search embeddings, for some memory and for the task summaries and search queries the assistant sends when it reads or searches memory. Reading memory sends relevant excerpts to the assistant.

## Revoking access

Revoke an app's access at https://app.unforgetter.com/account, and also remove the plugin in Antigravity. Removing it in the app alone may not revoke access. Revoking access does not delete saved memory.

## Links

- Documentation: https://unforgetter.com/docs
- Privacy: https://unforgetter.com/privacy
- Terms: https://unforgetter.com/terms
- Support: https://unforgetter.com/support

## License

MIT. See the `LICENSE` file.
