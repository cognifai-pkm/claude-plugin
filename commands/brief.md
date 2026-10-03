---
description: Summarize a CognifAI realm into themes, open threads, and next steps
argument-hint: <realm name>
allowed-tools: mcp__plugin_cognifai_cognifai__list_realms, mcp__plugin_cognifai_cognifai__get_realm_ideas, mcp__plugin_cognifai_cognifai__get_idea
---

Produce a briefing for the CognifAI realm: $ARGUMENTS

1. Match the realm by name: call `list_realms`, then compare the name the user gave to each realm's name, ignoring case and allowing partial matches. Never ask the user for a realm ID. If exactly one realm matches, use it. If several match, list their names and ask which one. If none match, show the user their realm names and ask which they meant. Then load its ideas with `get_realm_ideas`. If no realm name was given, show the user's realm names and ask which to brief.
2. Summarize: the main themes, the most recently updated ideas, ideas linked to many others, and open questions or half-finished ideas.
3. Keep it to one screen, citing ideas by title. Use `get_idea` only when a snippet is not enough.
4. End with 2-3 suggested next steps.

Write replies for the user in plain language. Never mention tool names, such as `get_idea` or `list_realms`, in what you say to the user. When suggesting a next step, offer it as a plain request or as one of the `/cognifai:` commands.
