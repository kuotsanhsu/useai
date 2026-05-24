---
id: english-as-programming-interface
kind: concept
status: draft
source:
  - user-question: "What are the main counterpoints of Reddit to Dijkstra in the Harvard article?"
  - interpretation: "Treat Reddit as Reddi, the author of the Harvard article, unless later corrected."
  - source-note: "E. W. Dijkstra, On the foolishness of natural language programming"
  - source-note: "Jean E. Sammet, The Use of English as a Programming Language"
  - source-note: "Vijay Janapa Reddi, English Is a Programming Language"
  - source-note: "Frederick P. Brooks, No Silver Bullet"
  - source-note: "Peter Naur, Programming as Theory Building"
  - source-note: "C. A. R. Hoare, How Did Software Get So Reliable Without Proof?"
  - source-note: "Leslie Lamport, Letter to the Editor"
  - source-note: "Peng et al., The Impact of AI on Developer Productivity"
  - source-note: "METR, Measuring the Impact of Early-2025 AI on Experienced Open-Source Developer Productivity"
  - source-note: "Pearce et al., Asleep at the Keyboard"
  - source-note: "Martin Fowler, Microservice Premium and Monolith First"
  - source-note: "The debugging/programming bug joke is widely attributed to Dijkstra, but no primary source was found during this edit."
  - source-access-note: "The direct Harvard page was not retrievable during this edit; Reddi's public LinkedIn summary and visible discussion were used as accessible evidence."
  - source-access-note: "Detailed Hoare passages were checked through full-text mirrors when the canonical record exposed only metadata."
tags: [software-engineering, ai, natural-language-programming, dijkstra, english, specification, formal-methods]
depends_on: [programming-hyperreality]
related: [accidental-complexity-and-ceremony, attention-management, programming-hyperreality, code-simulacra-and-formal-shadows, soundness-validity-and-software-evidence]
used_by: [concepts/programming-hyperreality.md, concepts/glossary.md]
supersedes: []
---

# English As Programming Interface

This note records the Reddi counterpoint to Dijkstra. The user question said "Reddit", but the source context points to Vijay Janapa Reddi's Harvard post. This is therefore not yet a survey of Reddit comments. It is a prose version of the Reddi-versus-Dijkstra distinction.

Dijkstra's objection in [EWD667](https://www.cs.utexas.edu/~EWD/transcriptions/EWD06xx/EWD667.html) is not merely that English is ambiguous. His deeper claim is that formal notation is an intellectual interface. Formal symbols narrow the boundary between human and machine, make legitimate manipulation answerable to relatively simple rules, and force nonsense to become visible sooner. For Dijkstra, replacing formal symbolism with a native tongue does not remove the work of precision. It relocates that work into a wider, less disciplined interface where responsibility, semantics, and failure modes become harder to locate.

Reddi's counterpoint is not that Dijkstra was wrong about the danger. In his public summary of [English Is a Programming Language](https://vijay.seas.harvard.edu/blog/english-is-pl/), Reddi says the debate is old, that LLMs brought it back, and that the important question is no longer whether English can be a programming language. The important question is whether the foundations exist to make English-driven programming reliable. In that sense, Reddi's correction is historical and infrastructural rather than purely semantic.

The practical situation has changed. English is no longer only a proposed future interface that a language designer might accept or reject. It is already operational whenever prompts drive code generation, tool calls, migrations, deployments, agents, API orchestration, or workflow automation. A person can now cause real system effects by writing English, even if the durable artifact is still code, configuration, data, or an external side effect. The tax Dijkstra warned about did not disappear. It moved into models, platforms, reviewers, test harnesses, policies, logs, rollback systems, and humans who may not recognize that they are programming.

The strongest form of Reddi's counterpoint is this: Dijkstra framed natural-language programming as a bad interface to avoid; Reddi frames it as an infrastructure problem that now has to be engineered because avoidance no longer prevents use. Once English instructions can trigger executable effects, the question "is English really a programming language?" becomes less useful than "what should English-expressed intent compile into before it is allowed to act?"

This does not defeat Dijkstra. It preserves his deeper standard. English may be a useful top layer for intent, exploration, planning, requirements, review questions, and low-risk reversible action, but it is not sufficient bottom-layer semantics. Before consequential action, English should compile into a formal shadow: a plan, diff, type, invariant, test, policy, schema, causal graph, Datalog fact base, acceptance criterion, audit log, or rollback condition. Natural language can initiate the work, but the work becomes trustworthy only when it passes through artifacts that can be checked, replayed, constrained, and owned.

The visible public discussion around Reddi's post adds two useful pressures. One response emphasizes that modern systems have too many interacting conditions for a single contract or isolated test to cover every future failure. Another emphasizes that permissive English interfaces require stable, inspectable layers beneath them. These pressures pull in both directions: they affirm Dijkstra's fear that natural language hides unresolved precision, and they support Reddi's demand for infrastructure around English-driven action.

## Drudgery, Ambiguation, And No Silver Bullet

