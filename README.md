# Interview Preparation Skills

A set of Claude skills that support preparation for case/decomposition interviews.

## Case Builder

`Case_Builder.zip` contains the **case-builder** skill. It builds a complete, self-contained practice case for AI Deployment Strategist / Forward Deployed Engineer style interviews, in a single pass, as one exportable document. Each case includes:

- the case story and the opening prompt for the candidate
- data reveals, released step by step
- stakeholder pressure questions (for example CHRO, CTO, CFO, Legal)
- ideal answer paths and a sample closing synthesis
- a feedback checklist and source notes

The answer key sits below a clear divider in the same document, so only read past it once you have run the interview.

Case Builder only *builds* cases. It does not run a live interview and does not grade one.

### What's in the zip

| File | Purpose |
|---|---|
| `case-builder.skill` | The packaged skill, ready to upload to Claude |
| `case-builder-SKILL.md` | The skill's instructions (readable source) |
| `case-builder-archetypes.md` | Case archetypes and their decomposition shapes |
| `case-builder-schema.md` | Field definitions and format for a case file |
| `case-builder-template.md` | A blank case template |

### How to use it

1. Download `Case_Builder.zip` and unzip it.
2. Add `case-builder.skill` to Claude as a skill.
3. Ask for a case, for example "build me a Nubank case", "a telecom customer service AI case", or "give me a churn case".
