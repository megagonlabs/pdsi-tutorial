# Selected Reading List — Post-Deployment Self-Improving Language Agents

*Proposed revision for the [AACL–IJCNLP 2026 PDSI tutorial](https://github.com/megagonlabs/pdsi-tutorial). Research checked November 6, 2026. This is a proposal, not a change to the GitHub repository.*

## Reading guide

This bibliography studies a **deployed agent system** that may preserve and use changes to knowledge, memory, skills, prompts, tools, policies, code, and model parameters **across task episodes**. A persistent update is evidence of adaptation, not automatically of improved competence. Improvement must be measured on future tasks and should be tested for retention, regressions, transfer, cost, and unwanted effects.

**Tags:** **CORE** = most useful tutorial reading; **SUPPORTING** = deepening or alternative mechanism; **CONTRAST** = crucial background, but not itself a demonstration of post-deployment learning; **FRONTIER** = newer work or preprint requiring extra scrutiny. A method may be useful to PDSI without having been evaluated in a deployed, lifelong setting.

**Two orthogonal distinctions:** (1) *when* an update happens: during a single interaction; between deployment episodes; or in offline training/design; (2) *what* changes: response/context; durable memory/knowledge; skills/workflows/harness; model weights; or the update mechanism itself. **Recursive self-improvement (RSI) is one possible self-improvement mechanism, not a synonym for post-deployment learning.**

## 12-paper suggested fast path

For participants with limited time, this sequence tells a coherent story from historical principles through systems and rigorous evaluation.

1. **[CORE]** [Carlson et al. (2010), *Toward an Architecture for Never-Ending Language Learning*](https://ojs.aaai.org/index.php/AAAI/article/view/7519) — Original NELL architecture: continual extraction coupled to learning how to extract better.
2. **[CORE]** [Mitchell et al. (2015), *Never-Ending Learning*](https://ojs.aaai.org/index.php/AAAI/article/view/9498) — Broader never-ending learning paradigm, coupling constraints, and lessons from NELL.
3. **[CORE]** [Zhao et al. (2024), *ExpeL: LLM Agents Are Experiential Learners*](https://ojs.aaai.org/index.php/AAAI/article/view/29936) — Reusable, non-parametric insights distilled from experience.
4. **[CORE]** [Wang et al. (2023), *Voyager: An Open-Ended Embodied Agent with Large Language Models*](https://arxiv.org/abs/2305.16291) — Explicit executable skills, curriculum, and iterative environment feedback.
5. **[CORE]** [Wang et al. (2025), *Agent Workflow Memory*](https://proceedings.mlr.press/v267/wang25bx.html) — Transferable workflow knowledge from trajectories; offline and online modes should be distinguished.
6. **[CORE]** [Hassell et al. (2026), *Learning from Supervision with Semantic and Episodic Memory*](https://arxiv.org/abs/2510.19897) — Semantic/episodic critique memory; a direct example of memory-driven learning without weight changes.
7. **[CORE]** [Ferraz et al. (2026), *Retrieval-Augmented LLM Agents: Learning to Learn from Experience*](https://aclanthology.org/2026.emnlp-main.57/) — Experience retrieval and retrieval-aware training, including generalization with imperfect trajectories.
8. **[CORE]** [Moll et al. (2026), *GRASP: Gated Regression-Aware Skill Proposer for Self-Improving LLM Agents*](https://aclanthology.org/2026.emnlp-main.452/) — Improvement gates and regression budgets, rather than blind accumulation.
9. **[CORE]** [Zhong et al. (2026), *SkillLearnBench*](https://arxiv.org/abs/2604.20087) — Evaluating acquisition, use, and outcomes of continually learned skills; drift under self-only feedback.
10. **[CORE]** [Xue et al. (2026), *PAST-Bench*](https://arxiv.org/abs/2608.04003) — Experience-on/off controls and evidence for save–retrieve–update pathways (preprint).
11. **[CORE]** [Zhao et al. (2026), *Continual Learning Exam*](https://arxiv.org/abs/2610.33956) — Increasingly demanding professional task ladders; valuable but does not replace direct causal tests of saved state (recent preprint).
12. **[CORE]** [Zhang et al. (2025), *Darwin Gödel Machine*](https://arxiv.org/abs/2505.22954) — An RSI example: code/harness modifications selected by evaluations, not necessarily an online deployed-learning protocol.

## I. Foundations: learning over time

- **[CORE]** [Carlson et al. (2010), *Toward an Architecture for Never-Ending Language Learning*](https://ojs.aaai.org/index.php/AAAI/article/view/7519) — Knowledge acquisition plus improved future extraction; AAAI 2010.
- **[CORE]** [Mitchell et al. (2015), *Never-Ending Learning*](https://ojs.aaai.org/index.php/AAAI/article/view/9498) — Tasks, coupling constraints, feedback, and self-reflection; AAAI 2015. **New addition.**
- **[CORE]** [Mitchell et al. (2018), *Never-Ending Learning*](https://doi.org/10.1145/3191513) — Retrospective on the paradigm; *Communications of the ACM*.
- **[SUPPORTING]** [Thrun and Mitchell (1995), *Lifelong Robot Learning*](https://publications.ri.cmu.edu/lifelong-robot-learning) — Early task-transfer view with an embodied agent. **New addition.**
- **[SUPPORTING]** [Thrun (1998), *Lifelong Learning Algorithms*](https://publications.ri.cmu.edu/lifelong-learning-algorithms) — Lifelong transfer across tasks.
- **[SUPPORTING]** De Lange et al. (2022), *A Continual Learning Survey: Defying Forgetting in Classification Tasks* — Classical stability–plasticity and forgetting baseline (existing reference).
- **[SUPPORTING]** [Shi et al. (2025), *Continual Learning of Large Language Models: A Comprehensive Survey*](https://doi.org/10.1145/3735633) — Useful distinction between continual model training and system-level lifelong learning. **New addition.**

## II. Clarifying the boundary: response adaptation versus durable learning

- **[CONTRAST]** [Lewis et al. (2020), *Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks*](https://arxiv.org/abs/2005.11401) — Retrieved information can update answers without necessarily teaching the agent a new competence.
- **[CONTRAST]** [Yao et al. (2023), *ReAct*](https://arxiv.org/abs/2210.03629) — Reasoning–action scaffold; not by itself a cross-session learning algorithm.
- **[CONTRAST]** [Schick et al. (2023), *Toolformer*](https://arxiv.org/abs/2302.04761) — Training a model for tool use, chiefly an offline capability-acquisition example.
- **[CONTRAST]** [Asai et al. (2024), *Self-RAG*](https://arxiv.org/abs/2310.11511) — Adaptive retrieval and critique at inference; not evidence of persistent post-deployment improvement.
- **[CONTRAST]** [Madaan et al. (2023), *Self-Refine*](https://arxiv.org/abs/2303.17651) — Improves an answer within a single episode; contrast with persistent learning.
- **[CORE]** [Shinn et al. (2023), *Reflexion: Language Agents with Verbal Reinforcement Learning*](https://proceedings.neurips.cc/paper_files/paper/2023/hash/1b44b878bb782e6954cd888628510e90-Abstract-Conference.html) — Episodic reflection across trials, but distinguish trial-level buffers from durable deployments. **Correct the year in the current reading list: NeurIPS 2023, not 2024.**
- **[CORE]** [Kamoi et al. (2024), *When Can LLMs Actually Correct Their Own Mistakes?*](https://aclanthology.org/2024.tacl-1.78/) — Critical analysis of when self-feedback succeeds; emphasizes reliable external feedback. **New addition.**

## III. Durable knowledge, evolving memory, and experience retrieval

- **[SUPPORTING]** [Park et al. (2023), *Generative Agents: Interactive Simulacra of Human Behavior*](https://doi.org/10.1145/3586183.3606763) — Memory, reflection, and planning; memory-supported behavior is not automatically improved competence.
- **[SUPPORTING]** [Packer et al. (2023), *MemGPT: Towards LLMs as Operating Systems*](https://arxiv.org/abs/2310.08560) — Hierarchical persistent memory and context management.
- **[SUPPORTING]** [Chhikara et al. (2025), *Mem0: Building Production-Ready AI Agents with Scalable Long-Term Memory*](https://arxiv.org/abs/2504.19413) — Production-minded long-term memory mechanisms; inspect evaluation carefully (preprint).
- **[SUPPORTING]** [Xu et al. (2025), *A-MEM: Agentic Memory for LLM Agents*](https://arxiv.org/abs/2502.12110) — Self-organizing linked memories and evolving structures; NeurIPS 2025.
- **[CORE]** [Hassell et al. (2026), *Learning from Supervision with Semantic and Episodic Memory: A Reflective Approach to Agent Adaptation*](https://arxiv.org/abs/2510.19897) — Instance-level critique and cross-instance semantic guidance; ACM CAIS 2026; worked-example candidate.
- **[CORE]** [Amin-Naseri et al. (2026), *A Dynamic Self-Evolving Extraction System (DySECT)*](https://arxiv.org/abs/2603.06915) — Closed loop from extraction to accumulated KB and back to improved extraction; ACL 2026 demo and worked-example candidate.
- **[CORE]** [Ouyang et al. (2025), *ReasoningBank: Scaling Agent Self-Evolving with Reasoning Memory*](https://arxiv.org/abs/2509.25140) — Distills lessons from successes and failures for subsequent tasks; differentiates raw traces from reusable insights.
- **[SUPPORTING]** [Wang et al. (2026), *Knowledge-Centric Self-Improvement*](https://arxiv.org/abs/2607.19592) — Transferable persistent knowledge rather than agent-specific code as the central self-improving artifact (preprint).
- **[SUPPORTING]** [Kim et al. (2026), *Memory Transfer Learning: How Memories are Transferred Across Domains in Coding Agents*](https://aclanthology.org/2026.emnlp-main.2666/) — Abstract lessons transfer; overly specific traces may cause negative transfer.
- **[SUPPORTING]** [Liu et al. (2026), *MemPro: Agentic Memory Systems as Evolvable Programs*](https://aclanthology.org/2026.emnlp-main.1364/) — Evolves the memory construction–retrieval pipeline itself; EMNLP 2026.

## IV. Experiences becoming reusable skills, workflows, and harnesses

- **[CORE]** [Zhao et al. (2024), *ExpeL: LLM Agents Are Experiential Learners*](https://ojs.aaai.org/index.php/AAAI/article/view/29936) — Abstraction and reuse of previous experiences.
- **[CORE]** [Wang et al. (2023), *Voyager*](https://arxiv.org/abs/2305.16291) — Executable skill library, open-ended curriculum.
- **[CORE]** [Wang et al. (2025), *Agent Workflow Memory*](https://proceedings.mlr.press/v267/wang25bx.html) — Online and offline workflow induction; ICML 2025.
- **[SUPPORTING]** [Zhou et al. (2025), *Memento: Fine-tuning LLM Agents without Fine-tuning LLMs*](https://arxiv.org/abs/2508.16153) — Case-based experience reuse and memory-directed learning (preprint).
- **[CORE]** [Zhu et al. (2026), *Unified Context Evolution for LLM Agents*](https://aclanthology.org/2026.emnlp-main.2188/) — Maintains typed Memory/Strategy/Workflow/Skill units and prunes less useful ones; EMNLP 2026.
- **[CORE]** [Moll et al. (2026), *GRASP*](https://aclanthology.org/2026.emnlp-main.452/) — Held-out acceptance gate and explicit regression budget; EMNLP 2026.
- **[SUPPORTING]** [Liu et al. (2026), *Harnessing LLM Agents with Skill Programs*](https://aclanthology.org/2026.emnlp-main.2086/) — Converts skills into executable interventions; EMNLP 2026.
- **[SUPPORTING]** [Wei et al. (2026), *Evo-Harness: Context-to-Harness Skill Compilation for Self-Evolving Agents*](https://aclanthology.org/2026.emnlp-main.969/) — Compiles noisy executions into reusable evolving harness skill material; EMNLP 2026.
- **[SUPPORTING]** [Lin et al. (2026), *When Not to Imitate: Boundary-Aware Skill Memory for Reliable Tool-Use LLM Agents*](https://aclanthology.org/2026.findings-emnlp.1141/) — Learn *applicability limits*, not only examples of successful procedures; Findings EMNLP 2026.

## V. Learning through weights and recursive self-improvement (RSI)

**Interpretation:** Parameter adaptation and RSI are important complementary techniques, but neither is synonymous with PDSI. Ask whether an individual method really runs and persists updates **after the system has been deployed**.

- **[SUPPORTING]** [Zweiger et al. (2025), *Self-Adapting Language Models (SEAL)*](https://arxiv.org/abs/2506.10943) — Self-generated update directives and lasting weight adaptation; NeurIPS 2025.
- **[SUPPORTING]** [Zhao et al. (2025), *Absolute Zero: Reinforced Self-play Reasoning with Zero Data*](https://arxiv.org/abs/2505.03335) — Self-proposed/verifiable training curricula; NeurIPS 2025, primarily a training paradigm, not automatically PDSI.
- **[SUPPORTING]** [Yin et al. (2025), *Gödel Agent*](https://aclanthology.org/2025.acl-long.1354/) — Agent-side self-modification, self-referential design; ACL 2025.
- **[CORE]** [Zhang et al. (2025), *Darwin Gödel Machine: Open-Ended Evolution of Self-Improving Agents*](https://arxiv.org/abs/2505.22954) — Empirically validated changes to an agent's own code, with archives of variants; relevant to RSI regardless of deployment timing.
- **[FRONTIER]** [Shi et al. (2026), *PluginRSI: Recursive Improvement of Agent Harnesses with Reusable Plugins*](https://arxiv.org/abs/2609.32423) — Evolves modular reusable agent-harness components (preprint).
- **[SUPPORTING]** [Ren et al. (2026), *Self-Improvements in Modern Agentic Systems: A Survey*](https://arxiv.org/abs/2607.13104) — Contemporary model- vs scaffold-modification taxonomy; excellent secondary resource.

## VI. Longitudinal evaluation: does retained state actually improve competence?

- **[CONTRAST]** Yoran et al. (2024), *AssistantBench: Can Web Agents Solve Realistic and Time-Consuming Tasks?* — Useful capability benchmark, but single-task success is not longitudinal learning evidence; EMNLP 2024.
- **[SUPPORTING]** [Maharana et al. (2024), *Evaluating Very Long-Term Conversational Memory of LLM Agents (LoCoMo)*](https://aclanthology.org/2024.acl-long.747/) — Multi-session recall, not direct proof of task-competence gain; ACL 2024.
- **[SUPPORTING]** [Wu et al. (2025), *LongMemEval*](https://proceedings.iclr.cc/paper_files/paper/2025/hash/d813d324dbf0598bbdc9c8e79740ed01-Abstract-Conference.html) — Knowledge updates, multi-session/temporal reasoning, abstention; ICLR 2025.
- **[SUPPORTING]** [Hu et al. (2025), *MemoryAgentBench*](https://arxiv.org/abs/2507.05257) — Incremental multi-turn interactions; retrieval, test-time learning, long-range understanding, and forgetting.
- **[SUPPORTING]** [Tang et al. (2025), *EvoWiki*](https://aclanthology.org/2025.acl-long.47/) — Evolving facts and temporal knowledge, rather than broad procedural competence; ACL 2025.
- **[CORE]** [Zhong et al. (2026), *SkillLearnBench*](https://arxiv.org/abs/2604.20087) — Verifiable skill, execution, and task outcome metrics; COLM 2026.
- **[CORE]** [Xue et al. (2026), *PAST-Bench*](https://arxiv.org/abs/2608.04003) — Ordered episodes with saved experience enabled/disabled, checking actual pathway use (preprint).
- **[CORE]** [Zhao et al. (2026), *Continual Learning Exam*](https://arxiv.org/abs/2610.33956) — Long-horizon task ladders; interpret gains and causality carefully (October 2026 preprint).
- **[SUPPORTING]** [Ma et al. (2026), *Benchmarking Continual Agent Memory for Online Learning, Transfer, and Forgetting*](https://openreview.net/pdf/2cd400b6dec127be21f88da3528c021c699c914f.pdf) — Combines factual/personal and procedural/system memory; ICLR 2026 workshop.

## VII. Reliability, bounded updates, failure modes, and governance

- **[CORE]** [Moll et al. (2026), *GRASP*](https://aclanthology.org/2026.emnlp-main.452/) — Regression-gated update acceptance; a practical design pattern.
- **[CORE]** [Lin et al. (2026), *When Not to Imitate*](https://aclanthology.org/2026.findings-emnlp.1141/) — Applicability boundaries guard against negative transfer from remembered successes.
- **[CORE]** [Kamoi et al. (2024), *When Can LLMs Actually Correct Their Own Mistakes?*](https://aclanthology.org/2024.tacl-1.78/) — Limits of self-critique absent externally reliable feedback.
- **[SUPPORTING]** [Wang et al. (2026), *AgentSpec: Customizable Runtime Enforcement for Safe and Reliable LLM Agents*](https://conf.researchr.org/details/icse-2026/icse-2026-research-track/29/AgentSpec-Customizable-Runtime-Enforcement-for-Safe-and-Reliable-LLM-Agents) — Runtime enforcement of policy constraints; ICSE 2026.
- **[SUPPORTING]** [Shumailov et al. (2024), *AI models collapse when trained on recursively generated data*](https://doi.org/10.1038/s41586-024-07566-y) — A failure mode of uncritical recursive synthetic-data training; *Nature* 2024. Do not assume all self-generated training suffers collapse.
- **[SUPPORTING]** [Srivastava and He (2025), *MemoryGraft: Persistent Compromise of LLM Agents via Poisoned Experience Retrieval*](https://arxiv.org/abs/2512.16962) — Experience stores become persistent prompt-injection surfaces (preprint).

## Further surveys and continuously updated indices

- [Gao et al. (2025), *A Survey of Self-Evolving Agents*](https://arxiv.org/abs/2507.21046) — Organizes **what**, **when**, and **how** an agent evolves; note its scope is broader than post-deployment learning.
- [Ren et al. (2026), *Self-Improvements in Modern Agentic Systems*](https://arxiv.org/abs/2607.13104) — Broad model/scaffold taxonomy and [paper index](https://selfimproving-agent.github.io/).
- [Self-Improving Agents in the Era of Experience: survey companion](https://frontisai.github.io/Awesome-Self-Improving-Agents/) — Broad evolving catalogue of research; use for discovery, not as a substitute for verifying primary papers.

## A reading-list standard for future additions

For each candidate, record: **mechanism** (what is updated); **timing** (within-episode, cross-episode online, or offline); **persistence** (what survives); **feedback** (environment, verifier, user, self-judge); **evidence** (held-out subsequent tasks, ablations, longitudinal trajectories); **regression/safety checks**; and **publication status** (peer-reviewed venue or preprint). Avoid describing a method as *post-deployment learning* solely because it uses memory, self-feedback, optimization, or the word "recursive".

### A cross-episode evaluation protocol worth teaching

1. Evaluate system `S0` on a pre-specified task distribution and a protected retention set.
2. Let `S0` interact with a separate ordered experience stream `E1...Et`.
3. Record candidate persistent change `Δt`, its source evidence, and whether the update is accepted.
4. Compare `S_t` with a **no-update control** under the same context, model, task budget, and test distribution.
5. Test new tasks, earlier tasks, transfer tasks, and changed-environment tasks; measure success, forgetting, negative transfer, resources, and safety.
6. Probe whether the intended persistent artifact was truly used (not merely stored or present in context).
7. Repeat over multiple horizons and update sequences; expose variance, rollback criteria, and failure cases.

**Caution:** A conventional benchmark score after a changed prompt or larger retrieved context is insufficient evidence that the *same deployed system* developed durable future competence.
