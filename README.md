# SalesTouch

![Version 0.9.2](https://img.shields.io/badge/version-0.9.2-111827)
![License MIT](https://img.shields.io/badge/license-MIT-16a34a)

SalesTouch is the LinkedIn MCP for AI agents. It connects Claude, Codex,
ChatGPT, Cursor, and other MCP-compatible agents to LinkedIn search, research,
conversations, messaging, engagement, publishing, durable scheduling, queues,
account controls, and paginated extraction through an OAuth-protected remote
endpoint.

SalesTouch is not affiliated with, endorsed by, or sponsored by LinkedIn.

## Install

### Claude Desktop, Cowork, or Claude Code

See the [Claude installation guide](plugins/salestouch/README.md), available in
English, French, German, Spanish, Brazilian Portuguese and Italian.

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

## Example workflows

### 1. Research a lead without changing external state

1. Ask SalesTouch to look up a profile URL.
2. Ask for the profile's recent posts, then continue with `next_cursor` when older history is needed.
3. Ask the agent to summarize useful context and draft a message.
4. Review the draft; no message is sent until a mutation tool is authorized.

### 2. Review a conversation and send an exact reply

1. Search the conversation by profile URL.
2. Read the bounded message history.
3. Ask the agent to draft a reply without sending.
4. Confirm the recipient and exact text, then authorize `linkedin_message`.

### 3. Build a Sales Navigator audience from structured filters

1. Resolve ambiguous filter values with `linkedin_sales_navigator_search_parameters`.
2. Run `scrape_sales_navigator_companies` or `scrape_sales_navigator_people` with the returned ids.
3. To restrict people to extracted companies, pass the company `result_id` to `scrape_sales_navigator_people` as `company_result_id`.
4. Inspect the bounded preview, page with `scrape_result_page`, or use the signed CSV/JSONL export.

### 4. Turn post engagement into a paginated result

1. Provide a LinkedIn post URL.
2. Run `scrape_linkedin_post_reactions` or
   `scrape_linkedin_post_comments`. Comment scraping extracts root commenters by default; pass `include_replies: true` only when reply authors are needed.
3. Read the bounded preview and stored result id.
4. If a comment result returns `source_paging.exhausted: false`, call `scrape_linkedin_post_comments` again with `source_paging.arguments` to continue the LinkedIn source extraction in the same reply mode. Large sources pause automatically after a bounded provider-request budget, so a call may return fewer profiles than `limit` without losing progress.
5. Use `scrape_result_page` only to page through profiles already stored by one scrape call.

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
- [Support](SUPPORT.md)
- [Security](SECURITY.md)
- [Privacy](https://www.salestouch.io/privacy)
- [Terms](https://www.salestouch.io/terms)
- Email: [support@salestouch.io](mailto:support@salestouch.io)

The files in this public distribution wrapper are licensed under the
[MIT License](LICENSE). The hosted SalesTouch backend remains proprietary.
