---
name: schedule-social-post
description: Draft, schedule, or publish a social post with Crosspublish. Use when the user wants to write a post, queue it, pick a time, or send it to one or more connected social accounts.
---

Use the Crosspublish MCP server. Work in the user's active social set.

1. If the user names a brand, client, or workspace that may not be the active set, call `list_social_sets`, then `set_active_social_set` with an id from that list.
2. Call `list_posts` before creating anything. If the post already exists as a draft or planned post, use its id. Otherwise create it with `create_draft`. To send the same post to more accounts, use `add_accounts`, not a second post.
3. Resolve a relative time ("tomorrow at 9", "next Tuesday") to a concrete date and time in the user's account timezone, unless they named another. If they say "add it to the queue" or leave the time to you, use `scheduledFor: "next-free-slot"` and report the time `schedule_post` returns.
4. Show the exact text, one message per block, the accounts, and the concrete date, time and timezone. Wait for the user to confirm. The text they confirm is the text you send.
5. Call `schedule_post`. Pass `scheduledFor` as a local wall-clock time without a zone, such as `2026-03-14T09:30`. Pass `timezone` only when the user asked for one.
6. To publish right away instead, call `publish_now` without a code: it returns a preview and a confirmation code and publishes nothing. Call it again with the code only after the user approves that preview.
7. Report any `issues` the tools return. `schedule_post` refuses a post with issues. Instagram needing an image is a common one: attach a file from the media library with `attach_media`, then schedule again.

Scheduling queues the post; it is not published until its time.
