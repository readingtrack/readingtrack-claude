---
name: save-to-readingtrack
description: Save an explanation, article, notes or code snippet from the conversation to the user's private ReadingTrack library. Use when the user says "save this to ReadingTrack", "save this for later", "keep this snippet", or asks to store something to read or revisit.
---

# Save to ReadingTrack

Use the `readingtrack` MCP tools to store content the user chose.

## Choosing the tool

- **`save_article`** — a complete explanation, guide or write-up. Requires `title` and `content_markdown`.
- **`save_snippet`** — a short excerpt, a code block, a command or a single note. `title` is optional.

## Rules

1. Save only content the user supplied or explicitly asked to save. Never invent, summarize or pad it unless the user asks for a summary to be saved.
2. Preserve the Markdown exactly: code fences with language tags, tables, links and Unicode.
3. Give articles a short, specific title (under 120 characters) that the user will recognise in their library later.
4. If the user says "save this" ambiguously, save the most recent substantial answer and say which one you saved.
5. After saving, reply with the returned reader URL so the user can open it.
6. Content is private. Do not tell the user it is published or shared.

## Failures

- Authentication errors: ask the user to reconnect ReadingTrack (in Claude Code, run `/mcp` and authenticate `readingtrack`).
- Size errors: the library accepts about 250 KB of Markdown per item. Offer to split the content into parts.
- On a transient error, retry the identical call once. Identical content does not create duplicates.
