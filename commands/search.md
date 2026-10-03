---
description: Search CognifAI ideas by title across all realms or one realm
argument-hint: <query> [realm name]
allowed-tools: mcp__plugin_cognifai_cognifai__search_ideas, mcp__plugin_cognifai_cognifai__list_realms, mcp__plugin_cognifai_cognifai__get_idea
---

Search CognifAI for: $ARGUMENTS

1. If the arguments name a realm, find it by name and pass its ID as `realmId` to `search_ideas`. Match the realm by name: call `list_realms`, then compare the name the user gave to each realm's name, ignoring case and allowing partial matches. Never ask the user for a realm ID. If exactly one realm matches, use it. If several match, list their names and ask which one. If none match, show the user their realm names and ask which they meant. If no realm is named, search all realms.
2. Present matches grouped by realm: title, type, tags, and a one-line snippet of the content.
3. Note that search matches titles only. If nothing matches, try one or two alternate phrasings before reporting no results.
4. Offer to show any match in full (fetch it with `get_idea`, but never mention tool names to the user). Suggest follow-ups the user can ask in plain words, such as "show me the full idea", or the `/cognifai:update` command to edit one.

Write replies for the user in plain language. Never mention tool names, such as `get_idea` or `list_realms`, in what you say to the user. When suggesting a next step, offer it as a plain request or as one of the `/cognifai:` commands.
