---
name: review-social-posts
description: Show the user's Crosspublish queue, calendar, drafts, or published posts. Use when they ask what is scheduled, planned, queued, on the calendar, saved as a draft, or whether a post went out.
---

Use the Crosspublish MCP server. Call `list_posts` right away. Pass `list=draft` for drafts, `list=published` for posts that already went out, and `list=queue` (the default) for everything with a time. Narrow with `network`, `from` and `to` when the user asks, e.g. "LinkedIn next week".

If they name a brand, client, or workspace that may not be the active set, call `list_social_sets` and `set_active_social_set` first, then list again.

An empty result means that list is empty. Say so.

Each message's `text` is the exact post as it will be published. Show it as written, each message as its own block, with status, time, copy label and accounts around it. Show each media URL as a link. Mention `issues` when the list is not empty.

Call `get_post` when they ask about one post. Take ids only from `list_posts` or `get_post`.
