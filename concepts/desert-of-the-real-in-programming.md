---
id: desert-of-the-real-in-programming
kind: concept
status: draft
source:
  - user-request: "Fact check and elaborate the Desert of the Real in programming, compilers, and handwritten assembly examples."
  - source-note: "Jean Baudrillard, Simulacra and Simulation"
  - source-note: "E. W. Dijkstra, Why is software so expensive?"
  - source-note: "C. A. R. Hoare, How Did Software Get So Reliable Without Proof?"
  - source-access-note: "Detailed Hoare passages were checked through full-text mirrors when the canonical record exposed only metadata."
  - source-note: "Leslie Lamport, Why We Should Build Software Like We Build Houses"
  - source-note: "IBM, Fortran history"
  - source-note: "GMP manual"
  - source-note: "FFmpeg developer documentation"
  - source-note: "VideoLAN dav1d project page and Jean-Baptiste Kempf dav1d assembly note"
tags: [software-engineering, ai, programming-hyperreality, assembly, compilers, optimization, dijkstra, hoare, lamport]
depends_on: [programming-hyperreality]
related: [code-simulacra-and-formal-shadows, programming-hyperreality, error-handling-and-fault-tolerance]
used_by: [concepts/programming-hyperreality.md, concepts/glossary.md]
supersedes: []
---

# Desert Of The Real In Programming

This note develops a local adaptation of Baudrillard's "desert of the real" for programming.

## Local Meaning

The desert of the real in programming would not be "AI writes some code" or "high-level tools remove some drudgery." It would be the total denunciation of writing code as a mode of understanding, design, and contact with the machine.

The danger is a stance like:

- writing code is only clerical translation;
- source code is just an intermediate artifact to be automated away;
- understanding lower layers is obsolete because a tool can generate them;
- executable output matters, but the act of writing, reading, deriving, and repairing code does not.

That stance cuts against Dijkstra, Hoare, and Lamport in different but related ways.

