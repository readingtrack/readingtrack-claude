# ReadingTrack for Claude

![ReadingTrack](assets/logo.png)

Save explanations, code snippets and ordered reading lists from Claude to your private [ReadingTrack](https://www.readingtrack.com) library. Then read, track and remember them on the web, in the browser extension or on mobile.

## What's included

- **MCP server** `readingtrack` (remote, OAuth) with tools `save_article`, `save_snippet`, `create_reading_list`, `add_to_reading_list` and `get_reading_lists`.
- **Skills**: `save-to-readingtrack` and `build-reading-list`, which tell Claude when and how to use those tools safely.

## Install (Claude Code)

```bash
claude plugin marketplace add readingtrack/readingtrack-claude
claude plugin install readingtrack@readingtrack
```

Then run `/mcp`, select `readingtrack` and choose **Authenticate**. A browser opens so you can sign in to ReadingTrack with Google or GitHub and approve access.

You'll need a free ReadingTrack account. If you don't have one, it's created the first time you sign in.

## Use

- "Save this explanation to ReadingTrack."
- "Save that code block as a ReadingTrack snippet."
- "Make a ReadingTrack reading list for learning Rust from these links: …"
- "Add this article to my *Distributed Systems* list."

## What the plugin sends

The plugin contains no code. It points Claude at one remote server, `https://www.readingtrack.com/api/mcp`, which is operated by ReadingTrack. When you ask Claude to save something, Claude sends that Markdown, its title, any tags, and any links you included to that server. Claude reads your list names and IDs only when it needs to pick a list. Links in a reading list are fetched later by ReadingTrack, which reads the page title and text so you can read them in the app. Nothing is sent anywhere else.

## Privacy

Only content you ask Claude to save is sent. Everything is private to your account, and these tools never publish it. You can revoke access at any time in ReadingTrack → Settings → Connected assistants. Privacy policy: https://www.readingtrack.com/privacy-policy · Support: https://www.readingtrack.com/support
