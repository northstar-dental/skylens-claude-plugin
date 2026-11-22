# SkyLens by NorthStar

SkyLens by NorthStar connects a practice's Open Dental data to AI assistants like
ChatGPT or Claude, so the team can ask questions and get answers and reports without
replacing the practice management system.

SkyLens works with Open Dental only. It reads a nightly, read-only copy of your
data. Images and X-rays are not included. Open Dental Cloud is not supported.

This plugin adds five question guides and connects Claude to the SkyLens server at
`https://mcp.northstar.dental/mcp`. It contains instructions and the server address,
with no scripts, hooks, API keys or bundled server. When you use a tool, Claude
uses the connected SkyLens tools to answer your question.

## Install in Claude Code

You need Claude Code and a SkyLens account with access to your practice's data.
In a Claude Code session, run:

```text
/plugin marketplace add northstar-dental/skylens-claude-plugin
/plugin install skylens@northstar-dental
```

Restart the session to load the plugin. Open `/mcp`, select
`plugin:skylens:skylens`, and follow the sign-in prompt. Sign in to SkyLens in your
browser and review the permissions before connecting. Do not paste credentials
into a conversation or edit this plugin to add them.

For connection instructions and guidance on patient identities, see the
[Claude connection guide](https://app.northstar.dental/connectors/claude).
Read the [NorthStar privacy policy](https://northstar.dental/privacy).

## Ask a question

Claude can select a guide from your question, or you can open one by name:

| Guide | Question family |
| --- | --- |
| `/skylens:production-and-collections` | Production and collections for a period |
| `/skylens:schedule-and-huddle` | A day's schedule and team briefing |
| `/skylens:outstanding-balances` | Current balances and accounts receivable |
| `/skylens:new-patients` | New patients over a period |
| `/skylens:saved-reports` | A saved query or named report |

Include the office and dates you mean. Answers should name the offices, dates,
metric definitions and data freshness returned by SkyLens. Available tools depend
on your practice and permissions; a missing tool or hidden identity is a limit to
explain, never a reason to guess. Review results before acting on them.

## Disconnect

To stop loading this plugin's guides and server, run
`/plugin uninstall skylens@northstar-dental` and restart Claude Code.
Uninstalling the plugin does not revoke an existing SkyLens authorization. In
SkyLens, open **Settings > Assistant** and disconnect the Claude connection too.
If you connected SkyLens separately in another Claude app, disconnect it there as
well.

## License

[Apache-2.0](LICENSE).
