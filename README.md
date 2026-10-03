# CognifAI plugin for Claude

Connect Claude to your [CognifAI](https://cognifai.app) knowledge base. Search, capture, and update ideas without leaving your AI workflow.

## Requirements

- A CognifAI **Pro or Pro+** account (the MCP server is not available on the free tier).

## Install

```
/plugin marketplace add <path-or-repo-of-this-plugin>
/plugin install cognifai@cognifai
```

On first use, Claude opens a browser window to sign in to CognifAI and approve access (OAuth 2.0 with PKCE). Run `/mcp` to check connection status or re-authenticate.

## Commands

| Command | What it does |
| --- | --- |
| `/cognifai:realms` | List your realms and your role in each |
| `/cognifai:search <query> [realm]` | Search ideas by title |
| `/cognifai:capture <text> [realm]` | Save a new idea |
| `/cognifai:update <idea> <change>` | Edit an idea's title, content, or tags (asks to confirm first) |
| `/cognifai:brief <realm>` | Summarize a realm into themes and next steps |

## MCP tools provided

`list_realms`, `get_realm_ideas`, `get_idea`, `search_ideas`, `create_idea`, `update_idea`

## Privacy and permissions

The plugin accesses only realms your CognifAI account can access, and creating or updating ideas requires the editor role or above. Authentication tokens are managed by Claude and never stored in this plugin.

## Privacy

This plugin contains no code that runs on your machine. It only configures a connection to the CognifAI MCP server at `https://cognifai.app/api/mcp`. Content you ask Claude to read from or write to your realms is exchanged with that server and handled under the CognifAI privacy policy: https://cognifai.app/privacy. The plugin sends no data to any other destination.

## License

MIT. See [LICENSE](LICENSE).

## Support

Contact cognifaiapp.pkm@gmail.com or see https://cognifai.app/mcp.
