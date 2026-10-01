# Case Archetypes

Each archetype is a generic analytical shape the case builder can wrap around any company or industry. The story changes every time; the underlying decomposition a strong candidate should reach for stays consistent. Pick one explicitly if the user names it (or something close — "give me a churn case" → Churn/Retention). Otherwise infer the best fit from the company/industry context given.

Use these as a starting skeleton for `expected_framework` and `ideal_paths`, not as a rigid script — adapt the specifics to the story.

---

### 1. Cost / Efficiency Decomposition
**Shape:** A cost or efficiency claim (e.g. "AI will cut support costs 30%") needs to be broken into its real drivers before anyone should believe it. Classic decomposition: `cost = volume × handle time × cost per unit` (e.g. contacts × AHT × BPO rate, or transactions × processing time × labor cost). A strong candidate identifies which lever the AI initiative actually moves, and which it doesn't.
**Typical stakeholders:** CFO (is the number real?), Ops lead (can the process actually change?), CHRO (headcount implications).
**Test objectives to draw from:** decomposing a headline number into drivers before accepting it; distinguishing a lever the AI touches from one it doesn't; sanity-checking assumptions against realistic ranges.

### 2. Revenue Growth
**Shape:** A growth target needs decomposition into `revenue = customers × conversion × frequency × average value` (or channel-specific equivalents). Candidate should identify which segment/channel/lever an AI capability plausibly moves, and flag where the story is optimistic.
**Typical stakeholders:** Head of Sales/Growth (does this cannibalize existing motion?), CFO (payback period), Product lead (does this fit the roadmap?).
**Test objectives:** separating incremental growth from cannibalization; identifying the highest-leverage segment; realistic time-to-impact.

### 3. Churn / Retention
**Shape:** Churn has multiple root causes (price, service quality, competitive offers, onboarding failure, product fit). Candidate should segment customers before proposing a fix, and connect the proposed AI intervention to a specific, evidenced cause rather than a generic "better service" claim.
**Typical stakeholders:** Head of CX, CFO (cost of intervention vs. value of retained customer), sometimes Legal/Compliance if the intervention touches regulated communications.
**Test objectives:** segmenting before diagnosing; matching intervention to root cause, not symptom; estimating retained-value vs. cost of the fix.

### 4. Product / Investment Comparison
**Shape:** Two or more options (build in-house vs. two vendors, or two use cases competing for the same budget) need comparison on a consistent set of criteria — cost, time-to-value, risk, strategic fit, optionality/lock-in. Candidate should propose the criteria before evaluating, not jump straight to a gut pick.
**Typical stakeholders:** CTO (technical risk, integration burden), CFO (TCO), sometimes a Board member or GC (lock-in, exit terms).
**Test objectives:** structuring a comparison framework before analyzing; weighing reversibility/optionality, not just headline cost; making a clear recommendation under real trade-offs.

### 5. Build vs. Buy
**Shape:** A specific variant of #4, but with its own well-known tension: internal capability and control vs. speed and vendor expertise. Candidate should surface what's actually being outsourced (the model? the integration work? the ongoing operational muscle?) rather than treating "buy" as a single monolithic choice.
**Typical stakeholders:** CTO/VP Eng (internal capability, opportunity cost of engineering time), CFO (capex vs. opex), CHRO (does this change headcount plans).
**Test objectives:** unbundling what's really being decided; identifying switching costs and lock-in; realistic assessment of internal team's actual capacity/expertise.

### 6. AI Implementation Risk & Governance
**Shape:** An AI system is technically ready but deployment risk (data quality, compliance, failure modes, human-in-the-loop needs, explainability) hasn't been addressed. Candidate should identify the specific failure modes that matter for this use case (not a generic "AI is risky" answer) and propose proportionate guardrails.
**Typical stakeholders:** Legal/Compliance (regulatory exposure), CISO (security), CHRO (workforce impact/trust), a frontline ops manager (what happens when it's wrong).
**Test objectives:** identifying concrete, case-specific failure modes; proportionate (not maximal) governance; distinguishing a pilot risk from a production risk.

### 7. Segment / Prioritization Strategy
**Shape:** Given limited resources and multiple candidate use cases or customer segments, candidate must propose criteria (impact, feasibility, dependency, risk) and rank rather than trying to do everything at once. Often pairs with a "why this one first" follow-up.
**Typical stakeholders:** CEO/COO (strategic sequencing), department heads competing for the same resource, CFO (budget).
**Test objectives:** building a prioritization framework before naming a winner; explicitly stating trade-offs of what's being deprioritized; sequencing logic (what unlocks what).

### 8. Change Management / Adoption
**Shape:** The technology works, but adoption is stalling — usage is low, workarounds have emerged, or a pilot never scaled. Candidate should diagnose whether the blocker is technical, incentive-based, trust-based, or organizational before proposing a fix.
**Typical stakeholders:** Frontline manager (what reps actually experience), CHRO (incentives, training, job security fears), CTO (whether the tool integrates into existing workflow or adds a step).
**Test objectives:** diagnosing before prescribing; distinguishing a training problem from a trust problem from an incentive problem; realistic rollout sequencing.

---

## Choosing an archetype when none is specified

Default to whichever archetype the researched company/industry context makes most plausible right now (e.g. a company known for rapid AI rollout attempts → Change Management or Governance; a company known for cost pressure → Cost Decomposition). If truly nothing points either way, default to Cost/Efficiency Decomposition or AI Implementation Risk & Governance — both are close to the core of what an AI Deployment Strategist actually does day to day.
