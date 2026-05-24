---
id: causal-code-intelligence
kind: concept
status: draft
source:
  - user-request: "Write down my idea for causal inference and your findings"
  - prior-chat: "neuro-symbolic AI, causal source-code reasoning, and Datalog/Prolog discussion"
  - prior-chat: "reverse engineering, causal modelling, queueing, and codebase reasoning follow-up"
tags: [causal-inference, software-debugging, reverse-engineering, neuro-symbolic-ai, datalog, prolog, root-cause-analysis]
depends_on: [retrieval-and-action-system, neuro-symbolic-ai]
related: [retrieval-and-action-system, programming-hyperreality, mathematical-programming-state-estimation]
used_by: []
supersedes: []
---

# Causal Code Intelligence

This thread explores applying Judea Pearl-style causal inference to source code for automatic root cause analysis, bug detection, and reverse engineering.

The working idea is to treat a codebase as a partially observed causal system. Static code structure gives possible causal paths. Runtime traces, tests, incidents, logs, and deployment history give observations. Interventions such as patches, reverts, mocks, feature flags, controlled inputs, and replay experiments provide stronger causal evidence.

## Core Claim

Source code analysis should move beyond asking only "what is connected to what?" It should also ask:

- What could have caused this failure?
- What evidence supports that causal claim?
- What intervention would test it?
- What counterfactual claim is justified?
- What part of the recovered model is static structure, observed behavior, probabilistic belief, or verified fact?

## Source Code As Causal Graph

Source code can be read as a possible causal mechanism, but not every static dependency is a live causal influence in a given failure.

- Static structure gives possible paths: calls, dataflow, control flow, configuration reads, dependency edges, service calls, ownership, and build or deployment links.
- Runtime structure gives activated paths: traces, logs, stack frames, spans, counters, test executions, user actions, and observed state transitions.
- Change structure gives plausible perturbations: commits, feature flags, dependency upgrades, schema changes, configuration edits, and environmental shifts.
- Interventions give stronger evidence: rollback, replay, controlled input changes, mocks, fault injection, instrumentation, and patches.

A root-cause claim should be treated as a counterfactual claim: if this part had been different, under relevant background conditions, the failure would not have occurred. The practical approximation is to search for the smallest intervention that prevents the failure while preserving the rest of the scenario.

## Pearl-Style Levels

- Association:
  This error correlates with a deploy, input, log pattern, module, dependency, or code path. Association is useful for ranking hypotheses but does not prove root cause.

- Intervention:
  Change the system and observe whether the failure changes. Examples include reverting a commit, disabling a feature flag, mocking a dependency, changing an input, adding instrumentation, or replaying with a patched function.

- Counterfactual:
  Ask whether the incident would have happened if a specific function, dependency, configuration, input, or commit had been different while relevant background conditions were held fixed. This requires more care than ordinary log analysis.

Raw logs are usually observational. Strong root-cause claims usually need interventions, replay, controlled experiments, or a well-justified causal model.

## Neuro-Symbolic Shape

The neuro-symbolic approach is applicable here if each layer has a clear role:

- Neural or LLM layer:
  Extract candidate facts from code, logs, stack traces, commits, issue text, documentation, and postmortems. Generate possible hypotheses and translate messy evidence into structured claims.

- Symbolic structure layer:
  Build AST, CFG, call graph, dataflow graph, dependency graph, ownership graph, deployment graph, configuration graph, and test-coverage graph.

- Rule layer:
  Use logic rules to derive reachability, taint paths, dependency closure, ownership paths, suspicious change-impact paths, and violated invariants.

- Probabilistic and causal layer:
  Rank likely causes under uncertainty, distinguish correlation from intervention evidence, and represent causal assumptions explicitly.

- Verification layer:
  Use tests, replay, symbolic execution, constraints, type checks, model checking, or proof assistants when a claim needs stronger justification.

The target workflow is:

```text
failure evidence
-> extracted facts
-> code, runtime, and change graph
-> symbolic rules
-> causal hypotheses
-> interventions or replay
-> ranked and explained root cause
```

## Knowledge Graphs And Rule-Derived Knowledge

A knowledge graph can be built with Prolog or Datalog-style facts, but the representation choice matters.

- Typed predicates are cleaner for reasoning: `calls(a, b)`, `reads(f, config)`, `changed(commit, file)`.
- Generic triples are more flexible for ingestion and interoperability: subject, predicate, object.
- A serious system may use both: typed predicates for rules, triples for interchange and loose metadata.

Rules do not create new objects in the world. They make consequences explicit. In Fregean terms, a rule can change the sense under which an existing structure is grasped. For example, `possible_cause(Change, Failure)` gives an inferential role to a debugging hypothesis: it is not a label of suspicion by mood, but a description earned by evidence and rules.

## Datalog And Prolog

Datalog is a strong fit for codebase reasoning because code facts can become predicates and debugging hypotheses can become rules.

