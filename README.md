# Matt Fuchs

I build AI agents and workflows and run them every day. Fifteen years on the business side of a $30B asset manager, finishing as the lead on its firm-wide AI rollout (production agents, governance, data access, an education program all 62 people went through). In July 2026 I left to build full time: Claude Code, MCP, evals, and the question I keep circling, what changes about how a business runs when this stuff actually works.

Most of what I build is for one user (me), so I can find out where it breaks. The code for the agents below is private because it holds real data; the job search board is public with a live demo on invented data.

## Featured: Job Search Board

A one-screen command center for a senior, network-driven job search. Every morning a routine collects postings from alert mail, a model reads each one against a rubric I keep correcting, and the survivors land on a hosted page. Verdicts, pipeline moves, people and to-dos flow back into one record that every other view is generated from.

**[Live demo](https://demo.mattfuchs.dev/job-board/)** · **[Repo and build guide](https://github.com/mfuchs22/job-search-board)**

[![The Overview tab](https://raw.githubusercontent.com/mfuchs22/job-search-board/main/screenshots/overview.png)](https://demo.mattfuchs.dev/job-board/)

The part I'd point a reviewer at is the rubric, not the code: after the first fifty-odd verdicts the point score barely discriminated above the floor, so the gates (location, travel, role shape, company trajectory) now run first and points second. The rubric is versioned, and a Monday routine proposes revisions from the week's verdicts that I accept or reject.

## What's running

Everything here runs on a schedule or sits in a channel waiting for a message. One record per system, one writer per record, a model only where reading text or making a judgment call needs one.

| System | What it does | Built with | Status |
|---|---|---|---|
| **Job search engine and board** | Collects, scores, reviews and tracks roles; the board above | Python, Supabase, Vercel, Notion, Claude Code | Public showcase, live demo |
| **Personal OS** | The repo everything else reads: who I am, what's in flight, decisions and insights logs, one agent file per vertical, a wiki of 70-odd pages on agent design | Markdown, Claude Code skills, a chief-of-staff router | Private |
| **Training coach** | Reads and writes TrainingPeaks through an MCP server, mirrors the plan to Google Calendar, coaches in Discord after every workout off a Strava webhook | Python, TrainingPeaks MCP, Discord, Claude Code | Private |
| **Media digest** | Records what I watch and listen to, fetches transcripts, hands a nightly queue to a model that writes wiki pages and a morning digest | Python, yt-dlp, Spotify API, Claude Code | Private |
| **Fantasy football agent** | Checks lineups, works the waiver wire, makes moves once approved, reports in a channel | Python, Yahoo and ESPN APIs, Telegram, Claude Code | Private |
| **Task board** | Phone and laptop view over a Notion tasks database, with an evening sweep that proposes what got done | Static page, Vercel functions, Supabase auth, Notion | Private |
| **Coursework tracker** | One page over two fall courses (AI Evals for Engineers & PMs, Product Faculty AI PM), reads and writes the Notion session record | Static page, Vercel, Notion | Private |
| **Bike garage** | Stock vs current spec, the parts bin, fit and compatibility, swaps drawn to scale on the product photo | Static page, Supabase, Claude Code | Private |
| **Home OS** | The house as a system: every component, who services it, what is due; plus a 3D property model built from public data | Python, Three.js | Private, in progress |
| **Golf caddie** | A ring-fenced iMessage agent for a group golf trip: tee times, weather, logistics, nothing else it can reach | Claude Code, iMessage, a locked-down settings file | Private |
| **Always-on channel session** | One Claude Code session that reads a Discord server and routes each channel's message to the right agent file | Claude Code, Discord | Private |

## How I work

- **Claude Code is the runtime.** Agents are markdown job descriptions plus skills; a chief-of-staff file routes plain-language requests to the right one. No framework.
- **Deterministic first.** Collection, dedupe, scheduling and mirroring are plain scripts with zero marginal cost. A model is reserved for reading text, scoring, synthesis and drafting. Every workflow is split that way on purpose.
- **Humans decide.** Verdicts, lineup moves, outreach, anything that reaches another person: the agent drafts, I approve. Feedback on every routine is logged and reviewed fortnightly to revise the prompts.
- **Evals and memory are real work.** A versioned rubric with a changelog, a feedback file per routine, a wiki of design patterns (human-in-the-loop, guardrails, completion conditions, reflection) that every new agent is checked against.
- **Infra:** a Mac mini running launchd routines, a Windows box for the always-on scrapers, Supabase for auth and tables, Vercel for pages, Notion as the record where a human needs to see it.

## Elsewhere

- Demos: [demo.mattfuchs.dev](https://demo.mattfuchs.dev)
- LinkedIn: [matt-fuchs-cfa](https://www.linkedin.com/in/matt-fuchs-cfa)
- Email: matthew.e.fuchs@gmail.com
