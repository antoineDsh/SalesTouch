# SalesTouch

SalesTouch is a text-only remote MCP plugin that connects Claude to LinkedIn through SalesTouch.

## Supported capabilities

- List connected LinkedIn accounts.
- List, search, and read LinkedIn conversations.
- Read the LinkedIn feed.
- Look up member profiles, companies, profile posts, and posts.
- Inspect invitation follow-ups and queued message state.
- Send messages, invitations, and post-acceptance follow-ups.
- Like or comment on posts and publish LinkedIn posts.
- Cancel queued actions.
- Extract people from LinkedIn searches, Sales Navigator searches, post reactions, post comments, groups, profile viewers, and company page viewers.
- Read large stored extraction results page by page.

## Install

### Claude Desktop or Cowork

1. Open `Customize` → `Add a plugin` → `Create a plugin` → `Add a marketplace`.
2. Add `antoinedsh/salestouch`.
3. Enable `salestouch` from the `Personal` tab.
4. Run `/mcp` and complete the browser login.

### Claude Code

```bash
/plugin marketplace add antoinedsh/salestouch
/plugin install salestouch@salestouch
/mcp
```

## Manual MCP configuration

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

## Response format

SalesTouch tools return text content containing JSON. Claude reads that content and presents the useful result directly in the conversation.

## Examples

- “List my connected LinkedIn accounts.”
- “Look up this LinkedIn profile and show their recent posts.”
- “Find my conversation with this person and summarize the thread.”
- “Send this exact message to this LinkedIn profile.”
- “Extract everyone who commented on this LinkedIn post.”
