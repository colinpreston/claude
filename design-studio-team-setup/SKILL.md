---
name: design-studio-team-setup
description: "Use when Colin wants to set up the \"company brain + desks\" team, desks, or dashboard for a new design client project, spin up a project, or onboard a new client."
---

# Design Studio — Team Setup

This sets up a "company brain + desks" anatomy for a design consultancy engagement: one shared "company brain" holding the client and project context, a roster of "desks" (roles), each with its own one-page brief and a memory log, a shared project-level research repository, a visual dashboard of the whole roster, and a review step that's just Colin typing send / edit / skip.

**Be upfront about how this actually works.** There is no standing swarm of agents running in the background chatting with each other live. Each "desk" is Claude taking on a specific role inside a session — sometimes the same conversation, sometimes a fresh one weeks later. What makes it feel like a team is that every desk reads and writes to the same shared docs: a role picks up where the last session left off by reading its own memory log and the logs of the roles it depends on, and the Delivery Manager's whole job is reading everyone's latest notes and turning gaps into an action list. That's the mechanism — plain persistence and cross-referencing, not real-time multi-agent chat. Say this plainly if Colin asks how it "talks to itself."

## Step 0 — Confirm you're in the right home

Each client engagement needs its own isolated company brain — reusing a project/workspace that already belongs to a different client mixes up two clients' confidential context in one place. Before onboarding, check what this session is actually attached to (a Claude.ai Project, a Cowork project, or nothing yet). If it's attached to something that clearly belongs to a different client, stop and ask him to open this in a fresh project for the new client first, rather than writing the new engagement's docs somewhere they don't belong. If nothing is attached yet, say so and proceed with local files, flagging that he should create/attach a project for this client when he can, so the docs persist and show up across his other Claude sessions.

## Step 1 — Interview Colin

Don't dump every question at once — ask, let him answer, capture it, then move to the next. He may have already given some of this; don't re-ask what he's already told you.

