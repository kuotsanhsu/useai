---
id: error-handling-and-fault-tolerance
kind: concept
status: draft
source:
  - user-request: "Elaborate Hoare's error handling as deliberate over-engineering and compare it with Joe Armstrong's Erlang let it crash philosophy."
  - source-note: "C. A. R. Hoare, How Did Software Get So Reliable Without Proof?"
  - source-access-note: "Detailed Hoare passages were checked through full-text mirrors when the canonical record exposed only metadata."
  - source-note: "Joe Armstrong, Making Reliable Distributed Systems in the Presence of Software Errors"
  - source-note: "Erlang/OTP Design Principles"
  - source-note: "Eliezer Yudkowsky, Irretrievability; or, Murphy's Curse of Oneshotness upon ASI"
tags: [software-engineering, fault-tolerance, error-handling, erlang, hoare, armstrong, irretrievability]
depends_on: [programming-hyperreality]
related: [programming-hyperreality, causal-code-intelligence, neuro-symbolic-ai]
used_by: [concepts/programming-hyperreality.md]
supersedes: []
---

# Error Handling And Fault Tolerance

This note compares Hoare's account of error handling as deliberate over-engineering with Joe Armstrong's Erlang philosophy of letting isolated processes crash under supervision.

## Hoare's Deliberate Over-Engineering

