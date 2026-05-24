---
id: neuro-symbolic-ai
kind: concept
status: draft
source:
  - prior-chat: "The Future Is Neuro-Symbolic: Where Has It Been, and Where Is It Going?"
  - prior-chat: "causal inference, Prolog/Datalog, source-code reasoning, and psychoanalytic modelling discussion"
tags: [neuro-symbolic-ai, ai, reasoning, logic, knowledge-graphs, causal-inference]
depends_on: []
related: [causal-code-intelligence, symbolic-reasoning-and-meaning, programming-hyperreality]
used_by: [causal-code-intelligence]
supersedes: []
---

# Neuro-Symbolic AI

Neuro-symbolic AI combines learned pattern recognition with explicit structures for reasoning, constraint, explanation, and verification.

The useful split is:

- Neural systems perceive, classify, associate, embed, translate, retrieve, and generate hypotheses.
- Symbolic systems represent, constrain, query, prove, plan, check, and explain.

The point is not that neural systems are shallow and symbolic systems are deep. The point is division of labor. Neural methods are strong at fluent contact with messy data. Symbolic methods are strong at inspectable structure, explicit assumptions, compositional reasoning, and correction.

## Paper Signal

The Belle and Marcus paper frames neuro-symbolic AI as a broad research family, not a single architecture. The prior discussion treated the paper as a source for these ingredients:

- knowledge graphs;
- logic programs;
- probabilistic logics;
- Bayesian and causal networks;
- statistical relational learning;
- temporal and dynamic logic;
- differentiable program induction and logic constraints;
- symbolic-executor pipelines;
- LLM-to-solver or LLM-to-tool workflows.

The reusable lesson is that scaling a neural model is not the same as installing a reasoning system. For serious reasoning tasks, the model should often generate or translate into an external structure that can be checked.

## Working Principle

Use neural models to propose and extract. Use symbolic, probabilistic, causal, or formal systems to carry the reasoning burden when the conclusion matters.

This means:

- the LLM can parse a failure log into candidate facts;
- a graph can preserve dependencies and provenance;
- Datalog can derive reachability or suspicious paths;
- a Bayesian model can rank uncertain hypotheses;
- a Pearl-style model can state which interventions would test a claim;
- a solver or proof assistant can check feasibility or proof obligations.

## Where This Repo Uses It

- `concepts/causal-code-intelligence.md`: code facts, debugging hypotheses, interventions, and counterfactual root-cause claims.
- `concepts/symbolic-reasoning-and-meaning.md`: rules as explicit inferential roles, not just labels.
- `concepts/programming-hyperreality.md`: warning that generated artifacts can resemble reasoning without becoming evidence.

## Open Questions

- Which tasks only need fluent synthesis, and which need external symbolic structure?
- When is an LLM explanation enough, and when must the claim be represented as facts, rules, tests, proofs, or interventions?
- How should neuro-symbolic workflows avoid becoming self-certifying loops where AI generates artifacts that only other AI artifacts validate?