1. **Client details** — client name, industry/sector, and anything useful about key stakeholders (names, roles, who's the primary contact).
2. **The brief** — the problem or opportunity, objectives, what's explicitly in and out of scope, constraints (budget, timeline, technical or brand constraints), how success will be judged, and any key dates or milestones already fixed.
3. **Team** — confirm the default roster below applies, and ask whether this project needs any specialists beyond it. Offer a few common examples as inspiration rather than a fixed menu — Content/UX Writer, Service Designer, Visual/Brand Designer, Data & Insight Analyst, Accessibility Specialist, Prototyping/Motion Specialist, Business Analyst — but the real question is what *this* engagement actually needs, not ticking boxes off a list.

## Step 2 — The roster

Every project gets this default team, no exceptions:

| Role | One-liner |
|---|---|
| Lead UX Designer | Owns the design direction — flows, wireframes, prototypes, design decisions |
| Lead UX Researcher | Plans and runs research, turns findings into insight the rest of the team can act on |
| Expert Workshop Facilitator | Designs and runs collaborative sessions (kickoffs, co-design, ideation, alignment) |
| Product Consultant | Keeps the work tied to product strategy and business value, not just craft |
| Engineering Principal | Represents technical feasibility and delivery reality — sense-checks ideas against what's actually buildable |
| QA & Definition Lead | Turns approved design into engineering-ready definition — user stories, acceptance criteria — and checks delivered work against it before anything ships |
| Delivery Manager | Coordinates the other desks, tracks what's moving and what's stuck, turns that into action (see Step 6 — not optional) |

Plus whichever specialists came out of Step 1, each written up the same way as the default roles.

The QA & Definition Lead sits at the design-to-engineering handoff on both sides of it: forward, it turns the Lead UX Designer's approved flows and the Content/UX Writer's copy into user stories and acceptance criteria the Engineering Principal and any actual dev team can build against; backward, once something is built, it checks the result against that same definition before Colin signs off on it shipping. Don't let this role drift into pure bug-hunting — the definition half (writing testable, buildable requirements from a design) is just as much its job as the checking half.

**The Boss** is Colin — Product & Service Design Director. He sits above the roster: plans the program of work, decides priorities and phasing, and gives the final send/edit/skip on anything a desk proposes. No desk commits budget, timeline, or anything client-facing without his say — see Step 8.

## Step 3 — Write the Project Brain

One doc for the whole engagement, following `references/project-brain-template.md`. Name it after the client, e.g. `<ClientName>_Project_Brain.md`. It holds the client details, the brief, the roster table (Step 2, plus any specialists), the fences (Step 8), a link to the desk dashboard (Step 7) once published, a pointer to the research repository (Step 5), a skill-sources note (see Step 4's skills bullet) listing anything recommended, whether Colin installed it or is still meaning to, and a "how to use this" section.

If this session has a Projects tool attached, write it there with `project_write` so it's visible across Colin's other sessions. Otherwise write it as a local file and tell him where, and that it should move into a proper project once one exists for this client.

## Step 4 — Write each role's brief

For every role in the roster — defaults and specialists alike — write a brief following `references/role-brief-template.md`. Each brief needs:

- **Instructions** — imperative, concrete: what this role actually does day to day on this engagement, not a generic job description.
- **Context** — which parts of the Project Brain it actually needs (not all of it necessarily matters to every role), plus the research repository (Step 5) as standing context for every role, not just the ones with a direct dependency on the Researcher.
- **Collaborates with** — which other roles' output it should read before it acts, and whose work depends on its own. This is the literal mechanism for "talking to each other": before the Lead UX Designer starts wireframing, it reads the Lead UX Researcher's latest findings log; before the Facilitator plans a workshop, it checks what the Delivery Manager flagged as open; before the QA & Definition Lead writes user stories, it reads the Lead UX Designer's approved flows and the Content/UX Writer's copy, and its own output in turn feeds the Engineering Principal. Name the actual roles and the actual direction of the dependency, don't just say "collaborates with everyone."
- **Skills to check automatically** — look at Claude's currently *installed* skills (design, marketing, data, product, and any others listed in this session) and name the ones that genuinely match this role's day job — e.g. a Lead UX Researcher's brief points to a user-research and a research-synthesis skill if the library has them; a Content/UX Writer's brief points to a UX-copy or copy-editing skill; a Data & Insight Analyst's brief points to data-analysis and visualization skills; a QA & Definition Lead's brief points to a product-requirements skill for the definition half and a design-handoff or accessibility-review skill for the checking half. The instruction to the role is to check and invoke these automatically when doing matching work, without waiting for Colin to name the skill — the same way a real specialist would just reach for their usual toolkit.

  If nothing *installed* genuinely fits a role, don't stop at "no skill exists" — check the known external skill catalogs below before falling back to `skill-creator`, since between them they cover most of a design studio's gaps:
  - **Owl-Listener/inclusive-design-skills** (`https://github.com/Owl-Listener/inclusive-design-skills`) — accessibility & inclusive design: accessibility decision-making and trade-offs, accessible content, adaptive interfaces, cognitive accessibility, inclusive interaction patterns, inclusive personas. Several of its categories include a dedicated `review` or `audit` skill (e.g. accessible-content/review, inclusive-interaction/audit) — a strong fit for a QA & Definition Lead's checking half, and for an Engineering Principal, an Accessibility Specialist, or a Lead UX Designer doing an accessibility pass.
  - **Owl-Listener/designer-skills** (`https://github.com/Owl-Listener/designer-skills`) — a broad general design toolkit: design ops (critique, QA, handoff, sprint planning), design research (interviews, journey maps, JTBD, usability testing), design systems, interaction design (including named UX laws — Fitts's, Hick's, Jakob's, etc.), prototyping & testing, UI design, UX strategy (IA, opportunity framing, stakeholder alignment), and visual critique. Its design-ops category (`design-qa-checklist`, `handoff-spec`, `design-review-process`) is close to a direct match for a QA & Definition Lead on both halves of the role. Useful across almost every design-side role, including filling gaps for Delivery Manager (design-ops workflow skills) and Visual/Brand Designer (visual-critique, ui-design).
  - **jamiemill/layers-skills** (`https://github.com/jamiemill/layers-skills`) — the "Layers" method: product strategy, conceptual modelling, domain modelling, interaction flow, observed behaviour, user needs. A strong fit specifically for a Product Consultant or Lead UX Researcher, especially early on when objectives or scope need prioritising against real user/business need rather than instinct.
  - **coreyhaines31/marketingskills** — a large marketing library (SEO, CRO, copy, paid/measurement, growth & retention, sales/GTM, strategy). Check for overlap with this session's already-installed `anthropic-skills:*` marketing skills first — much of it may already be covered — before recommending Colin add it.

  These are plain skill repositories (the Agent Skills spec, agentskills.io) — Claude can identify which one would help a given role, but can't install it into Colin's account from inside a session.

  **Once the full roster's gaps are known, ask Colin — don't just log recommendations silently.** After writing every role's brief and compiling the complete list of "recommended, not yet installed" skills across the whole roster, stop and ask Colin (with `AskUserQuestion` when it's available, one question per repo or one combined question if the list is short) whether he wants to install any of them before setup finishes. List the specific repo(s) and which role(s) each would help.

  **For every repo Colin says yes to, guide him through the install right then — every single setup, not just when he asks.** Claude can't run the install itself from inside a session, so don't stop at printing a bare command and moving on — walk him through it like you're standing next to him. Two routes exist; give the in-app one first, since it's the one that's actually worked for Colin (no terminal needed) — fall back to the CLI only if the in-app add fails:

  1. **In-app marketplace add (first choice):** In the Claude app, go to **Customise → Plugins tab → the black "Add" button → Marketplace**, then paste the GitHub repo link (e.g. `https://github.com/Owl-Listener/designer-skills`) into the repo field and confirm. Repeat once per repo — each is added as its own marketplace/plugin. Success looks like the repo appearing in the Plugins tab in-app; take Colin's word for what he sees there over a same-session tool check, since a newly-added marketplace may not show up in Claude's own plugin-listing tool until the session's view of the catalog refreshes — don't treat a miss there as proof it failed.
  2. **CLI fallback (only if the in-app add fails)** — e.g. the repo isn't packaged with a marketplace manifest: open a terminal on the machine where he manages his Claude skills and run `npx skills add <owner>/<repo>`. If that also fails, capture the exact error text before troubleshooting further — don't guess at fixes blind.
  3. Ask him to confirm once it's done (or say he'll do it later) before you finish the setup — don't silently assume it happened.
  4. Once he confirms, update the Project Brain's skill-sources note and the affected role brief(s)' "Tools / references" to reference the newly installed skill directly, in the same setup rather than leaving it as a dangling "flagged" note. Note in the Brain which route worked (in-app marketplace add vs. CLI) so a future setup doesn't have to rediscover it.

  If he says install later or skip, don't push — just record that plainly (see below) and move on; offer to walk him through it whenever he's ready in a future session.

  Whatever he says — install now (and confirms), later, or skip — record the answer in the Project Brain's skill-sources section so a future session doesn't ask again about the same repo unless something's changed (new role added, or Colin says he's changed his mind). Do this once per setup, batched across every gap found — not once per role as each brief gets written.

  Re-check this whole step each time a role is added or the available/installed skills change, and repeat the ask (and the guided install, if he wants it) for any new gap that turns up.
