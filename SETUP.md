# Set up SalesTouch

SalesTouch is an AI-native GTM prospecting platform. It helps agents research
and qualify prospects, build audiences, start conversations, manage follow-ups,
and execute controlled LinkedIn outreach.

SalesTouch is not affiliated with, endorsed by, or sponsored by LinkedIn.

## Requirements

- A SalesTouch workspace with an active plan.
- A LinkedIn account connected inside SalesTouch.
- An MCP client that supports Streamable HTTP and OAuth.

## Endpoint

```text
https://www.salestouch.io/api/mcp
```

Name the connection `salestouch`. The browser will open SalesTouch for OAuth
authorization. The AI client never receives the LinkedIn password or
authentication secrets.

## Verify the connection

Start with a read-only request:

> List the LinkedIn accounts connected to my SalesTouch workspace.

The client should call `linkedin_accounts` and return at least one connected
account. No LinkedIn action is performed by this verification.

## Safe first workflows

1. Look up a profile and summarize its public professional information.
2. Read an existing conversation and draft a reply without sending it.
3. Inspect a post and prepare a comment for approval.

Sending, inviting, commenting, liking, publishing, and cancelling queued
actions modify external state. Review the exact target and content before
approving those calls.
