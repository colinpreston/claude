# design-studio-team-setup

A Claude skill for Colin Preston. Sets up a "company brain + desks" pattern for a new design consultancy client engagement: one shared Project Brain, a roster of role "desks" each with a one-page brief and a memory log structured in three zones (Active Notes / Digest / Archive) so it stays usable as the engagement grows, a shared project-level research repository built the same way, a retrieval mode (RAG-style: search, then answer only from what's found and cite the source) for specific questions rather than routine work, a Delivery Manager that both reacts (status checks, stalled-handoff spotting) and proactively routes new multi-desk work (sequencing who's needed and in what order from the roster's dependency graph, before anyone starts), a visual desk-status dashboard, and a Colin send/edit/skip review gate.

Default roster: Lead UX Designer, Lead UX Researcher, Expert Workshop Facilitator, Product Consultant, Engineering Principal, QA & Definition Lead, Delivery Manager — plus whatever specialists a given engagement needs.

## Using this as a Claude skill

Drop this folder into wherever Claude loads skills from (a synced skills directory, or a plugin/marketplace repo) so it's discoverable as `design-studio-team-setup`. See `SKILL.md` for the full instructions Claude follows, and `references/` for the two document templates it fills in per engagement.

## Structure

```
design-studio-team-setup/
  SKILL.md                              — the skill itself
  references/
    project-brain-template.md           — shared engagement-level context doc
    role-brief-template.md              — per-role brief template
```