- **Memory** — its own dedicated log doc, e.g. `<ClientName>_<RoleName>_Log.md`, appended to (never overwritten) every time the role is used: what it was given, what it produced, what's still open. This is what lets a role "remember" past sessions and lets other roles read its history. For any role whose work involves collecting research or data (most obviously the Lead UX Researcher and a Data & Insight Analyst, but any role can end up gathering input — a Facilitator running a workshop, a Product Consultant interviewing stakeholders), this own log is where the full detail of what was done lives — the synthesized headline findings ALSO go into the shared research repository, see Step 5.
- **Handoff** — what this role can draft and run with on its own, and what needs Colin's send/edit/skip before it moves (tie back to Step 8's fences). For the QA & Definition Lead specifically: drafting user stories and running QA checks is internal work; anything that blocks a ship decision, or any finding communicated to the client's own engineers or to the client as a hard requirement, needs Colin's send.

## Step 5 — Project-level research memory

Research and data findings are too valuable to sit locked in one role's private log, only reachable by whichever roles happen to have an explicit "reads from" arrow to it. Set up one more shared doc, `<ClientName>_Research_Repository.md`, at the same project level as the Project Brain (write it with `project_write` if a Projects tool is attached, same as the Brain). Create it empty (or with a short "no research run yet" placeholder) as part of initial setup, alongside the Project Brain and role briefs — don't wait for the first study to exist before it exists.

Whenever ANY role collects research or data as part of its work — interviews, usability tests, surveys, analytics pulls, SEO/search data, workshop outputs, stakeholder input, anything that counts as an input gathered rather than an opinion formed — it appends a synthesized entry to this repository, in addition to (never instead of) logging the full detail in its own role log. Keep each entry short: what was collected, the headline finding or number, the date, which role produced it, and a pointer to that role's own log for the full detail. Append-only, like every other memory doc here — never overwritten, most recent first or last, pick one and stay consistent.

