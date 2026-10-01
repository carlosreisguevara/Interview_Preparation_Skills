---
name: case-builder
description: Builds a complete, self-contained case-interview exercise for AI Deployment Strategist / Forward Deployed Engineer style interviews (e.g. Wonderful, Nubank, or similar enterprise-AI companies) in one pass, producing a single exportable document with the case story, data reveals, stakeholder pressure questions, ideal answer paths, and a feedback checklist. Use this whenever the user asks to build, create, draft, or generate a new practice case or mock case for this kind of interview — including requests naming a specific company ("build me a Nubank case"), an industry ("a telecom customer service AI case"), or an analytical archetype ("give me a churn case", "something on build vs buy"). This skill only builds the case. It does not run a live interview and does not grade a finished one — those are separate skills (case-interviewer, case-feedback) that read the file this one produces.
---

# Case Builder

## What this is for

This is one of three skills that work together but stay deliberately separate: **case-builder** (this one) creates a case in full, upfront, in a single pass. **case-interviewer** later reads that finished case and runs a live Socratic session. **case-feedback** later reads the case plus a transcript and gives improvement-focused feedback. This skill should never try to do the other two jobs — no live back-and-forth, no scoring a performance. Its only output is a complete, ready-to-run case file.

The person using this is preparing for real interviews (e.g. at Nubank) for a role that blends technical judgment, stakeholder navigation, and business reasoning around deploying AI in enterprises — not a classic market-sizing consulting case. Keep that lens throughout: math exists only to redirect a hypothesis toward the case's real question, never as the centerpiece.

## Before starting: check for duplicates

If the user has attached a prior case file, an index of past cases, or mentions cases they've already done, skim it before writing anything new. Avoid repeating the same company + archetype combination, and avoid reusing the same curveball or stakeholder question verbatim. If nothing is attached, there's nothing to check — proceed normally, but say so isn't necessary; just build the case.

## The build sequence

Build in this order — later steps depend on earlier ones, especially the stakeholder questions, which only make sense once the story exists.

**1. Determine scope.** Figure out what's been specified: a named company, a named industry/context, a named archetype (see `references/archetypes.md`), or nothing specific. If the user gives a company or industry but no archetype, pick the archetype that best fits what's realistic for that context. If they give an archetype but no company, invent a plausible company/industry context to carry it. If genuinely nothing is specified, pick a well-rounded default (often an AI-implementation-risk or cost-decomposition case) — don't stop to ask unless the request is truly too vague to proceed.

**2. Research for grounding.** If a real company or industry is named, use web search to pull real, current facts: business model, scale, customer segments, known technology initiatives, competitive pressures, publicly known pain points. This is grounding material, not a search for an existing case — no such case exists to find. The scenario itself is always invented; only the texture around it (numbers, org structure, market dynamics) should be real where possible. If project knowledge is available in this conversation (e.g. Wonderful's published deployment write-ups, the McKinsey casebook), draw on it too — the Wonderful material is especially useful for realistic failure modes and organizational patterns to build a story around.

**3. Build the core story.** Using the chosen archetype's known-good decomposition shape (`references/archetypes.md`) as the backbone, write: `candidate_prompt` (the cold open), `interviewer_context` (what's really going on, for the interviewer only), `explicit_test_objectives` (the specific judgment being probed — e.g. "can they decompose a cost claim into volume × AHT × contract rate before jumping to solutions"), `expected_framework`, `data_reveal_sequence` (each fact tagged with what unlocks it), lightweight `quant_elements`, and an optional `curveball`.

**4. Add stakeholder pressure questions — only now.** With the story built, decide who would realistically be in the room (CHRO, CTO, CFO, Legal, Ops, a frontline manager) and write 2–4 pointed questions tied specifically to this case's stakes — not generic ones. A CHRO layoffs question only lands if the case actually involves headcount-sensitive automation; don't force one in where it doesn't fit. Tag each with the persona and what a strong answer would cover.

**5. Write ideal paths and a sample answer.** Draft 2–3 distinct defensible routes through the case (not one single "correct" answer), plus a short sample strong closing synthesis.

**6. Write the feedback checklist.** A short list of what to look for afterward (structuring, decomposition rigor, stakeholder/behavioral judgment, technical-business translation, synthesis) — a checklist for narrative feedback, not a scored rubric. No numeric scores anywhere in this system.

**7. Write source notes.** Briefly note what real material this drew on (a specific Wonderful dispatch, a McKinsey case adapted, what was researched for the named company).

Full field definitions and format: `references/schema.md`. A blank starting point: `assets/case_template.md`.

## Producing the output

Fill `assets/case_template.md` with everything above and save it as the working case file (markdown) — this is what case-interviewer and case-feedback will read later, so keep the structure intact even though the user won't see this file directly.

Then produce **one exportable document** (read `/mnt/skills/public/docx/SKILL.md` first, then build it) containing:
1. The case story, data, and stakeholder questions (what the user reads before/during practice)
2. A clear visual divider reading `⚠ ANSWER KEY BELOW — only continue once you've run the interview`
3. Everything below that line: expected framework, ideal paths, sample answer, feedback checklist, source notes

Do not split this into multiple files — one document only, by design, even though it means the answer key travels with the case.

If a case index/log is available in this conversation (or the user asks for one), append a row: case_id, title, archetype, industry_context, skills_tested, date. This is what future duplicate-checking and case selection by tag will rely on — mention to the user that they should hold onto and re-attach this index (and their case files) in future sessions, since nothing persists automatically between conversations.

## Style notes

- Real consulting cases (see the McKinsey casebook in project knowledge) alternate structured framework moments with a natural, conversational data reveal — don't write a wall of exposition. Build the `data_reveal_sequence` so an interviewer can drip it out.
- Keep quant light and purposeful. If the case is about cost, a good decomposition is something like cost = volume × AHT × contract rate — not a market-sizing exercise with a calculator-heavy chain of assumptions.
- Write for someone who already has technical and business fluency (per the AI Deployment Strategist context) — don't over-explain basic concepts within the case text itself.