In [How Did Software Get So Reliable Without Proof?](https://ora.ox.ac.uk/objects/uuid%3Ae2c12b4d-cc50-439a-96d4-f9552a95f54f), Hoare treats defensive programming as one form of deliberate over-engineering. The term is not praise for arbitrary complexity. It names extra structure that may be redundant in a perfectly reasoned system but useful in real systems built under incomplete proof, changing requirements, human error, unreliable environments, and partial observability.

His examples include:

- checking an exceptional case again even when the programmer believes another component has already ruled it out;
- guarding distributed communication with timeouts;
- dynamically checking incoming messages for plausibility;
- ignoring suspicious messages when the sender is expected to have its own timeout protection;
- auditing global system tables and reinitializing suspicious entries to safe values;
- using rapid warm restart to restore a recent valid state after software, hardware, or operator faults.

The basic idea is: do not rely on the ideal proof obligation having been discharged elsewhere. In theory, a caller or earlier layer may have established the precondition. In practice, a later layer may still check because boundaries leak, assumptions drift, requirements change, and the cost of one extra guard may be lower than the cost of diagnosing the rare escaped fault.

This is why Hoare's over-engineering is close to the engineering idea of a safety factor. The extra code is a margin against unknowns. But Hoare also warns that over-engineering has a cost: redundant error-handling code increases volume, maintenance burden, testing burden, and may itself contribute to the failures it was meant to prevent.

## Armstrong's Let It Crash

In [Making Reliable Distributed Systems in the Presence of Software Errors](https://erlang.org/download/armstrong_thesis_2003.pdf), Armstrong gives Erlang a different default. Erlang processes are isolated, cheap to create, communicate by message passing, and can be linked so failures become visible to other processes. The Erlang/OTP design principles describe supervision trees as workers doing the work and supervisors monitoring and restarting workers when something goes wrong.

The slogan "let it crash" does not mean "ignore errors." It means:

- if a process reaches a state where it cannot correctly continue, fail early;
- keep ordinary worker logic simple instead of burying every worker in defensive recovery code;
- propagate failure information to linked processes;
- let a supervisor restart the worker, restart a group, degrade to a simpler task, or fail upward;
- preserve enough failure information in logs to improve the system later.

Armstrong's key move is non-local error handling. The process doing the work is not always the right place to repair the failure. A separate supervisor may have a clearer view of restart policy, dependency relationships, escalation, and system-level recovery.

## Irretrievability And Oneshotness

Eliezer Yudkowsky's [Irretrievability; or, Murphy's Curse of Oneshotness upon ASI](https://www.lesswrong.com/posts/fbrz9xhKpEeTKw5zL/irretrievability-or-murphy-s-curse-of-oneshotness-upon-asi) adds a third axis: whether recovery remains possible after a serious mistake.

The useful engineering import does not require accepting every ASI-risk claim in the post. The reusable point is that some projects are globally one-shot even when they contain many locally recoverable steps. A large system can let you retry small operations while still denying a second try after the wrong global failure.

The post's recurring examples point to several failure modes:

- a corrective mechanism can be damaged by the failure it was meant to recover from;
- testing and simulation may not match deployment conditions;
- previous experience may be drawn from a non-identical distribution;
- a slow or continuous process can still outrun the controller's ability to correct;
- local recoverability does not imply global retrievability.

This makes irretrievability different from both Hoare-style defensive programming and Erlang-style supervision. Hoare asks, "What redundant checks should remain even if another layer should have handled this?" Armstrong asks, "What should crash and who should restart it?" Irretrievability asks, "Will we still have observation, control, rollback, and another attempt after the failure?"

## The Real Comparison

Hoare, Armstrong, and the irretrievability frame share a premise: large software systems fail in ways that proof, tests, and local programmer intention do not fully eliminate. They differ in where they place the recovery margin.

Hoare's style often adds local or boundary checks. It asks each component to distrust its environment enough to protect itself and the rest of the system. It is strongest at untrusted inputs, external dependencies, global tables, distributed messages, and systems where ignoring, sanitizing, retrying, or reinitializing can preserve service.

Erlang's style moves much of the margin into system structure. It asks workers to do the work or fail, then relies on isolation, links, supervisors, restart strategies, and simpler fallback tasks. It is strongest when work can be isolated into restartable processes and when state can be reconstructed, externalized, or safely abandoned.

The irretrievability frame moves the margin into project structure and consequence analysis. It asks whether the larger effort remains controllable if the local recovery machinery fails. It is strongest for migrations, launches, deployments, security incidents, safety-critical control, irreversible data operations, and any action where failure can destroy the evidence, state, authority, budget, reputation, or control channel needed for another try.

The conflict is therefore not:

- defensive programming versus no error handling.

The better distinction is:

- local defense inside the worker;
- boundary defense at trust and protocol edges;
- non-local recovery by supervisors;
- retrievability analysis at the project and system boundary;
- formal prevention where the invariant is too important to recover from after the fact.

## Practical Rule

Use local error handling when the condition is expected, recoverable, and part of the domain contract. Examples: invalid user input, unavailable resource, business-rule rejection, parse failure, retryable network timeout, or an API call that should return a useful diagnostic.

Use Erlang-style crash and supervision when the worker state is corrupted, the invariant has been violated, or the worker does not know how to continue safely. The recovery policy should live at a level that understands dependencies, restart scope, state reconstruction, and service degradation.

Use Hoare-style redundant defense at boundaries where assumptions cross trust, process, machine, organization, or time. Examples: external messages, global state, persisted data, migrations, background jobs, and any interface where the caller's correctness cannot be assumed.

Use irretrievability analysis before high-consequence action. Ask whether the failure would preserve observation, rollback, authority, control channels, and another acceptable attempt. If not, reduce scope, stage the rollout, add independent recovery channels, rehearse on realistic environments, require review, or refuse automation until the action is made retrievable enough.

Use formal methods, types, model checks, transactions, or proof obligations when the system cannot tolerate the failure after it occurs. In those cases, "let it crash" may be too late and redundant defensive checks may be too weak.

## AI Workflow Implication

For AI-assisted programming, both philosophies warn against a common failure:

- filling code with superficial error-handling branches that nobody can justify;
- or letting agents take destructive actions without isolation, rollback, supervision, and logs.

The irretrievability frame adds a stricter warning: do not confuse many small retry loops with a retrievable overall action. An AI agent may retry tool calls, regenerate code, and repair tests while still performing a globally one-shot operation such as deleting data, rewriting history, sending an irreversible message, migrating production state, or changing an access boundary.

The useful synthesis is to separate business logic from recovery logic and to classify the action's retrievability before execution. Let ordinary code stay clear where possible, but put explicit supervisors around model calls, tool execution, migrations, file writes, external APIs, and production actions. Before consequential action, decide the containment unit, the restart or rollback rule, the log that survives failure, the independent recovery channel, and the invariant that must not be violated.
