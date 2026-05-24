---
id: mathematical-programming-state-estimation
kind: concept
status: draft
source:
  - prior-chat: "mathematical programming solvers, GPS path fitting, odometry, and factor graphs discussion"
tags: [optimization, mathematical-programming, state-estimation, factor-graphs, gps, odometry]
depends_on: []
related: [causal-code-intelligence]
used_by: []
supersedes: []
---

# Mathematical Programming And State Estimation

This note captures the optimization and state-estimation side thread from the neuro-symbolic conversation.

## Solver Families

Mathematical programming solvers are usually grouped by problem form:

- Linear programming: HiGHS, GLPK, CLP, CPLEX, Gurobi.
- Mixed-integer programming: Gurobi, CPLEX, Xpress, SCIP, CBC, HiGHS.
- Quadratic and conic optimization: MOSEK, OSQP, SCS, ECOS, Clarabel.
- Nonlinear programming: Ipopt, KNITRO.
- Global nonlinear or mixed-integer nonlinear optimization: BARON, Couenne, Bonmin, SCIP.
- Constraint programming and integer optimization: OR-Tools CP-SAT, MiniZinc-backed solvers.
- Modeling layers: AMPL, JuMP, Pyomo, CVXPY, GAMS, MiniZinc.

The modeling layer is not the solver. It is the language used to express the problem.

## GPS Path Fitting

Noisy GPS path fitting can be read as:

```text
GPS observations are noisy samples from a latent path.
```

If a map is known, this is usually map matching:

- latent state: true position on a road or path graph;
- emission model: how close each GPS point is to a segment;
- transition model: how plausible movement is between segments;
- decoding: Viterbi or related shortest-likelihood path search.

If the map is unknown, manifold learning can help recover path structure from many traces:

- principal curves;
- graph principal curves or principal graphs;
- Isomap;
- diffusion maps;
- learned graph skeletons.

UMAP and t-SNE can visualize trajectory structure, but they are usually not enough for path fitting because the fitted object must support distance, projection, and valid transitions.

## Odometry

Odometry turns path fitting into state estimation and sensor fusion.

The measurements have complementary failure modes:

- GPS gives noisy absolute position and can jump.
- Odometry gives smooth relative motion and drifts over time.

The standard objective combines:

- GPS residuals;
- odometry residuals;
- heading and speed smoothness;
- map or manifold distance;
- hard or soft constraint violations.

## Factor Graphs

A factor graph represents a large estimation problem as many local constraints.

- Variables are unknown states, such as pose, velocity, heading, or sensor bias.
- Factors are measurements or constraints, such as GPS observations, odometry, speed limits, turn constraints, and road membership.

The solver finds the latent state trajectory that minimizes total error.

Useful libraries include:

- GTSAM;
- g2o;
- Ceres Solver;
- robot_localization in ROS;
- Theseus;
- PyPose;
- JAX-based differentiable optimization stacks.

## Boundary With Causal Inference

Factor graphs are graph-based, but they usually answer an estimation question:

```text
Given noisy measurements, what latent state best explains them?
```

Pearl-style causal inference answers a different question:

```text
What would happen under an intervention?
```

Both can be useful in debugging and reverse engineering. The distinction matters because a graph of dependencies is not automatically a graph of causal interventions.