This repository is standing context for every desk, not just the ones with an explicit collaboration arrow to the Researcher or Analyst — add it to every role's "Context needed" in Step 4, and to Step 3's Project Brain description as a linked doc. A role about to start work checks this repository the same way it checks the Project Brain: routinely, not only when its own brief happens to name a specific dependency. This is what makes a finding from, say, a Data & Insight Analyst's traffic analysis available to the Content/UX Writer even though nothing in the Writer's brief names the Analyst directly.

## Step 6 — The Delivery Manager is not just another desk

Every other role produces work. The Delivery Manager's job is different: whenever Colin asks for a status check — "what needs doing," "where are we," "give me the team update" — it reads every other role's latest memory-log entry (and the research repository from Step 5, to catch anything logged there that hasn't yet been picked up by the roles it's relevant to), spots where something is stuck (Role A produced something Role B hasn't picked up, a decision is sitting on Colin's desk, two roles are quietly blocked on the same open question), and turns that into a short, prioritised action list. It never invents work or makes a call on Colin's behalf — it only surfaces what's already logged elsewhere and says who or what it's waiting on. When Colin asks for a status check and a desk dashboard already exists (Step 7), the Delivery Manager also refreshes and republishes it so the visual and the written action list agree. This keeps the whole roster's status visible without needing a status meeting, adapted for a design engagement's pace (workshops, research cycles, deliverable deadlines).

## Step 7 — Build the desk dashboard

Once the Project Brain and every role's brief exist, publish a visual dashboard of the whole roster as a Claude Artifact (or the nearest equivalent persistence flow if the Artifact tool isn't available in the session — see the artifact-design and persisted-artifacts guidance for how to pick between them). This is a standard part of every setup, not an optional extra. Load the `artifact-design` skill before writing it.

Treat it as a real UI, not a document: it's scanned and operated, not read top to bottom. At minimum it should show, per desk: the role name and one-liner, its current status (not started / in progress / blocked / standing by — read honestly off whether its memory log has entries and what it says, never invented), what it's waiting on or doing next if that's known, and who it reads from / feeds into. Above the grid, surface the shared picture at a glance: how many desks are staffed, how many logs have been opened, how many entries the research repository holds, and the single biggest open blocker if the brief has one (most new engagements start with scope, stakeholders, or priority unconfirmed — say so plainly rather than papering over it with placeholder-looking "green" statuses). Include the fences (Step 8) as a visible panel, not buried in a linked doc. Ground the visual design in the client's actual world where it fits naturally — their industry, materials, or vernacular — rather than a generic template dashboard; this is a chance to make the artifact feel specific to the client, not just functional.

This dashboard is a snapshot, not a live feed — say so on the page itself. It gets refreshed by republishing (same file path or `url`, so the link stays stable), most naturally as part of a Delivery Manager status check (Step 6). Record the published URL in the Project Brain (Step 3) so any future session can find it.

## Step 8 — Fences

Always Colin's explicit send, whichever desk it comes from:
- Anything sent to the client (a deliverable going out, an email, a workshop invite)
- Anything committing budget, scope, or timeline beyond what's already agreed in the brief
- Any change to what the brief itself says
- Anything that speaks for the client publicly or externally

Everything else — drafting, research, synthesis, workshop planning, prototyping, internal analysis — can run ahead on its own and comes back to Colin as send (do it), edit (here's what's off), or skip (drop it).

## Step 9 — Using it day to day, once set up

Name a role directly ("as the Lead UX Researcher, draft the discussion guide for the stakeholder interviews") or just describe the job ("we need to plan the kickoff workshop") — Claude reads the Project Brain plus the matching role's brief to pick it up, checks the research repository (Step 5) for anything already known before starting new work, and checks that role's "skills to check automatically" list — installed and recommended-external alike — before treating the job as generic work. Any role that collects research or data along the way appends a synthesized entry to the repository before finishing, not just to its own log. Ask the Delivery Manager for a status check any time — this both gives Colin the action list and refreshes the desk dashboard. If a new specialist turns out to be needed partway through the engagement, run Step 1's team question again for just that role and add its brief (with its own matched skills and the research repository as standing context) and a row on the dashboard the same way — the roster isn't fixed once written.
