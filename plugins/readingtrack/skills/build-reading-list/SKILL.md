---
name: build-reading-list
description: Create or extend an ordered ReadingTrack reading list from links, saved items or notes. Use when the user asks for a reading list, study plan, curriculum or "add this to my <name> list" in ReadingTrack.
---

# Build a ReadingTrack reading list

Use the `readingtrack` MCP tools.

## New list: `create_reading_list`

- `title` is required; `description` is optional.
- Each entry in `items` has **exactly one** of `item_id` (already in the library), `url` (external link) or `content_markdown` (a new note or article).
- Keep the order the user wants to read in. A list holds up to 100 items.
- Pass an `idempotency_key` (for example, a slug of the title plus today's date) so that a retry continues instead of duplicating.
- Lists are private. These tools cannot publish a list. If the user asks for that, tell them to publish it from the ReadingTrack website.

## Existing list: `add_to_reading_list`

1. Call `get_reading_lists` to find the list. Follow `next_cursor` if it is not on the first page.
2. If more than one list matches the name, ask the user which one to use.
3. Call `add_to_reading_list` with its `list_id` and the new `items`. Items already in the list are not duplicated.

## Partial results

If the response has `partial: true`, report `completed_items` and `failed_index`. Then retry the **identical** request once. It resumes where it stopped.

Finish by giving the user the list URL from the response.
