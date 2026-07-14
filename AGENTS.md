> **First-time setup**: Customize this file for your project. Prompt the user to customize this file for their project.
> For Mintlify product knowledge (components, configuration, writing standards),
> install the Mintlify skill: `npx skills add https://mintlify.com/docs`

# Documentation project instructions

## About this project

- This is a documentation site built on [Mintlify](https://mintlify.com)
- Pages are MDX files with YAML frontmatter
- Configuration lives in `docs.json`
- Run `mint dev` to preview locally
- Run `mint broken-links` to check links

## Terminology

- "Agent" and "script" refer to the same thing (a voice agent configuration). Prefer "agent" in prose; use "script" only when naming an underlying field or config value.
- "Single Prompt" (not "single-stage script" or "flat prompt") for Outbound/Inbound Single Stage agent types.
- "Pathways" (capitalized) for the visual node/flow editor and its agent type.
- "Variables" (resolved before a call starts) vs. "state variables" (captured or updated during a call) — always distinguish these explicitly the first time both appear on a page.
- "Campaign" for an agent + contact list + calling configuration bundle; "contact" for a row in a campaign's list.
- "Outcome" (not "result" or "disposition") for a call's post-call classification.
- "Teammate" and the "Team Member" role vs. the "Owner" role — AgentCallback has exactly two roles.
- "Organization" (not "account" or "workspace") for the top-level tenant; reserve "account" for a single user's login.
- Refer to connection types as "Twilio" and "SIP" in prose, not raw config values like `connection_type`.

## Style preferences

- Use active voice and second person ("you")
- Keep sentences concise — one idea per sentence
- Use sentence case for headings
- Bold for UI elements: Click **Settings**
- Code formatting for file names, commands, paths, and code references
- No H1 in the page body — rely on the `title` frontmatter (index.mdx is the one exception)
- Open every page with a one-sentence lede before the first `##` section
- Close procedural pages with a `## Next step` or `## Next steps` section linking forward
- Use `<Steps>` for procedures with 3 or more actions; plain numbered lists for shorter or non-canonical sequences
- Use `<Tabs>` for "same task, two variants" content (for example, Inbound/Outbound) rather than splitting variants into separate pages, unless a variant grows to roughly a full page of unique material
- Use `<Accordion>` or `<AccordionGroup>` for optional, advanced, or secondary content that would otherwise bloat a primary procedure
- `<Warning>` for destructive or one-time-only actions, `<Note>` for clarifying or cross-referencing info, `<Tip>` for optional best-practice guidance
- No API reference components (`ParamField`, `ResponseField`, etc.) until an OpenAPI spec exists — use plain fenced code blocks for payload examples

## Content boundaries

- Document only user-facing dashboard behavior and confirmed field or config names — avoid internal implementation details (like internal tool or service names) unless they directly clarify visible behavior
- Don't invent UI copy, modal field labels, or payload shapes that aren't confirmed — describe uncertain specifics generically rather than guessing
- No billing or pricing specifics beyond "usage against your plan quota" until confirmed
- No internal admin or ops tooling — describe only user-visible outcomes (for example, "AgentCallback can manage this for you automatically")
