# ReadingTrack for Claude

This is the plugin marketplace for [ReadingTrack](https://www.readingtrack.com). It holds one plugin, `readingtrack`. The plugin connects Claude to your private ReadingTrack library. Then you can save explanations, code snippets and ordered reading lists from any conversation, and read, track and remember them later.

## Install in Claude Code

```bash
claude plugin marketplace add readingtrack/readingtrack-claude
claude plugin install readingtrack@readingtrack
```

Then run `/mcp`, select `readingtrack` and choose **Authenticate** to sign in.

On claude.ai and the Claude apps, add ReadingTrack from the connector directory, or as a custom connector with URL `https://www.readingtrack.com/api/mcp`.

## Contents

- [`plugins/readingtrack`](plugins/readingtrack): the plugin. It has a remote MCP server connection and two skills, and no executable code. Its README says what it sends and where.

Setup guide: https://www.readingtrack.com/docs/integrations/claude-code · Privacy: https://www.readingtrack.com/privacy-policy · Support: https://www.readingtrack.com/support
