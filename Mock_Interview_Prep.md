# Mock Interview Prep — Michael Munga

Use this to rehearse before recording your 30-minute mock interview (Week 11, Part C). Practice out loud, not just in your head — the grading covers STAR usage and technical accuracy on delivery, not just content.

## Motivation & Fit

1. **Walk me through your background — procurement to software to data analytics. Why the pivot?**
   - Anchor: procurement gave you the operations lens; you moved into engineering to build the tools, then into analytics because that's where the decisions actually get made.
2. **Why operational/data analyst roles specifically, not pure software engineering?**
   - Anchor: you like being closest to the decision a business makes, not just the code that supports it — cite the KEMSA and FlowGuard work as evidence.
3. **Where do you want to be in 2 years?**
   - Keep this honest and specific to you — don't let me script this one for you.

## Behavioral (STAR)

4. **Tell me about a time you had to change your understanding of a project midway through.**
   - *Situation:* Assumed rerouting trucks between depots would solve the FlowGuard turnaround problem.
   - *Task:* Validate the assumption before building on it.
   - *Action:* Researched OMC contractual storage agreements (TSAs) and found KPC has no visibility into retail station capacity — rerouting wasn't viable.
   - *Result:* Reframed the whole problem around depot clearance time instead, which was the real, addressable bottleneck.

5. **Tell me about a time you found a flaw in existing work (yours or someone else's) and had to fix it.**
   - *Situation:* Audited a teammate's existing capstone repo.
   - *Task:* Assess what was actually working vs. what looked done but wasn't (e.g. forecasting model, redistribution engine using hardcoded distances).
   - *Action:* Rebuilt the redistribution engine with real haversine distance, built out the unfinished financial scorecard and multi-horizon forecasting.
   - *Result:* Verified end-to-end with real data — e.g., a real 8.0km Kiambu→Nairobi match, approved through the actual workflow.

6. **Tell me about a time you had to explain a technical result to a non-technical audience.**
   - *Situation:* Week 6 predictive maintenance work required two briefs — one for engineers, one for a CFO audience.
   - *Task:* Translate a Logistic Regression classifier's output into a decision a CFO would act on.
   - *Action:* Focused on cost/risk framing instead of model internals — same discipline behind this term's Week 11 business case.
   - *Result:* Practice you can point to directly for this bootcamp's own CFO-facing deliverable.

## Technical / Procurement Knowledge

7. **Explain the difference between correlation and causation, using an example from your own work.**
   - Anchor: the Week 3 sensor/weather correlation (r = -0.778) that didn't survive robustness checks (leave-one-out, Spearman, Fisher z) — driven by a single outlier.
8. **How do you handle class imbalance in a classification problem?**
   - Anchor: SMOTE / class weights, used in Week 9's operational ML work.
9. **Walk me through how you'd validate a forecasting model before trusting it operationally.**
   - Anchor: tiered flags (Critical/Warning/Watch/Healthy) rather than a single binary alert — reduces false-alarm fatigue while still catching real risk.
10. **From your procurement background — how do you evaluate whether a supplier consolidation is worth it?**
    - This one's yours to answer from direct experience — don't let a model answer replace your own numbers here.

## Analytical Thinking

11. **If a stockout forecast is wrong 20% of the time, is the model still useful? How would you decide?**
    - Anchor: depends what "wrong" costs — a false Critical flag costs a wasted review; a missed Critical flag costs an actual stockout. Ask what the asymmetry in cost is before answering blind.
12. **How would you prioritize which of KPC's five problem domains to tackle first with limited engineering time?**
    - Anchor: your team's own pivot from Domain 5→2 after discovering an assumption (destination readiness) wasn't viable — prioritize by validated bottleneck size, not by which problem sounds most impressive.

---

**How to use this:** don't memorize scripts word-for-word — walk through each Situation→Task→Action→Result out loud once, then again in your own words. The interviewer wants to hear you think, not recite.
