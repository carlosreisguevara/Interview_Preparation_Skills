# Case File Schema

This is the shared contract for the whole system. case-builder writes files in this shape; case-interviewer and case-feedback (built separately, later) read them. Keep field names and structure stable — the other two skills depend on being able to find these sections reliably.

## Metadata
- `case_id` — short unique slug, e.g. `nubank-churn-2026-01`
- `title` — human-readable name
- `source_type` — one of: `wonderful`, `mckinsey-adapted`, `named-company`, `custom-industry`
- `industry_context` — e.g. "LatAm consumer fintech", "European telecom customer service"
- `case_archetype` — one of the eight in `archetypes.md` (or a close variant, named)
- `skills_tested` — tags from: technical-business translation, stakeholder alignment, scoping under ambiguity, quantitative/decomposition reasoning, execution judgment, executive communication (add others if the case genuinely calls for it)
- `est_time_min` — rough expected length of a live session

## Grounding
- `research_grounding` — the real facts pulled in about the named company/industry (from web search and/or project knowledge). Bullet points, sourced where possible. This is texture, not plot — the scenario itself is invented.

## The case itself
- `candidate_prompt` — the cold-open prompt exactly as the candidate would first hear it
- `interviewer_context` — what's really going on, background only the interviewer sees, never shown to the candidate up front
- `explicit_test_objectives` — the specific judgment/skill this case is built to probe, stated plainly (this is what a strong candidate response actually needs to demonstrate — not the plot)
- `expected_framework` — the structure/issues a strong candidate should surface early, grounded in the chosen archetype's decomposition shape
- `data_reveal_sequence` — ordered list of facts/exhibits, each with a trigger condition for when it unlocks (e.g. "reveal only if candidate asks about integration constraints" or "reveal automatically after candidate proposes an initial framework")
- `quant_elements` — lightweight, directional decomposition math only (never a full market-sizing or NPV exercise). State the calculation shape and a worked-through answer.
- `curveball` — optional mid-case complication that tests adaptability

## Stakeholder pressure
- `stakeholder_pressure_qs` — list of `{persona, question, what_a_good_answer_covers}`. Built after the core story exists, and specific to this case's actual stakes (not generic).

## Resolution material
- `ideal_paths` — 2–3 distinct, defensible routes through the case (not one single correct answer), each a short sequence of what a strong candidate asks/concludes at each stage
- `sample_strong_answer` — a short closing synthesis/recommendation a top candidate might give

## Feedback material
- `feedback_dimensions` — a checklist (not a scored rubric) covering: structuring/framework quality, decomposition/quant rigor, business + technical judgment, stakeholder/behavioral handling, communication & synthesis, adaptability to the curveball if present

## Provenance
- `source_notes` — what this case drew on: specific Wonderful dispatch, McKinsey case adapted, or what was researched for a named company/industry

## Formatting notes
- Fields containing lists (data reveals, stakeholder questions, ideal paths) should stay as clearly delimited lists/tables in the markdown source, not paragraphs — this is what makes the file reliably readable by the other two skills.
- No numeric scores anywhere in this schema. Feedback is narrative, organized by the checklist above.
