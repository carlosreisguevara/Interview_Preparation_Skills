# Interview Preparation Skills

A set of Claude skills that support preparation for case/decomposition interviews, aimed at AI Deployment Strategist / Forward Deployed Engineer style roles.

The skills work as a pipeline. Each one does a single job:

| Step | Skill | What it does |
|---|---|---|
| 1 | **case-builder** | Builds a complete practice case in one pass: story, data reveals, stakeholder questions, answer key. Does not run or grade the interview. |
| 2 | **case-interviewer** | Runs a live, Socratic interview from a case file made by case-builder. Releases data only when earned, challenges ungrounded hypotheses, and never reveals the answer key. |

## How to use

1. Download the skills you want from the [`downloads/`](downloads) folder (`case-builder.skill`, `case-interviewer.skill`).
2. Add them to Claude as skills.
3. Ask Claude for a case, for example "build me a Nubank case" or "give me a churn case".
4. Attach the case file it produces and say "interview me on this" to run the live session.

## What's in this repo

```
downloads/   Ready-to-upload .skill files
skills/      The readable source for each skill
  case-builder/
    SKILL.md            Instructions for the skill
    references/         Case archetypes and the case-file schema
    assets/             Blank case template
  case-interviewer/
    SKILL.md            Instructions for the skill
    references/         Interview phrasing techniques
```

`skills/` is the source of truth. The files in `downloads/` are the same content packaged for upload.

## Roadmap

A **case-feedback** skill is referenced by both skills. It would read the case plus the interview transcript and give improvement-focused feedback. It is not in this repo yet.