Example fact types:

```prolog
calls(function_a, function_b).
reads(function, state).
writes(function, state).
introduced_by(function, commit).
depends_on(service_a, service_b).
observed_in(failure, trace).
```

Example derived rules:

```prolog
reachable(A, B) :- calls(A, B).

possible_cause(Change, Failure) :-
  introduced_by(Func, Change),
  reachable(Func, Failure).
```

Datalog is useful for:

- recursive reachability;
- taint and dataflow analysis;
- dependency closure;
- change-impact analysis;
- ownership and responsibility paths;
- explainable "why is this suspicious?" traces;
- scalable querying over large static fact bases.

Prolog is useful for:

- exploratory reasoning;
- prototype search strategies;
- interactive hypothesis development;
- richer recursive search where full Datalog restrictions are too tight.

The limit is important: Datalog and Prolog do not perform causal inference by themselves. They recover candidate structure and constraints. Pearl-style causality enters when deciding which edges represent actual causal influence, what interventions are valid, and which counterfactuals are justified.

## Chain-Of-Thought Boundary

Chain-of-thought is a verbal reasoning trace. It can be useful as an interface, but it is not the same as a durable reasoning substrate.

Causal code intelligence should externalize the reasoning into artifacts that can be inspected without trusting the model's prose:

- facts extracted from code, traces, logs, and commits;
- queryable graphs;
- rules with explainable derivations;
- probabilistic rankings with assumptions;
- interventions or replay results;
- counterfactual claims marked by their evidence level.

The LLM can parse, hypothesize, translate, and explain. The durable intelligence belongs in the graph, rules, evidence, and interventions.

## Reverse Engineering Model Classes

Reverse engineering is model recovery under uncertainty. Useful model classes include:

- Structural models: modules, call graphs, dataflow, dependencies, ownership, schemas.
- Behavioral models: traces, state machines, protocols, input/output behavior, failure paths.
- Semantic models: invariants, contracts, preconditions, postconditions, domain rules.
- Architectural models: service boundaries, deployment topology, queues, shared resources.
- Domain models: business objects, workflow states, operational concepts.
- Operational models: load, latency, throughput, bottlenecks, retries, queues, resource contention.
- Evolutionary models: commits, migrations, feature flags, dependency versions, incident history.

## Tool Roles

- CodeQL and Datalog-like query systems: static code facts, reachability, security, and dataflow queries.
- Souffle and Doop: scalable Datalog-style program analysis.
- Joern and code property graphs: structural, semantic, and vulnerability-oriented code querying.
- Glean: large-scale code indexing and fact storage.
- Infer, CHC, SMT, and symbolic execution tools: feasibility and correctness checks.
- rr and time-travel debugging: replay-based causal testing.
- Whyline-style debugging: why and why-not questions over program behavior.
- Coz-style causal profiling: performance causality through controlled slowdown experiments.
- Lean or other proof assistants: formal proof/specification layer for claims that need high assurance.

The useful role split is:

- query engines discover suspicious paths;
- SMT or symbolic execution checks feasibility;
- runtime tracing shows what actually happened;
- causal profiling and replay test interventions;
- proof assistants verify abstract claims when proof is worth the cost.

## Queueing And Estimation Boundary

Queueing theory belongs in the operational model of a live system. Little's law, `L = lambda W`, can expose hidden work-in-system and bottlenecks from throughput and latency telemetry.

Factor graphs belong more naturally to probabilistic state estimation. They combine noisy measurements and constraints to infer latent state. That is useful for telemetry reconstruction or path fitting, but it is not Pearl-style causal intervention by itself. See `concepts/mathematical-programming-state-estimation.md`.

## Research Questions

- What are the right causal variables in software: functions, commits, configs, services, states, inputs, traces, tests, owners, or dependencies?
- How should static dependency edges be distinguished from causal influence edges?
- Which interventions are cheap, safe, and informative enough to run automatically?
- How can replay systems make counterfactual debugging more rigorous?
- How should uncertainty be represented when the code graph is known but runtime behavior is only partially observed?
- How can a system explain why a hypothesis was ranked highly without pretending it has proved causality?
- How should this connect to postmortems, incident review, and project planning?

## Practical Direction

The near-term version of this idea should not try to build a full causal reasoner immediately. It should start by building a retrieval and action system for debugging:

- collect failure evidence;
- extract structured code and incident facts;
- build queryable program and change graphs;
- derive suspicious paths with Datalog-style rules;
- rank hypotheses probabilistically;
- propose concrete interventions;
- record which interventions changed the outcome.

This needs a future practical project before the idea is trusted. The project should be small, instrumented, and built around known injected faults so the system can compare plain AI debugging against neuro-symbolic causal debugging with interventions.

The long-term goal is automatic root cause analysis that can say not only "this path is suspicious" but also "this is the causal claim, this is the evidence, this is the missing intervention, and this is the counterfactual we are or are not entitled to make."
