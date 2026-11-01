# Crosspublish for Cursor

Draft, schedule and publish social media posts from Cursor with [Crosspublish](https://crosspublish.com).

Supports Instagram, Facebook, TikTok, LinkedIn, X, Threads, YouTube, Pinterest, Bluesky, Mastodon and Google Business Profile.

- Draft, schedule and publish posts to your connected accounts.
- Add images and videos, and tailor the text for each network.
- Review your queue and drafts, then edit or reschedule posts.
- Check account and post analytics (Pro plan).
- Read and reply to comments and messages in one inbox (Pro plan).

## What's inside

- `plugins/crosspublish/mcp.json`: the remote Crosspublish MCP server, `https://crosspublish.com/api/mcp`.
- `plugins/crosspublish/skills/`: skills for reviewing, scheduling and editing posts.

## Use it

Install the plugin, then connect the Crosspublish MCP server and sign in with your Crosspublish account (OAuth). You need at least one social account connected in Crosspublish. The Free plan works; analytics and the inbox need Pro.

Ask things like "What's in my posting queue?", "Draft a post announcing our launch and schedule it for tomorrow at 9am", or "Which posts got the most views this month?". You are asked to confirm before anything is scheduled, published, deleted or replied to.

## Data

The plugin sends your requests to your own Crosspublish account through `https://crosspublish.com/api/mcp`. Crosspublish handles that data under its [privacy policy](https://crosspublish.com/privacy) and [terms](https://crosspublish.com/terms-of-service). The plugin itself stores nothing.

Support: [crosspublish.com/help](https://crosspublish.com/help) or contact@crosspublish.com.

## License

MIT
