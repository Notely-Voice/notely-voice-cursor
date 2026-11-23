# Notely Voice

Search and read your existing Notely Voice Pro library from Cursor: voice notes, full audio transcripts, AI-generated summaries, action items, and folders.

## What it does

- **Library overview**: total notes, starred notes, folder breakdown, and recent activity
- **Recent notes**: your latest recordings with titles, dates, folders, and summaries
- **Search**: find notes by topic, date range, or folder, with snippet previews
- **Open a note**: full transcript, summary, key takeaways, and action items
- **Folders**: list your folders with note counts
- **Account status**: your plan, account type, and total note count

The plugin is read-only. It does not record audio, transcribe new uploads, edit or delete notes, share notes, or process payments.

## Example prompts

- "Give me an overview of my voice notes and library."
- "What are my most recent voice notes?"
- "Search my voice notes for project launch discussions."
- "Open the transcript and action items for my last meeting."
- "List all my voice note folders."
- "Which Notely plan am I on?"

## Install

**From the Cursor Marketplace:** Open **Cursor Settings -> Plugins**, search for **Notely Voice**, click **Install**, then complete the Notely Voice sign-in prompt (or run `/add-plugin notely-voice` in chat).

**MCP configuration:**

```json
{
  "mcpServers": {
    "notely-voice": {
      "type": "http",
      "url": "https://mcp.notelyvoice.ai/mcp"
    }
  }
}
```

Sign-in uses OAuth 2.1 on `notelyvoice.ai`; never paste a password or token into chat. You need a Notely Voice Pro account.

## What the plugin contains and connects to

- One skill (`get-started`) that instructs Cursor how to use the Notely Voice tools safely.
- One remote MCP server (`https://mcp.notelyvoice.ai/mcp`), operated by Notely Voice Pro. It exposes six read-only tools: `get_notes_overview`, `get_recent_notes`, `search_notes`, `get_note_by_id`, `list_folders`, and `check_account_status`.

Your search queries and note requests are sent to that server, and the notes it returns are shown to the assistant to answer you. The plugin runs no local code, installs no packages, contains no credentials, and sends data nowhere else.

## Privacy, terms, and support

- Privacy policy: https://notelyvoice.ai/privacy
- Terms of service: https://notelyvoice.ai/terms
- Support: support@notelyvoice.ai

To disconnect, remove Notely Voice under **Cursor Settings -> Plugins** (or MCP settings), and revoke access from your Notely Voice account if you want existing authorization removed.

## License

This plugin wrapper is licensed under the [MIT License](LICENSE), while the hosted Notely Voice Pro service and MCP server remain governed by the [Notely Voice Terms of Service](https://notelyvoice.ai/terms).
