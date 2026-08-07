# SalesTouch

![Version 0.6.0](https://img.shields.io/badge/version-0.6.0-111827)
![License MIT](https://img.shields.io/badge/license-MIT-16a34a)

SalesTouch is an AI-native GTM prospecting platform. It helps agents research
and qualify prospects, build audiences, start conversations, manage follow-ups,
and execute controlled LinkedIn outreach. It provides account, conversation,
lookup, outreach, engagement, publishing, durable scheduling, queue, and paginated extraction tools
through an OAuth-protected remote endpoint.

SalesTouch is not affiliated with, endorsed by, or sponsored by LinkedIn.

## Install

### Claude Desktop, Cowork, or Claude Code

In Claude Desktop or Cowork, add the marketplace `antoinedsh/salestouch`, then
enable the `salestouch` plugin and complete OAuth from `/mcp`.

In Claude Code:

```text
/plugin marketplace add antoinedsh/salestouch
/plugin install salestouch@salestouch
/mcp
```

### Cursor

Install this repository as a Cursor plugin, or add the following remote MCP
configuration:

```json
{
  "mcpServers": {
    "salestouch": {
      "url": "https://www.salestouch.io/api/mcp"
    }
  }
}
```

### Any Streamable HTTP client

Use `https://www.salestouch.io/api/mcp` and name the server `salestouch`. The
client discovers the SalesTouch OAuth flow automatically; no static API key or
LinkedIn credential belongs in the MCP configuration.

## OAuth and first check

The browser authorization flow grants scoped SalesTouch access. LinkedIn
passwords, cookies, and authentication secrets are never shared with the AI
client.

Verify the connection with a read-only request:

> List the LinkedIn accounts connected to my SalesTouch workspace.

## Three complete workflows

### 1. Research a lead without changing external state

1. Ask SalesTouch to look up a profile URL.
2. Ask for the profile's recent posts.
3. Ask the agent to summarize useful context and draft a message.
4. Review the draft; no message is sent until a mutation tool is authorized.

### 2. Review a conversation and send an exact reply

1. Search the conversation by profile URL.
2. Read the bounded message history.
3. Ask the agent to draft a reply without sending.
4. Confirm the recipient and exact text, then authorize `linkedin_message`.

### 3. Turn post engagement into a paginated result

1. Provide a LinkedIn post URL.
2. Run `scrape_linkedin_post_reactions` or
   `scrape_linkedin_post_comments`.
3. Read the bounded preview and stored result id.
4. Continue with `scrape_result_page` until the result is complete.

## Safety and limitations

- Read tools are non-destructive and idempotent.
- Messages, invitations, likes, comments, and publications modify LinkedIn and
  are non-idempotent.
- These write tools accept `scheduled_for`; SalesTouch persists the action and
  reconnects a sleeping credential-based account when execution becomes due.
- Cancelling a queued action modifies SalesTouch state and cannot be assumed
  idempotent.
- Availability depends on an active SalesTouch plan, a connected LinkedIn
  account, platform availability, permissions, and usage limits.
- SalesTouch does not bypass LinkedIn safeguards. Users are responsible for
  reviewing targets and content and for complying with applicable platform
  rules and law.

## Troubleshooting

If OAuth fails, reconnect from the MCP client, confirm the endpoint, verify the
SalesTouch plan and connected account, then retry the read-only account check.
Never paste credentials, cookies, OAuth tokens, private messages, or prospect
data into a support request.

## Documentation and support

- [Documentation](https://www.salestouch.io/docs)
- [Getting started](https://www.salestouch.io/docs/getting-started)
- [Authentication and scopes](https://www.salestouch.io/docs/authentication)
- [Troubleshooting](https://www.salestouch.io/docs/troubleshooting)
- [OpenAI plugin submission](OPENAI_PLUGIN_SUBMISSION.md)
- [Claude directory submission](CLAUDE_DIRECTORY_SUBMISSION.md)
- [Support](SUPPORT.md)
- [Security](SECURITY.md)
- [Privacy](https://www.salestouch.io/privacy)
- [Terms](https://www.salestouch.io/terms)
- Email: [support@salestouch.io](mailto:support@salestouch.io)

The files in this public distribution wrapper are licensed under the
[MIT License](LICENSE). The hosted SalesTouch backend remains proprietary.