- [Dijkstra](https://www.cs.utexas.edu/~EWD/transcriptions/EWD06xx/EWD648.html) treats code as the deposit of understanding and argues that programmers must produce trustworthy solutions supported by convincing arguments, not merely text that runs.
- [Hoare](https://ora.ox.ac.uk/objects/uuid%3Ae2c12b4d-cc50-439a-96d4-f9552a95f54f) treats specification, review, assertions, preconditions, postconditions, invariants, tests, and mathematical reasoning as ways to make design and code intelligible to an engineering process.
- [Lamport](https://lamport.azurewebsites.net/pubs/wired.pdf) argues that writing specifications is part of thinking clearly before coding, and that code is a poor medium for understanding code.

The local warning is: if programming becomes only generated artifact management, then the "real" of programming has been evacuated. The real is not raw machine code by itself. The real is the disciplined relation among intention, notation, execution, evidence, performance, repair, and understanding.

## Fact Check: Compilers And Assembly

The claim "compilers made understanding assembly obsolete" is too strong. The better claim is:

- Compilers and high-level languages made assembly non-default for most programming.
- They did not make assembly knowledge obsolete for all work.
- Assembly survived where the abstraction boundary still leaks: compilers, runtimes, kernels, embedded systems, reverse engineering, debugging, calling conventions, vectorization, cryptography, codecs, big-number arithmetic, and performance-critical inner loops.

Fortran is the right historical anchor. [IBM describes](https://www.ibm.com/history/fortran) early programming as machine-language work done by specialists and presents Fortran as a major abstraction that increased productivity, lowered costs, and separated software from the exact machine. IBM also notes that the first Fortran compiler was optimizing and produced code nearly as fast as handcrafted numerical code.

So the first "desert" was not that assembly vanished. It was that routine contact with assembly stopped being necessary for ordinary programming. That was a genuine liberation, but also a genuine loss of routine contact with the machine.

## Fact Check: GMP, FFmpeg, dav1d

[GMP](https://gmplib.org/manual/Assembly-Coding.html) supports the point strongly, with a limited scope. The GMP manual says the speed of GMP comes partly from carefully optimized assembly for common inner loops across many CPUs. Its assembly-coding section says assembly subroutines are the most significant source of speed at small to moderate sizes, that carry handling and widening multiplies are hard to express in C, and that hand-coded low-level routines can beat generic C by factors from 2 to 10.

[FFmpeg](https://ffmpeg.org/developer.html#Optimization) also supports the point strongly, again with a limited scope. The FFmpeg developer documentation says FFmpeg is mainly C, but for SIMD and DSP work modern compilers cannot generate efficient code from plain C, so handwritten assembly is used. FFmpeg also makes the engineering discipline explicit: keep a plain C implementation, use architecture-specific optimized functions, dispatch at runtime, and test assembly with `checkasm`.

[dav1d](https://images.videolan.org/projects/dav1d.html) supports the point especially well as a modern case. VideoLAN describes dav1d as an AV1 decoder focused on speed, size, and correctness, and invites contributions in C or ASM. [Jean-Baptiste Kempf's 2021 dav1d note](https://jbkempf.com/blog/2021/dav1d-0.9.1-a-ton-of-asm/) says the project had about 140000 lines of assembly at the time, calls it large for handwritten assembly, and says the code is faster than what compilers generate by themselves. [A later 2023 note](https://jbkempf.com/blog/2023/dav1d-1.2.0/) counted more than 200000 lines of assembly for dav1d 1.2.0, so the point strengthened rather than disappeared.

The careful conclusion:

- These projects do not prove that humans generally beat compilers.
- They prove that expert humans can beat compilers in narrow, well-understood, performance-critical kernels.
- They also prove that this only works inside an engineering system: C fallbacks, tests, runtime dispatch, maintainers, review, benchmarks, architecture-specific knowledge, and a willingness to pay maintenance cost.

## Why Humans Sometimes Beat The Compiler

The reason is not mystical superiority over automation. It is that the human expert may know something the compiler is not allowed to assume or cannot conveniently infer.

Examples:

- the exact mathematical operation being implemented;
- the acceptable data ranges;
- the target CPU family and its SIMD instructions;
- cache and register pressure tradeoffs;
- carry propagation strategy;
- alignment and layout constraints;
- the surrounding call pattern;
- which branch of portability can be sacrificed in a specialized implementation;
- which correctness tests and benchmarks will catch mistakes.

The compiler optimizes a program under the language semantics and target model it is given. A maintainer writing assembly can change the representation, split a generic kernel into specialized kernels, exploit a CPU-specific instruction sequence, or encode domain knowledge that is not present in the C source.

This is a narrow and expensive victory. It is not a reason to write everything in assembly. It is evidence that writing code remains a form of thinking when the human knows what must happen more precisely than the abstraction can express.

## AI-Age Analogy

The compiler analogy is useful for AI, but it must be handled carefully.

High-level languages did not destroy programming. They moved the main work upward. The best programmers stopped writing routine assembly, but they still needed to understand algorithms, data structures, interfaces, invariants, failure modes, and sometimes machine behavior.

AI may do something similar for ordinary code. It may make much routine code non-default as a handwritten activity. But the assembly exception warns against a total denunciation of writing code:

- some code is where thinking happens;
- some low-level details are where reality pushes back;
- some performance and correctness problems only become visible by writing, reading, measuring, and repairing the artifact directly;
- some generated code will need a human who understands exactly what should have been generated.

The local rule:

- Let tools remove routine translation.
- Do not let tools remove the practices that produce understanding.
- When the abstraction fails, be willing to descend into the lower layer.
- Treat handwritten low-level code as justified only when the proof of need, benchmark, correctness tests, and maintenance path are explicit.

## Relation To Programming Hyperreality

Programming hyperreality appears when the generated artifact, benchmark score, type signature, test suite, or AI explanation becomes more convincing than actual understanding.

The desert of the real is the more severe stance: it says there is no need to preserve the human practice of writing as a way of thinking at all.

The counterexample from assembly is important because history already tested a weaker version of that stance. Compilers made routine assembly unnecessary, but the projects with the strongest need for performance and control still keep handwritten assembly where the abstraction is not good enough.

The same pattern should be expected with AI-assisted programming. The point is not nostalgia for manual code. The point is disciplined reversibility: the higher-level tool is good only if someone can still descend, inspect, reason, and repair when reality demands it.
