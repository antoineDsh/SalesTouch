# SalesTouch

SalesTouch connects Claude to LinkedIn through an OAuth-protected remote MCP server.

The plugin provides LinkedIn account, conversation, lookup, outreach, engagement, publishing, queue, and stored extraction tools.

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

## Examples

- “List my connected LinkedIn accounts.”
- “Find my conversation with this profile and summarize the latest messages.”
- “Look up this LinkedIn post and comment with this exact text.”
- “Extract the people who reacted to this LinkedIn post.”

See the [plugin README](plugins/salestouch/README.md) for the supported capability list and manual MCP configuration.
