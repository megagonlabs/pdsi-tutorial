# Tutorial outline

*AACL–IJCNLP 2026 · Post-Deployment Self-Improving Language Agents: Learning, Memory, and Adaptation*


## Intended learning outcomes

Participants should be able to:

1. Relate **never-ending learning**, **lifelong learning**, and **continual learning** to current language-agent and post-deployment self-improving research.
2. Identify the **object of learning** (knowledge, memory, skills, policies, self-monitoring), the available feedback, and the durability of an update.
3. Evaluate whether persistent adaptation produces **future improvement**, including temporal generalization, forgetting, drift, and adverse side effects.
4. Design a bounded update-and-validation loop with provenance, explicit acceptance criteria, and rollback.

## Part I — Why static NLP systems are no longer enough (20 minutes)

- Changing facts, user intents, tools, APIs, and task distributions.
- Why ad hoc prompt edits and occasional retrieval refreshes do not, by themselves, solve continual adaptation.
- The distinction between a deployed language agent and a fixed predictor.

## Part II — Foundations: never-ending, lifelong, and continual learning (30 minutes)

- History, terminology, and assumptions, including NELL and subsequent learning paradigms.
- Stability versus plasticity, transfer, forgetting, drift, and open-ended learning objectives.
- What counts as learning across episodes instead of behavior confined to one interaction.

## Part III — What a self-improving agent learns (35 minutes)

- **Knowledge and memory:** facts, provenance, retrieved sources, durable experiences.
- **Skills:** procedures, tools, workflows, and task decomposition.
- **Policies:** planning, recovery, and decision heuristics.
- **Self-monitoring:** uncertainty, failure prediction, anomaly detection.
- Evidence sources: user feedback, retrieval traces, tool outcomes, environment observations, and evaluation logs.

## Part IV — Design patterns for learning after deployment (35 minutes)

- Modular versus end-to-end adaptation.
- Memory updates, selective consolidation, and forgetting.
- Reflective and iterative improvement, including the limitations of self-feedback.
- Provenance and auditability; update gating and rollback.
- Weak supervision and synthetic data without uncontrolled error amplification.

## Part V — Evaluation, governance, and reliability under change (30 minutes)

- Measure progress beyond a single benchmark snapshot.
- Regression detection, temporal generalization, negative transfer, and forgetting.
- Tool-use reliability, long-horizon behavior, offline versus online evaluation.
- Update policies, safety checks, privacy, and bounded risk.
- Why a stored change is not synonymous with improved competence.

## Part VI — Worked example and case studies (20 minutes)

- Revisit information extraction as an agent deployed over multiple episodes.
- Introduce evolving schemas, evidence, feedback, and memory/state updates.
- Validate candidate updates against future tasks and older capabilities before consolidation.
- Discuss failure cases, e.g., drift or contamination from noisy feedback.

## Part VII — Open research problems (10 minutes)

- Benchmarks for self-improving language agents across time.
- Multilingual and domain-specific adaptation under limited feedback.
- Choosing what to learn online versus offline.
- Preventing reward hacking, proxy optimization, and silent degradation.

## Timing note

The seven teaching segments total **180 minutes**. The official event listing specifies **14:00–17:30** on **Monday, November 9, 2026**, in **Muhe Hall C**. Break timing has not been included in this draft.
