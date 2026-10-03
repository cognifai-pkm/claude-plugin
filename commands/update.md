---
description: Edit the title, content, or tags of an existing CognifAI idea
argument-hint: <idea title or ID> <what to change>
allowed-tools: mcp__plugin_cognifai_cognifai__update_idea, mcp__plugin_cognifai_cognifai__search_ideas, mcp__plugin_cognifai_cognifai__get_idea, mcp__plugin_cognifai_cognifai__list_realms
---

Update a CognifAI idea: $ARGUMENTS

1. Locate the idea by title with `search_ideas`, resolving any realm by name. Match the realm by name: call `list_realms`, then compare the name the user gave to each realm's name, ignoring case and allowing partial matches. Never ask the user for a realm ID. If exactly one realm matches, use it. If several match, list their names and ask which one. If none match, show the user their realm names and ask which they meant. Never ask the user for an idea ID. If several ideas match, list their titles and ask which one.
2. Read it with `get_idea` so edits build on the current content.
3. Show the user the proposed change (old vs. new) and wait for confirmation, because `update_idea` overwrites `title`, `content`, and the whole `tags` list.
4. Call `update_idea` with only the changed fields. If the idea is immutable or the user is a viewer, explain that and stop.

Write replies for the user in plain language. Never mention tool names, such as `get_idea` or `list_realms`, in what you say to the user. When suggesting a next step, offer it as a plain request or as one of the `/cognifai:` commands.
