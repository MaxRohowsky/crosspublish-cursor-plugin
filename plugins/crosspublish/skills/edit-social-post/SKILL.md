---
name: edit-social-post
description: Change, add media to, move, or delete a Crosspublish post. Use when the user wants to rewrite a draft or queued post, add or remove an image or video, give one network its own text, change post options, unschedule, or delete a post.
---

Use the Crosspublish MCP server. Call `get_post` before changing a post, and take the id from `list_posts` or `get_post`. Show the user what will change and wait for confirmation.

## Text

`update_post` replaces the whole thread of one copy. Send every message to keep, copying unchanged `text` exactly, including line breaks. A message left out is deleted with its media.

When the post has more than one copy, pass `copy`: `shared` for the thread several accounts share, or a network such as `x` for that network's own copy.

To give one network different text, call `detach_copy`, then `update_post` with that copy. `merge_copy` puts a network back on the shared copy and deletes its separate text and media.

## Media

Add an image or video from the media library with `list_media` and `attach_media` (`mediaId`), or pass a public HTTPS image URL as `url`. Remove a file with `remove_media` and the file id from `get_post`, not with `update_post`.

For a file on the user's computer, call `upload_media` and run the curl command it returns, or call `request_upload_link` and give the user the link.

## Accounts and options

`add_accounts` and `remove_accounts` change which accounts a post goes to. `set_post_options` changes per-network settings such as YouTube and Pinterest titles, the Pinterest board, TikTok privacy, the Google Business button, the X community or the Threads topic. Look up boards with `list_pinterest_boards`, communities with `search_x_communities`, and TikTok privacy levels with `get_tiktok_creator_info` first.

## Timing and deleting

`unschedule_post` keeps a scheduled post at its time as planned, so it does not publish. `move_to_drafts` takes it off the calendar. `delete_post` deletes a draft, planned or scheduled post for good and always needs the user's explicit yes. Published posts cannot be edited or deleted here.
