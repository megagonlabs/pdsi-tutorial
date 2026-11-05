# Post-Deployment Self-Improving Language Agents

**Learning, Memory, and Adaptation**  
**AACL–IJCNLP 2026 · Tutorial T4**

**Instructor:** Estevam Hruschka — Lab Director and Staff Research Scientist, [Megagon Labs](https://megagon.ai/)

**When:** Monday, November 9, 2026 · 14:00–17:30 (China Standard Time, UTC+8)  
**Where:** Muhe Hall C · Hengqin, China

[**Official tutorial abstract**](https://aclanthology.org/2026.aacl-tutorials.4/) · [**AACL2026 tutorial program**](https://2026.aaclnet.org/program/tutorials/) 

## About this tutorial

Deployed language agents operate in environments that change: users develop new goals, knowledge sources evolve, tools and APIs shift, and previously unseen failures arise. A prompt edit or a refreshed document index can alter behavior, but **not every adaptation constitutes learning, and not every persistent change produces an improvement**.

This tutorial connects never-ending, lifelong, and continual learning with modern LLM-based agents that continue to improve after being deployed. We take a **system-level view**: learning may involve durable changes to memory, retrieved knowledge, tool-use procedures, policies, model parameters, or any other element of the agent harness. The central challenge is deciding **what to learn, from which evidence, how to validate an update, and whether it improves future performance without unacceptable regressions**.

The tutorial synthesizes foundational research and modern work on agentic NLP, retrieval and memory, reflection, online adaptation, and evaluation over time. It is intended for NLP/ML researchers, practitioners building long-running language agents, and graduate students familiar with LLMs.

## Tutorial outline

The planned **three-hour instructional program** covers:

| Part | Topic | Time |
|:--|:--|--:|
| I | Why static NLP systems are no longer enough | 20 min |
| II | Foundations: never-ending, lifelong, and continual learning | 30 min |
| III | What a self-improving language agent learns | 35 min |
| IV | Design patterns for learning after deployment | 35 min |
| V | Evaluation, governance, and reliability under change | 30 min |
| VI | Worked example and case studies | 20 min |
| VII | Open research problems and discussion | 10 min |

The conference reserves a 14:00–17:30 slot; the above segments total 180 minutes of instruction. The detailed agenda, including breaks, is subject to the final session schedule. See [the expanded outline](docs/outline.md).

## Materials

This repository is the evolving home for the tutorial. 

- [Expanded outline](docs/outline.md) — topics and learning outcomes
- [Selected reading list](docs/reading-list.md) — foundational and recent literature
- [Slides](slides/README.md) — slides will be linked or added here when available
<!--
- [Worked example](examples/README.md) — 
GitHub Pages -->

## Distinguishing adaptation from improvement

A useful guiding principle for the tutorial is that **persistence is necessary for cross-episode learning, but persistence alone does not establish improved competence**. Evaluation needs to test future behavior across tasks, situations, and time, including regressions and failures, rather than assuming any successful update is beneficial.

## Citation

Estevam Hruschka. 2026. [Post-Deployment Self-Improving Language Agents: Learning, Memory, and Adaptation](https://aclanthology.org/2026.aacl-tutorials.4/). In Proceedings of the 15th International Joint Conference on Natural Language Processing and the 5th Conference of the Asia-Pacific Chapter of the Association for Computational Linguistics: Tutorial Abstracts, pages 27–31, Hengqin, China. Association for Computational Linguistics.
 (Hruschka, AACL-IJCNLP 2026)

