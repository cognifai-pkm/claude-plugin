---
description: Save a new idea to a CognifAI realm
argument-hint: <idea text or title> [realm name]
allowed-tools: mcp__plugin_cognifai_cognifai__create_idea, mcp__plugin_cognifai_cognifai__list_realms
---

Capture this in CognifAI: $ARGUMENTS

1. Choose the target realm. Match the realm by name: call `list_realms`, then compare the name the user gave to each realm's name, ignoring case and allowing partial matches. Never ask the user for a realm ID. If exactly one realm matches, use it. If several match, list their names and ask which one. If none match, show the user their realm names and ask which they meant. If no realm was named and several are plausible, show the realm names and ask which one. Never pick a realm where the user's role is `viewer`.
2. Draft a concise title and markdown content from the input. Do not invent facts that were not provided. Pick the `type` (`generic`, `url`, `person`, `event`, `organization`) that fits and add a few short lowercase tags.
3. Call `create_idea`.
4. Confirm with the title, realm name, and tags.

Write replies for the user in plain language. Never mention tool names, such as `get_idea` or `list_realms`, in what you say to the user. When suggesting a next step, offer it as a plain request or as one of the `/cognifai:` commands.
