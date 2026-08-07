# Changelog

## 0.6.0 - 2026-08-07

- Add durable `scheduled_for` support to LinkedIn messages, invitations,
  invite-then-message workflows, likes, comments, and publications.
- Reconnect sleeping credential-based LinkedIn accounts when scheduled actions
  become due while keeping manual reconnect failures visible.
- Promote long-term scheduled actions into the Inngest execution horizon and
  prioritize explicit schedules over automatically queued work.

## 0.5.10 - 2026-07-30

- Align MCP safety annotations with actual behavior: LinkedIn and scrape reads
  are open-world, additive outreach actions are non-destructive, and only queue
  cancellation is destructive.

## 0.5.9 - 2026-07-30

- Publish the `status.include` input as one canonical array shape so ChatGPT
  can call multi-section status requests without an ambiguous union.

## 0.5.8 - 2026-07-30

- Position SalesTouch as an AI-native GTM prospecting platform across MCP and
  marketplace metadata.
- Prepare the OpenAI submission under Business & Operations with an accurate
  standalone-product and third-party integration disclosure.

## 0.5.7 - 2026-07-30

- Add the OpenAI MCP plugin submission pack, reviewer fixtures, and portal test cases.
- Align open-world safety annotations with external write behavior.
- Synchronize the hosted server and every public distribution version surface.

## 0.5.6 - 2026-07-30

- Add the Claude Connectors Directory and community plugin marketplace submission pack.
- Expand reviewer guidance across all 26 MCP tools with dedicated test-workspace safeguards.
- Link the public submission and compliance material from both plugin READMEs.

## 0.5.5 - 2026-07-30

- Keep public listing descriptions focused on SalesTouch capabilities and prospecting value.

## 0.5.4 - 2026-07-30

- Rewrite public descriptions around the prospecting outcomes SalesTouch delivers for AI agents.

## 0.5.3 - 2026-07-30

- Remove the unpublished development-only package from the public marketplace repository.
- Add the LinkedIn independence disclaimer to every public directory manifest.

## 0.5.2 - 2026-07-30

- Publish the canonical SalesTouch server identity, icons, strict tool schemas, annotations, structured outputs, and normalized errors.
- Add MCP Registry, Cursor, Smithery discovery, and OpenAI verification metadata.
- Add public setup, workflow, troubleshooting, support, security, review, and MIT distribution documentation.

## 0.5.1 - 2026-04-23

- Add the `routine_start` / `routine_next` / `routine_complete` MCP tools so Claude can open a daily prospecting routine with a stats dashboard (daily goal, XP, level, streak), iterate leads one at a time through phase 1 (replies awaiting) then phase 2 (prospection, score > 50: send draft → first message → invite → enrich), and wrap up with XP, achievements, and a recap.
- Persist routine sessions through the new `ProspectRoutineRun` table so a user can resume a day's routine across conversations, with deduplicated lead serving, anti-replay guards on progress and completion rewards, combo tracking, and daily-goal overflow bonuses.
- Extract the `routine-prospection` gamification playbook into a shared `ROUTINE_PLAYBOOK_PROMPT`, and refresh the embedded lead-search / draft-review UIs with locale-aware copy plus smoother partial-tool updates.

## 0.5.0 - 2026-04-23

- Ship the new lead-centric prospecting workflow with `lead.prospect`, `lead.prospect.review`, `lead.prospect.send`, and `lead.prospect.cancel`, plus direct message send helpers for faster Claude-driven outreach.
- Add rich MCP Apps review surfaces for lead search and prospect drafts, including CRM-style profile context, conversation timelines, inline/fullscreen layouts, and keyboard-driven review actions inside Claude.
- Refresh the published MCP docs, prompts, and plugin manifests around the new in-chat review flow and the expanded prospecting tool surface.
- Streamline the marketplace bundle to match the current published runtime surface and remove the old mirrored skill payloads from the shipped plugin package.

## 0.4.8 - 2026-04-15

- Update routine-prospection skill to use default action sort instead of explicit score_order, surfacing leads by next action needed.
- Document the two lead sort strategies (action vs field) in the salestouch skill reference.

## 0.4.7 - 2026-04-13

- Add the `lead.lexical.extract` MCP tool and the new `rebuild-global-lexical-scoring` skill so Claude can rebuild lexical scoring from the existing lead base in one pass.
- Add the `lead.rescore` MCP tool to preview or trigger organization-wide and targeted lead rescoring from the published runtime surface.
- Allow global lexical review saves with `apply_globally=true` so reviewed headline patterns can be stored without binding them to a specific import or offer.
- Refresh the published prospecting and scoring docs around the new global scoring rebuild workflow.

## 0.4.6 - 2026-04-13

