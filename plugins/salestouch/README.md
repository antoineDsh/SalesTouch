# SalesTouch

![Version 0.5.4](https://img.shields.io/badge/version-0.5.4-111827)
![License MIT](https://img.shields.io/badge/license-MIT-16a34a)

Turn your AI agent into a LinkedIn prospecting operator. SalesTouch helps it
find and qualify the right people, start conversations, manage follow-ups, and
turn outreach into real opportunities. This Claude plugin connects to the
OAuth-protected SalesTouch remote server and exposes account, conversation,
lookup, outreach, engagement, publishing, queue, and paginated extraction
tools.

SalesTouch is not affiliated with, endorsed by, or sponsored by LinkedIn.

## Install

### Claude Desktop or Cowork

1. Open `Customize` → `Add a plugin` → `Create a plugin` →
   `Add a marketplace`.
2. Add `antoinedsh/salestouch`.
3. Enable `salestouch` from the `Personal` tab.
4. Run `/mcp` and complete the browser authorization.

### Claude Code

```text
/plugin marketplace add antoinedsh/salestouch
/plugin install salestouch@salestouch
/mcp
```

### Manual MCP configuration

```json
{
  "mcpServers": {
    "salestouch": {
      "type": "http",
      "url": "https://www.salestouch.io/api/mcp",
      "headers": {
        "Accept": "application/json, text/event-stream"
      },
      "oauth": {
        "authServerMetadataUrl": "https://www.salestouch.io/.well-known/oauth-authorization-server/api/auth"
      }
    }
  }
}
```

Do not add a LinkedIn password, cookie, token, or API secret. Claude receives
only the scoped SalesTouch OAuth authorization.

## Supported workflows

- List connected LinkedIn accounts.
- List, search, and read conversations.
- Read the authenticated feed.
- Look up profiles, companies, profile posts, and individual posts.
- Inspect invitation follow-ups and queued message state.
- Send messages, invitations, and post-acceptance follow-ups.
- Like or comment on posts and publish posts.
- Cancel queued SalesTouch actions.
- Extract people from searches, post engagement, groups, profile viewers, and
  company page viewers.
- Read stored extraction results page by page.

## Response contract

Each tool exposes a strict input schema, tool annotations, and an output
schema. Successful calls return MCP `structuredContent` and temporarily retain
the equivalent JSON text content for compatibility. Errors use
`{code, message, retryable}` without internal provider metadata.

Read tools are non-destructive and idempotent. Messages, invitations, likes,
comments, publications, and queue cancellation mutate state and should run
only after the user verifies the exact target and content.

## Example workflows

### Lead research

Look up a profile, read recent posts, and draft a tailored message without
sending it.

### Conversation reply

Find a conversation by profile URL, read its latest messages, draft a reply,
then authorize `linkedin_message` only after reviewing the recipient and text.

### Post engagement extraction

Extract reactions or comments from a post, inspect the bounded preview, and
page through the stored result with `scrape_result_page`.

## Troubleshooting and limitations

Reconnect OAuth if authorization expires. Confirm that the workspace has an
active plan and a connected LinkedIn account, then test `linkedin_accounts`.
Availability and results depend on platform access, permissions, rate limits,
and source data. SalesTouch does not bypass LinkedIn safeguards.

- [Setup](../../SETUP.md)
- [Support](../../SUPPORT.md)
- [Security](../../SECURITY.md)
- [Review test cases](../../REVIEW_TESTS.md)
- [Documentation](https://www.salestouch.io/docs)
- [Privacy](https://www.salestouch.io/privacy)
- [Terms](https://www.salestouch.io/terms)
- Email: [support@salestouch.io](mailto:support@salestouch.io)

This public distribution wrapper is licensed under the
[MIT License](../../LICENSE). The hosted SalesTouch backend remains
proprietary.