The local warning can be put this way: English appears to liberate the programmer from programming drudgery, but it can drag the work into ambiguation hell. The user no longer fights syntax, boilerplate, unfamiliar APIs, or mechanical edits. Instead the user may have to fight unstated assumptions, underspecified goals, overbroad interpretations, hidden context, non-reproducible generations, and plausible code whose meaning is not yet owned.

More sharply: English may multiply accidental complexity by replacing formal syntax with interpretive state. The work does not disappear; it returns as ambiguity management, prompt negotiation, clarification overhead, review burden, and ownership of underspecified generated artifacts. For the broader version of this point, including the parallel with dogmatic OOP, Kubernetes, and premature microservices, see [Accidental Complexity And Ceremony](accidental-complexity-and-ceremony.md).

That warning is one-sided unless it is balanced by the real value of removing accidental labor. The positive tradition is not new. Jean Sammet's 1966 CACM talk, [The Use of English as a Programming Language](https://cacm.acm.org/research/the-use-of-english-as-a-programming-language/), was explicitly a plea for using English or another natural language as a programming language. The desire is therefore not a shallow AI-age fantasy. It names a durable human-computer-interface wish: let users express the work closer to the language in which they already think about the domain.

Brooks's [No Silver Bullet](https://www.cs.unc.edu/techreports/86-020.pdf) gives the better frame. High-level languages really did free programmers from much accidental complexity, and English-driven AI can do something similar for boilerplate, search, glue code, translation, draft tests, and routine refactoring. A controlled experiment on [GitHub Copilot](https://arxiv.org/abs/2302.06590) found substantial speedup on a bounded programming task, so the productivity gain should not be dismissed as illusion.

The opposite overcorrection is also wrong. METR's [early-2025 RCT](https://metr.org/blog/2025-07-10-early-2025-ai-experienced-os-dev-study/) studied experienced developers working on mature open-source repositories they already knew well, and found slowdown rather than speedup in that setting. This does not refute the Copilot result; it localizes it. English-driven AI can be liberating for some tasks and a drag on others, especially where the essential difficulty is tacit repository knowledge, architectural judgment, long-horizon maintenance, or careful review.

Brooks's deeper warning is that eliminating accidental complexity does not eliminate essential complexity. The hard part remains the abstract conceptual structure: requirements, invariants, state spaces, interfaces, change, user fit, and the system's hidden interactions. English can make the accidental layer feel lighter while making the essential layer less explicit. That is the no-silver-bullet correction to the AI-age temptation.

Naur's [Programming as Theory Building](https://pages.cs.wisc.edu/~remzi/Naur.pdf) gives the positive role of English. Conversation, explanation, naming, examples, and narrative help programmers build the theory of the program. English is not merely a source of ambiguity; it is also one of the media in which understanding is formed and transferred. But the theory is not guaranteed by the existence of fluent text. A prompt transcript, generated patch, or plausible explanation can accompany theory building without proving that theory was actually built.

Security work on Copilot gives the operational caution. [Pearce et al.](https://arxiv.org/abs/2108.09293) studied generated code security and found that plausible code suggestions can still be unsafe. This supports the core position: English-driven code can reduce drudgery, but it shifts attention toward review, specification, security, tests, and formal shadows.

Dijkstra's verified source-backed claim is the stricter one from structured programming: testing can show the presence of bugs, not their absence. The joke that if debugging removes bugs then programming must put them in is widely attributed to Dijkstra, but this note treats that attribution as unverified until a primary source is found. The joke is still useful as a warning: every act of construction is also an opportunity to introduce new obligations for proof, testing, review, and later attention.

The proof side also needs balance. The local claim is not "English bad, proof good." A proof liberates attention only inside a well-stated formal frame. It lets a settled claim cool down because the remaining attention can move to assumptions, specifications, trusted implementation boundaries, and model-world fit. That is why proof can be an attention cache. But Hoare's [How Did Software Get So Reliable Without Proof?](https://ora.ox.ac.uk/objects/uuid%3Ae2c12b4d-cc50-439a-96d4-f9552a95f54f) is a standing warning against treating direct proof as the only route to reliability. Reliability also comes from specification discipline, review, assertions, testing, defensive margins, maintenance, and feedback from use.

Lamport's [Letter to the Editor](https://www.microsoft.com/en-us/research/publication/letter-to-the-editor/) gives the other side of that balance: criticism of naive program verification should not become permission to publish or ship algorithms without any correctness argument. The practical position is therefore layered. Use English to discover, communicate, and revise intent. Use tests and experiments to keep the formal frame in contact with reality. Use proofs, types, model checking, static analysis, and other formal shadows when the cost of leaving a universal claim as live doubt is too high.

The resulting stance is practical rather than purist. English is an interface for intent, not a replacement for formal semantics. It can make programming more accessible and expressive, but it also expands the population of people who can accidentally program. The danger is programming hyperreality: fluent English can look like intent, a generated plan can look like semantics, and a successful demo can look like infrastructure. The discipline is to treat English prompts as executable intent that must be grounded in formal shadows and reality contact before they become consequential action.