- Tighten published MCP OAuth metadata around the actual SalesTouch permission scopes and clarify the consent labels for SalesTouch, messaging, and LinkedIn access.
- Fix public API thread resource permissions so draft thread access maps to the right published capability.
- Add editable ideal and acceptable company-size targeting fields to offer positioning so offer scoring settings can be updated directly in the app.

## 0.4.5 - 2026-04-12

- Add mission start timing to the `create-mission` skill: check running missions and let the user choose between starting now or saving for later.
- Fix mission-save reference payload format and linkedin-message-writer skill metadata alignment.

## 0.4.4 - 2026-04-11

- Expand the `create-mission` skill into a full guided flow that picks one source strategy, validates the source, saves the mission, and launches the first import.
- Tighten the LinkedIn scrape import skill so every import resolves an existing mission first and delegates back to mission creation when no good fit exists.
- Refresh onboarding around explicit user confirmations, a LinkedIn connection check before mission setup, and a mission step that includes the first lead import.

## 0.4.3 - 2026-04-10

- Align the `create-offer` reference payload with the snake_case `offer.save` MCP schema so plugin examples match the actual command contract.
- Expand the LinkedIn scrape import skill with all supported source URL types, clearer examples, and the required date inputs for company page viewers.

## 0.4.2 - 2026-04-10

- Add a new `onboarding` skill that guides first-time users from company setup to their first sent LinkedIn message.
- Refresh the `routine-prospection` skill around a tighter one-lead-at-a-time cadence with clearer session progress and milestone messaging.
- Simplify the gamification guide so onboarding and daily prospecting share a more focused achievement and combo system.

## 0.4.1 - 2026-04-10

- Add a `create-offer` skill that researches company context and builds exhaustive `offer.save` payloads.
- Add a `create-mission` skill with reproducible mission briefs organized around description, job to be done, instructions, and sources.
- Expose clearer mission MCP aliases and route existing prospecting skills toward the new mission and offer creation flows.

## 0.4.0 - 2026-04-10

- Add the new LinkedIn scrape import skill with clearer source inference from supported Sales Navigator and LinkedIn URLs.
- Ship a full prospecting routine skill that runs lead selection, enrichment, draft review, and send flows from SalesTouch MCP.
- Make draft workflows lead-centric so save, send, and cancel actions resolve the active draft from the lead instead of exposing internal draft ids.
- Expose active lead drafts in `lead.search` context responses to support review and follow-up sessions directly from Claude.

## 0.3.0 - 2026-04-10

- Ship the new lead scoring model with import provenance, lexical fit, completeness, activity, company size targeting, and optional deep scoring support.
- Add offer-specific lexical review flows so imports can return headline samples and save new weighted expressions through `scrape.review.save`.
- Expose import scoring inputs plus lead deep score and offer company size settings across the published MCP command surface.
- Retire the legacy public scoring command in favor of the import-driven review workflow and the unified scoring engine.

## 0.2.0 - 2026-04-10

- Consolidate the Claude-facing MCP surface around compound lead, scrape, LinkedIn, mission, and offer tools so common workflows require fewer calls.
- Remove legacy public REST endpoints, MCP resources, and deprecated runtime pages from the published plugin surface.
- Tighten OAuth scope metadata, public permission mapping, and premium gating for the new MCP aliases.
- Align the bundled plugin layout and docs with the `output-styles` path and the streamlined marketplace manifest.

## 0.1.16 - 2026-04-09

- Align the protected resource metadata with the full SalesTouch OAuth scope set so Claude requests the right scopes during plugin authorization.
- Add explicit consent labels for agent, import, LinkedIn, scoring, and email scopes in the plugin auth flow.

## 0.1.15 - 2026-04-09

- Request the full SalesTouch scope set during the initial Claude OAuth authorization flow.
- Return proper MCP auth challenges when a tool call is missing required scopes so Claude can re-authorize cleanly.
- Publish the plugin manifest with explicit command, agent, skill, hook, MCP, and output-style paths.
- Add placeholder `agents/`, `scripts/`, and `styles/` plugin directories for a more stable bundle layout.

## 0.1.13 - 2026-04-09

- Release the SalesTouch Claude marketplace plugin.

## 0.1.12 - 2026-04-08

- Release the SalesTouch Claude marketplace plugin.

## 0.1.11 - 2026-04-08

- Release the SalesTouch Claude marketplace plugin.

## 0.1.10 - 2026-04-08

- Pin the bundled MCP config to the canonical OAuth metadata endpoint for more reliable Claude connection setup.

## 0.1.9 - 2026-04-08

- Release the SalesTouch Claude marketplace plugin.

## 0.1.0

- Added the initial SalesTouch Claude plugin scaffold.
- Mirrored routine-agent skills into the plugin bundle.
- Added MCP catalog and resource scaffold aligned with the current routine command surface.
