# SalesTouch

![Version 0.9.2](https://img.shields.io/badge/version-0.9.2-111827)

[English](README.md) · [Français](docs/fr.md) · [Deutsch](docs/de.md) · [Español](docs/es.md) · [Português](docs/pt.md) · [Italiano](docs/it.md)

**LinkedIn outreach for AI agents.** SalesTouch is a LinkedIn MCP that connects
Claude to prospect research, conversations, messaging, publishing, follow-ups
and queues. SalesTouch is not affiliated with or endorsed by LinkedIn.

## Requirements

Use a SalesTouch workspace with an active plan and a connected LinkedIn account.
Sales Navigator features require the corresponding account access. Results
remain subject to permissions, source availability and platform limits.

## Install in Claude Code

Run these commands in Claude Code:

```text
/plugin marketplace add antoineDsh/SalesTouch
/plugin install salestouch@salestouch
```

Restart Claude Code to load the plugin, then run `/mcp`, choose SalesTouch and
complete the browser authorization. No LinkedIn password, cookie or API key
belongs in the conversation or plugin configuration.

## Install in Claude Desktop or Cowork

Open **Customize → Plugins**. In **Personal plugins**, select **+ → Add
marketplace**, choose the repository option and enter `antoineDsh/SalesTouch`.
Install and enable `salestouch`, then authorize its SalesTouch connector.
Available controls depend on your Claude plan and organization settings.

## Three prompts to start

1. "List my connected LinkedIn accounts with SalesTouch."
2. "Research this LinkedIn profile and its recent posts, then draft a relevant
   introduction without sending it: [profile URL]."
3. "Read this LinkedIn conversation, summarize what the prospect needs, and
   draft a reply without sending it: [conversation ID or profile URL]."

Replace bracketed values with your own targets. You can also extract search
results or post engagement, page through stored results and download exports.
Review the exact recipient, content and time before approving a message,
invitation, comment, publication or scheduled action. Pending means queued,
not delivered. Inspect the queue before retrying a write.

## Connection and support

The remote MCP endpoint is `https://www.salestouch.io/api/mcp`, using Streamable
HTTP and OAuth. If authorization fails, reconnect the SalesTouch connector,
verify your workspace and LinkedIn connection, then retry the account prompt.
Share only a safe error code and reproduction steps with support, without
credentials, tokens or private messages.

- [Setup](SETUP.md) · [Support](https://www.salestouch.io/support) · [Security](SECURITY.md)
- [Documentation](https://www.salestouch.io/docs) · [Privacy](https://www.salestouch.io/privacy) · [Terms](https://www.salestouch.io/terms)
- [support@salestouch.io](mailto:support@salestouch.io)

The plugin files use the [MIT license](LICENSE). The hosted backend is proprietary.

## Version 0.9.2

Fixed Claude Code sign-in by requesting only the OAuth scopes needed by the MCP.

## Version 0.9.1

Updated installation guidance in six languages; setup and support files included
in the package; technical MCP analytics without conversation goals or tool
payloads. See the [changelog](CHANGELOG.md).
