# PHOTONIC QEC RESEARCH IDEATION — MODEL HANDOFF PROTOCOL

## 1. Your role

You are one iteration in a multi-model research ideation process.

Your job is to identify, investigate, criticize, refine, and propose computational quantum research projects at the intersection of **photonic quantum computing, quantum error correction, and quantum simulation/software frameworks**.

The student intends to use the resulting project for:

1. a highly competitive high-school science fair project, and
2. potentially a serious research paper suitable for submission to a strong peer-reviewed journal if the results justify it.

Do not lower the scientific standard because the researcher is a high-school student. The project should be scoped so that a motivated student can realistically execute a substantial computational version of it, but the **research question itself should be legitimate research rather than a student demonstration**.

The ideal outcome is a project that could plausibly interest researchers working in photonic quantum computing or quantum error correction.

---

# 2. Primary software/framework constraint

The researcher specifically wants ideas that obtain scientific value by connecting **two or more simulation/computational frameworks that operate at different abstraction levels**.

Frameworks of particular interest include:

- **Strawberry Fields**
- **PennyLane**
- **Stim**
- **PyMatching**
- **Qiskit**

Other libraries may be proposed if they materially improve the scientific project.

A strong project might use a division such as:

### Strawberry Fields
Microscopic or physical photonic simulation:

- Fock states
- photon loss
- multimode optical effects
- beamsplitters/interferometers
- finite detector efficiency
- photon-number-resolving measurements
- Gaussian/CV processes
- temporal/spectral effects when appropriately modeled

### Stim
Large-scale stabilizer/QEC simulation:

- stabilizer circuits
- repeated syndrome extraction
- detector events
- logical observables
- detector error models
- high-volume Monte Carlo sampling

### PyMatching
Decoding:

- minimum-weight perfect matching
- logical-error estimation
- syndrome processing
- weighted decoding

### PennyLane
Optimization/differentiation:

- physical-parameter optimization
- variational optimization
- differentiable components
- surrogate objectives
- hybrid classical/quantum optimization

Do NOT force every framework into every project.

The important criterion is that **each framework performs a scientifically necessary role that the other framework cannot conveniently perform**.

A project such as:

> “simulate something in Strawberry Fields and then simulate something else in Qiskit”

is not sufficient.

The coupling between simulators must itself enable a new scientific question.

---

# 3. Central idea-generation principle

The most promising direction discovered so far is to exploit the **abstraction gap between realistic photonic physics and scalable quantum-error-correction simulation**.

For example:

$$
\text{physical photonic device}
\rightarrow
\text{measurement statistics / physical faults}
\rightarrow
\text{effective QEC noise}
\rightarrow
\text{logical failure rate}.
$$

Strawberry Fields can model physical optical effects that Stim cannot.

Stim can simulate QEC systems at scales that Strawberry Fields cannot.

PennyLane can potentially optimize physical parameters using downstream performance objectives.

Therefore, useful research questions may exist specifically at the interface

$$
\boxed{
\text{microscopic photonic physics}
\leftrightarrow
\text{logical QEC behavior}
}
$$

rather than purely inside either field.

This is a direction to investigate, NOT a requirement that every proposed project use exactly this structure.

You should search broadly for other similarly powerful simulator interfaces.

---

# 4. Required quality criteria for every proposed project

Every serious candidate must pass all of the following tests.

## A. Scientifically meaningful problem

The project must answer a real research question.

Avoid projects whose main contribution is:

- creating software infrastructure,
- reproducing known simulations,
- connecting APIs,
- benchmarking software packages,
- visualizing known results,
- implementing a known paper without a new question.

Software may be a major output, but it should exist to answer a scientific question.

---

## B. Plausible novelty

You MUST search the current literature before claiming that an idea is novel.

Search:

- recent journal papers,
- arXiv,
- conference papers when relevant,
- research-group publications,
- documentation only when necessary to understand software capabilities.

Pay particular attention to approximately **2023–present**, while checking older foundational work as necessary.

For every candidate, determine:

1. What has already been done?
2. What is the nearest existing paper?
3. Exactly how is the proposed project different?
4. Is that difference scientifically meaningful?
5. Could the difference support a standalone paper?

Never claim “nobody has done this” merely because an exact search phrase returns nothing.

---

## C. Important enough to matter

Ask:

> If the hypothesis is confirmed, what changes?

Strong outcomes include:

- identifying an important previously ignored failure mechanism,
- changing how experiments should be operated,
- changing how photonic QEC should be simulated,
- discovering a new physical/QEC tradeoff,
- improving logical error rates under equal resources,
- showing that an accepted approximation fails in an important regime,
- developing a transferable design principle,
- enabling a capability researchers currently lack.

A narrow numerical observation with little consequence is not enough.

---

## D. Publication depth

A project should support several layers of analysis.

Prefer projects with:

- a clear baseline,
- multiple physical regimes,
- code-distance scaling,
- parameter sweeps,
- robustness tests,
- comparison with accepted approximations,
- theoretical interpretation,
- sensitivity studies,
- reproducible computational methods.

A project that produces one graph is usually too small.

---

## E. Executability

The project must be computationally feasible without requiring fabrication of quantum hardware.

It may use realistic experimental parameters from literature.

Avoid ideas requiring:

- proprietary experimental data,
- access to actual quantum-photonic hardware,
- enormous HPC resources beyond reasonable academic/cloud access,
- solving a completely open mathematical problem before simulations can begin.

The student can handle substantial Python simulation and research software.

---

## F. Simulator integration must be fundamental

The project should ideally require capabilities from two different abstraction levels.

A good example is:

$$
\text{Strawberry Fields}
\rightarrow
\text{physical event distribution}
\rightarrow
\text{Stim}
\rightarrow
P_L.
$$

A weaker example is simply independently running two simulators and comparing them.

---

## G. Science-fair suitability

Even though publication quality is the goal, the research should produce a comprehensible experimental narrative:

$$
\text{problem}
\rightarrow
\text{hypothesis}
\rightarrow
\text{method}
\rightarrow
\text{simulation}
\rightarrow
\text{result}
\rightarrow
\text{physical interpretation}.
$$

There should be measurable independent and dependent variables.

The final project should be explainable to technically sophisticated judges without requiring them to understand an entire software ecosystem.

---

# 5. What NOT to propose without a genuinely new angle

Previous investigation suggests that several broad areas are already crowded.

Do not simply propose:

- generic optimization of fusion gates,
- “make FBQC more loss tolerant,”
- generic biased-noise QEC,
- generic decoder-aware hardware optimization,
- arbitrary asymmetric redundancy allocation,
- generic optimization of photonic architecture parameters,
- “use machine learning to improve QEC,”
- basic soft decoding,
- basic analog-information decoding,
- generic photonic source optimization,
- generic hardware/software co-design.

These areas are not forbidden.

However, if you revisit one of them, identify a **precise unresolved question** that survives literature review.

---

# 6. Existing research history

Do not discard this section in future handoffs.

Every model should preserve it and append its own conclusions.

## Historical Direction A — Decoder-aware photonic source/component allocation

Concept:

Allocate higher-quality sources, detectors, couplers, or other hardware nonuniformly according to logical sensitivity.

General objective:

$$
\min P_L
$$

subject to a hardware/resource budget.

Potential variables included:

- source brightness,
- detector efficiency,
- source quality,
- fusion resources,
- location-dependent component quality.

### Assessment

Interesting co-design concept, but increasingly appeared too close to existing hardware/QEC optimization and resource-allocation ideas.

It did not appear sufficiently differentiated for the desired research standard without a substantially stronger physical mechanism.

### Status

**Not a current candidate. Preserve for historical context only.**

---

## Historical Direction B — Differentiable asymmetric photonic QEC architecture discovery

Concept:

Allow redundancy to vary spatially:

$$
\min_{\{r_i\}}P_L
$$

subject to

$$
\sum_i r_i\leq N_{\max}.
$$

Possible optimization variables:

- tree depth,
- redundant photons,
- fusion redundancy,
- ancilla allocation,
- bridge protection,
- graph structure.

Hypothesis:

Logical sensitivity might demand deliberately asymmetric photonic architectures.

### Assessment

Potentially interesting, but too close to ongoing work in:

- optimized fusion-based quantum computing,
- tailored loss-tolerant architectures,
- resource-aware photonic QEC,
- biased/asymmetric QEC design.

The project also risked becoming generic numerical architecture optimization rather than revealing a sufficiently important new physical principle.

### Status

**Rejected as current primary direction. Preserve in handoff history.**

---

## Historical Direction C — Analog-information CV–DV decoding

Concept:

Retain continuous measurement outcomes

$$
x_i
$$

instead of immediately thresholding them into binary syndromes.

Map them to probabilities

$$
P(E_i\mid x_i)
$$

and use those as soft decoder information.

For matching, for example:

$$
w_i
\sim
-\log\frac{p_i}{1-p_i}.
$$

### Assessment

Further literature review showed that soft/analog information in GKP/CV-DV decoding already has substantial precedent.

In particular, modern photonic architectures already use raw homodyne information to derive downstream error probabilities.

A more specialized resource-aware analog-decoding project was considered, involving precision/calibration/communication costs, but it did not remain compelling enough relative to other directions.

### Status

**Not a current candidate.**

---

## Historical Direction D — Correlated photon-loss bursts

Concept:

Compare QEC performance under independent photon loss with spatially or temporally correlated photon-loss bursts at the same marginal loss probability.

Possible work included:

- burst-aware routing,
- syndrome scheduling,
- correlation-aware decoding,
- physical layout interleaving.

### Assessment

This generated potentially interesting questions, but it drifted toward designing QEC around a prescribed correlation model rather than exploiting the photonic simulators in a uniquely necessary way.

Unless a highly realistic physical mechanism and simulator coupling produces a new angle, do not revive it as a generic correlated-noise project.

### Status

**Not a current candidate. Preserve historically.**

---

# 7. Most recent three-project research program

A later ideation round produced three linked directions.

Originally:

1. hidden errors from multiphoton emission + photon loss,
2. QEC-optimized temporal filtering,
3. physical photonic noise compiler.

Further research and criticism changed their status.

---

## Idea 1 — Hidden errors from multiphoton emission + loss

### Original concept

A nominal single-photon source occasionally emits more than one photon:

$$
|1\rangle\rightarrow |2\rangle.
$$

Photon-number-resolving detection might normally reveal this.

But with photon loss:

$$
|2\rangle
\rightarrow
|1\rangle
$$

before detection.

A detector could then observe an apparently valid single-photon event.

Thus two imperfections that are separately detectable may combine to create an **unheralded hidden fault**.

The proposed simulation stack was:

$$
(g^{(2)},\eta,V,\eta_{\rm det},\ldots)
$$

$$
\downarrow
$$

Strawberry Fields physical simulation

$$
\downarrow
$$

conditional physical-event / detector-pattern statistics

$$
\downarrow
$$

effective QEC faults

$$
\downarrow
$$

Stim/PyMatching

$$
\downarrow
$$

logical error rate $$P_L$$.

### Later assessment

The effect is physically legitimate, and literature explicitly notes that multiphoton-emission-plus-loss effects can be neglected in simplified models.

However, as a **standalone flagship project**, it was judged too narrow.

A likely result such as

> “simplified erasure models underestimate logical error by X% in this parameter range”

might be publishable but does not necessarily solve a sufficiently broad problem.

### Current status

**Not a standalone project.**

Retain it as a possible **validation case for Idea 3**, particularly because it introduces higher-Fock-state physics that a scalable stabilizer simulator cannot represent directly.

---

## Idea 2 — QEC-optimized temporal filtering

### Original concept

Photon distinguishability caused by temporal/spectral mismatch reduces interference quality.

Time-resolved detection or temporal postselection can improve accepted-event fidelity.

However, narrower acceptance windows also reject more events.

This creates a tradeoff:

$$
\text{unheralded distinguishability error}
\leftrightarrow
\text{heralded erasure}.
$$

Since quantum error correction can often tolerate known erasures much more effectively than unknown errors, the physically optimal temporal filter need not be the logically optimal temporal filter.

Instead of maximizing HOM visibility or optical fidelity, optimize

$$
\min_{\Delta t} P_L(\Delta t).
$$

Possible pipeline:

$$
\text{temporal/spectral mismatch + jitter}
$$

$$
\xrightarrow{\text{physical optical simulation}}
P(\text{measurement outcomes},t_1,t_2,\ldots)
$$

$$
\xrightarrow{\text{filtering/decision rule}}
p_{\rm erasure}, p_{\rm hidden}, p_{\rm correlated},\ldots
$$

$$
\xrightarrow{\text{Stim/PyMatching}}
P_L.
$$

PennyLane or another optimizer could optimize either:

- a temporal cutoff,
- detector decision boundaries,
- more general time-dependent acceptance policies.

### Later assessment

This was initially considered independently strong because it connects an experimentally adjustable physical parameter directly to logical QEC performance.

However, subsequent research was considered sufficient to **remove it from the current main-project list**.

Do not simply revive this exact idea.

A future model may reconsider it only if it identifies a materially new unresolved question not covered by the literature review.

### Current status

**Not a current candidate.**

Preserve it because components of the physical-to-QEC mapping remain relevant to Idea 3.

---

# 8. CURRENT ACTIVE PROJECT — Idea 3: Physical Photonic Noise Compiler

THIS IS THE ONE EXISTING IDEA THAT REMAINS ACTIVE.

Do not treat it as rejected unless your own literature research provides strong evidence that the central contribution already exists.

## Core problem

Detailed photonic simulators and large-scale QEC simulators operate at fundamentally different abstraction levels.

A physical photonic device may have:

- vacuum components,
- multiphoton states,
- finite $$g^{(2)}$$,
- photon loss,
- mode mismatch,
- partial distinguishability,
- detector inefficiency,
- PNR detector behavior,
- dark counts,
- beamsplitter imbalance,
- phase errors,
- spectral effects,
- temporal effects,
- correlated measurement outcomes.

Strawberry Fields can model many such microscopic effects.

Stim, however, operates on stabilizer-level noise:

- Pauli faults,
- erasures when represented appropriately,
- detector events,
- correlated detector-error mechanisms,
- logical observables.

Stim cannot directly propagate arbitrary Fock-space optical states through a massive fault-tolerant computation.

Conversely, Strawberry Fields cannot realistically simulate millions of full-QEC trials for large codes using full Fock-space state representations.

Therefore there is an important translation problem:

$$
\boxed{
\text{realistic physical photonic noise}
}
$$

$$
\downarrow
$$

$$
\boxed{
\text{effective scalable QEC noise model}
}
$$

---

## What “noise compilation” means

The term does NOT merely mean adding noise channels to Strawberry Fields.

The proposed compiler would take physical device parameters such as

$$
\theta_{\rm phys}
=
\{
\eta,
g^{(2)},
V,
\eta_{\rm detector},
\phi,
R_{\rm BS},
\ldots
\}
$$

simulate a small physical photonic primitive, and determine the probability distribution over physically meaningful outcomes.

It would then infer or construct the QEC-level consequences.

Conceptually:

$$
\theta_{\rm phys}
$$

$$
\downarrow
$$

Strawberry Fields

$$
\downarrow
$$

$$
P(\text{physical optical outcome})
$$

$$
\downarrow
$$

classification/inference of resulting QEC faults

$$
\downarrow
$$

$$
P(
\text{detector flips},
\text{erasures},
\text{Pauli faults},
\text{correlated faults},
\text{logical effects}
)
$$

$$
\downarrow
$$

Stim detector error model / effective stabilizer noise model.

The compiler then enables large-scale simulation:

$$
\text{small accurate optical calculation}
\rightarrow
\text{large approximate QEC calculation}.
$$

---

## Why this matters

Many photonic fault-tolerance calculations must simplify hardware noise into idealized channels such as:

$$
p_{\rm loss},
\quad
p_X,
\quad
p_Z.
$$

But physical optical mechanisms may generate:

- conditional errors,
- non-independent faults,
- correlated detector patterns,
- hidden faults,
- state-dependent faults,
- noise structures that are not well captured by independent Pauli/erasure assumptions.

The scientific question is therefore not merely:

> Can software translate one format into another?

It is:

> **When, how, and with what accuracy can realistic microscopic photonic noise be reduced to scalable QEC noise models without losing the logical consequences that matter for fault tolerance?**

Important possible research outputs include:

### 1. Approximation validity

Determine regions where

$$
P_L^{\rm simplified}
\approx
P_L^{\rm physically\ compiled}
$$

and regions where

$$
P_L^{\rm simplified}
\neq
P_L^{\rm physically\ compiled}.
$$

### 2. Required correlation order

Determine whether:

- independent Pauli channels,
- pairwise correlated faults,
- higher-order detector hyperedges,
- conditional fault models,

are required to reproduce the physical simulation.

### 3. Compression

Determine how much physical information can be discarded while retaining accurate logical behavior.

For example:

$$
\text{full physical model}
\rightarrow
\text{compressed DEM}
$$

with bounded error in predicted $$P_L.$$

### 4. Transferability

Determine whether a compiled primitive remains accurate when embedded into:

- different code distances,
- repeated rounds,
- different photonic architectures,
- different decoders.

### 5. Optimization

Potentially use PennyLane or classical optimization around the compiler:

$$
\theta^*
=
\arg\min_\theta
P_L\left[
C(\theta)
\right],
$$

where $$C$$ denotes physical-noise compilation.

This would allow optimization of hardware parameters directly for logical performance.

---

## Important caution about Idea 3

Do NOT assume that “Strawberry Fields → Stim noise compiler” is automatically novel.

Search aggressively for related work involving:

- detector error model learning,
- effective noise model extraction,
- channel reduction,
- photonic fault-model derivation,
- microscopic-to-stabilizer noise mapping,
- coherent-noise detector models,
- model reduction for QEC,
- photonic fusion noise modeling,
- physical-device-informed decoding.

The contribution must be more specific than:

> “We created a Python interface between Strawberry Fields and Stim.”

That alone would not meet the project standard.

The strongest formulation is likely centered on the scientific problem of **faithfully reducing complex photonic noise into scalable QEC models and quantifying when conventional approximations fail.**

### Current status

**ONGOING / ACTIVE.**

Any new ideas generated should be compared against this project rather than automatically replacing it.

---

# 9. What you must do in this iteration

Perform a fresh ideation and literature-search cycle.

## Step 1 — Critically evaluate the active compiler project

Research the closest literature to Idea 3.

Determine:

- whether the central idea already exists,
- what parts already exist,
- what parts remain genuinely open,
- whether it is strong enough for the publication/science-fair goal,
- what specific formulation would maximize novelty and importance.

Do not eliminate it from the handoff even if you think it is weak.

Instead assign an assessment such as:

- Very strong
- Strong
- Promising but needs reframing
- Weak
- Likely already done

and explain why.

---

## Step 2 — Generate several genuinely new ideas

Generate approximately **3–7 strong candidate projects**.

Prefer quality over quantity.

Search beyond obvious keywords.

Potential seams to investigate include, but are not limited to:

- realistic photonic noise that scalable QEC papers approximate,
- physical measurement information discarded before decoding,
- coherent optical effects converted into QEC faults,
- photonic hardware parameters that affect logical errors nontrivially,
- physically derived correlated noise,
- mismatch between optical fidelity objectives and logical-QEC objectives,
- non-Pauli photonic errors,
- leakage-like photonic behavior,
- temporal/spectral multimode physics,
- bosonic-to-qubit interfaces,
- measurement-induced faults,
- fault-model compression,
- decoder mismatch caused by physical noise assumptions,
- physical mechanisms producing syndrome correlations,
- differentiable optimization across simulator boundaries,
- experimental control parameters that can trade one QEC error class for another.

Do not limit yourself to these categories.

A substantially different simulator pairing is acceptable if scientifically justified.

---

# 10. Required analysis for every new idea

For every proposed project provide:

## Title

A concise research-project title.

## Core research question

One sentence.

## Physical mechanism

Explain what actually happens physically.

## Why two simulators are required

Explicitly assign a role to each framework.

For example:

$$
\text{Strawberry Fields}
\rightarrow
\text{microscopic physics}
$$

$$
\text{Stim}
\rightarrow
\text{logical-scale QEC}.
$$

## Novelty boundary

Identify the closest existing research.

Explain exactly what would be new.

## Why it matters

Explain what researchers could learn or change if the result succeeds.

## Minimum viable experiment

Describe the smallest simulation that could test whether the idea has merit.

## Full paper path

Explain how the MVP could become a paper:

- scaling,
- robustness,
- parameter sweeps,
- comparison baselines,
- theoretical model,
- additional physical mechanisms.

## Main risks

For example:

- already published,
- effect too small,
- simulator cannot model required physics,
- computational cost,
- mapping to QEC ambiguous,
- no useful experimental regime.

## Kill criterion

State what early result would justify abandoning the idea.

## Evaluation

Score approximately from 1–10 on:

- novelty,
- importance,
- feasibility,
- simulator-integration strength,
- publication potential,
- science-fair clarity.

Do not inflate these scores.

---

# 11. Comparison requirement

At the end, rank:

- the ongoing physical-noise compiler,
- all new ideas generated in this iteration,
- any historical idea you believe deserves reconsideration.

Explain which project you would pursue if only **one** could be completed.

Then identify whether any ideas naturally combine into a broader research program.

Do not merge ideas merely because they share software.

They should share a scientific question or infrastructure.

---

# 12. Critical reasoning rules

You are explicitly encouraged to tell the researcher that an idea is bad.

Do not preserve an idea's ranking merely because a previous model liked it.

However:

$$
\boxed{\textbf{Never delete previous ideas from the handoff.}}
$$

Even if an idea is:

- already published,
- weak,
- unimportant,
- technically infeasible,
- too broad,
- too narrow,

retain it in the historical section and append your assessment.

This is important because later models need to understand what has already been investigated and why it was rejected.

Do not allow the brainstorming process to cycle back into already-rejected ideas under slightly different wording.

---

# 13. Handoff-generation requirement

At the END of your work, produce a complete updated handoff document for the next model.

The handoff must be **self-contained**.

Assume the next model has seen NONE of the previous conversation.

Every handoff must preserve:

1. the science-fair objective,
2. the publication objective,
3. the simulator-integration requirement,
4. the novelty criteria,
5. the feasibility criteria,
6. all historical ideas,
7. each idea's current status,
8. reasons ideas were rejected,
9. the complete status of the ongoing physical-noise compiler,
10. the ideas generated during your iteration,
11. literature findings relevant to those ideas,
12. your criticism of previous ideas,
13. your ranking,
14. unresolved questions,
15. recommended next investigations.

When receiving a handoff from a previous model:

- preserve its contents,
- fact-check important claims,
- critically evaluate its proposed ideas,
- append your own research,
- update statuses where justified,
- NEVER silently remove rejected ideas.

Think of the handoff as a cumulative research notebook.

---

# 14. Status vocabulary

Use consistent labels:

**ACTIVE**  
Currently being seriously considered or developed.

**PROMISING**  
Strong enough to investigate further.

**NEEDS LITERATURE VALIDATION**  
Interesting but insufficiently checked.

**FALLBACK**  
Usable if stronger projects fail.

**VALIDATION CASE**  
Useful as an experiment within another project but not necessarily a standalone paper.

**REJECTED — TOO CLOSE TO PRIOR WORK**

**REJECTED — TOO NARROW**

**REJECTED — INSUFFICIENT IMPORTANCE**

**REJECTED — TECHNICALLY INFEASIBLE**

**REJECTED — WEAK SIMULATOR INTEGRATION**

Do not use “rejected” to mean erased from history.

---

# 15. Current research-state summary

At the beginning of this iteration, the state is:

### ACTIVE

**Physical Photonic Noise Compiler: Strawberry Fields → scalable QEC model → Stim/PyMatching**

Central question:

$$
\boxed{
\text{How can microscopic photonic noise be reduced into scalable QEC fault models while preserving the logical behavior relevant to fault tolerance?}
}
$$

### VALIDATION CASE

**Multiphoton emission + photon loss producing hidden faults**

Potentially useful for testing whether the compiler captures higher-Fock-state physical mechanisms missed by simple erasure models.

Not considered strong enough as the main standalone project.

### HISTORICAL / NO LONGER CURRENT

**QEC-optimized temporal filtering**

Previously considered a strong standalone project involving:

$$$$
\text{unheralded distinguishability}
\leftrightarrow
\text{heralded erasure}.
$$$$

Subsequent research was considered sufficient to stop treating it as a current project.

Preserve the idea but do not simply re-propose it.

### OTHER HISTORICAL DIRECTIONS

- asymmetric photonic QEC redundancy discovery,
- decoder-aware source/component allocation,
- analog-information CV–DV decoding,
- correlated photon-loss burst mitigation,
- generic differentiable photonic/QEC co-design.

These should not be resurfaced without a genuinely new mechanism or research question.

---

# 16. Ultimate standard

The target is not merely:

> “This is impressive for a high-school student.”

The desired standard is:

> “This asks a legitimate unanswered question in quantum photonics/QEC, uses the simulator combination for a scientifically necessary reason, produces falsifiable computational results, and could become a credible research paper if executed rigorously.”

Generate ideas accordingly.

---

# 17. New literature and criticism from this iteration

## Scope and confidence

This is a targeted literature pass, not a claim of exhaustive systematic review. The search emphasized 2023--2025 work and checked foundational software papers and documentation where needed. The date matters: software capabilities and preprints can change quickly, and a final paper proposal must repeat the search immediately before starting the project.

Relevant anchors found during this pass include:

- Stim and PyMatching remain a standard scalable workflow for stabilizer sampling, detector error models, and matching-based decoding. The relevant scientific limitation is not the existence of this workflow; it is whether a physically derived model is sufficient for the logical question.
- Sparse Blossom made large matching simulations practical: Oscar Higgott, "Sparse Blossom: correcting a million errors per second," arXiv:2303.15933, https://arxiv.org/abs/2303.15933.
- Hardware-specific and correlated-noise decoding is an active area. For example, decoding-graph reweighting for drifted/correlated noise was studied in arXiv:2311.16214, https://arxiv.org/abs/2311.16214. This makes "learn a better decoder from data" a weak novelty claim by itself.
- Recent photonic work continues to study tailored fusion-based schemes and realistic loss/distinguishability tradeoffs. A useful recent anchor is "Tailoring Fusion-Based Photonic Quantum Computing Schemes to Quantum Hardware," PRX Quantum 6, 020304 (2025), https://link.aps.org/doi/10.1103/PRXQuantum.6.020304.
- Integrated photonic demonstrations already show that photonic error correction and fault-tolerant measurement primitives are experimentally meaningful, not merely hypothetical: "Encoding Error Correction in an Integrated Photonic Chip," PRX Quantum 4, 030340 (2023), https://journals.aps.org/prxquantum/pdf/10.1103/PRXQuantum.4.030340.
- Leakage is recognized as a distinct QEC problem rather than an ordinary Pauli channel. A representative recent reference is "Overcoming leakage in quantum error correction," Nature Physics (2023), https://www.nature.com/articles/s41567-023-02226-w.
- Bosonic QEC tooling is expanding. IBM's Bosonic Qiskit overview is useful for mapping the neighboring landscape, but it is not evidence that a particular photonic-to-Stim compiler has already been solved: https://www.ibm.com/quantum/blog/bosonic-error-correction.
- Quantum error cancellation for photonic loss (arXiv:2403.05252) shows that loss and non-Gaussian optical effects remain active topics, but it addresses mitigation rather than the proposed logical-model reduction: https://arxiv.org/abs/2403.05252.

### Consequence for the active compiler

The broad statement "build a Strawberry Fields to Stim interface" is not a publishable research question. Device-informed detector models, correlated decoding, and automated DEM generation are already active. The defensible question is narrower:

> For a specified photonic primitive and code family, what is the smallest effective fault model that preserves the logical observables of the full microscopic simulation within a measured error tolerance, and in which physical regimes do standard independent-erasure or Pauli approximations fail?

This turns software plumbing into a falsifiable model-reduction study. The novelty boundary is the measured sufficiency/error tradeoff, especially for higher-Fock-number events, hidden faults, and context-dependent correlations that cannot be represented by a single marginal loss rate.

### Assessment of Idea 3

**Strong if reframed; weak if presented as an API project.** The active compiler has high simulator-integration strength and a clear science-fair story. Its main risk is that a full Fock-space-to-stabilizer mapping is not unique: the same optical outcome can correspond to different logical faults depending on encoding, circuit location, feed-forward rule, and decoder. The project must therefore define one primitive, one code family, one fault-injection convention, and one error metric before making broad claims.

The most important deliverable should be a Pareto curve:

$$
\text{model complexity}
\quad\longleftrightarrow\quad
\left|P_L^{\rm full}-P_L^{\rm reduced}\right|.
$$

That curve is scientifically more valuable than a large software package.

---

# 18. New candidate projects

The candidates below are intentionally narrower than the original brainstorming directions. Scores are provisional, on a 1--10 scale, and are not claims of guaranteed novelty.

## Candidate A - Sufficiency maps for photonic noise compilation

**Status: PROMISING; recommended primary project**

### Core research question

How many correlation orders and physical outcome classes are required for a reduced QEC noise model to reproduce the logical failure behavior of a microscopic photonic primitive?

### Physical mechanism

Finite source quality, photon loss, detector inefficiency, multiphoton emission, and partial distinguishability produce a joint distribution over optical outcomes. Marginalizing that distribution too aggressively can turn hidden or correlated faults into apparently independent erasures.

### Why two simulators are required

- **Strawberry Fields:** generate Fock-space outcome statistics for a small, physically specified source/fusion/measurement primitive.
- **Stim:** embed candidate effective faults into repeated syndrome-extraction circuits at several code distances and rounds.
- **PyMatching:** compare a baseline independent decoder with decoders using the compiled weights/correlations.

The scientific result is the reduction error, not the software connection.

### Novelty boundary

DEM generation and hardware-aware decoding already exist. A new contribution would be an experimentally interpretable *sufficiency map*: independent, pairwise, or higher-order models are compared against the same microscopic source, and the boundary is reported in terms of physical parameters and logical-error tolerance. This is different from merely fitting a decoder to syndrome data.

### Why it matters

It tells researchers when a simple loss/Pauli model is safe, when it is dangerously optimistic, and how much microscopic information must be retained to make a logical prediction.

### Minimum viable experiment

Choose one fusion-like two-mode primitive. Sweep transmission, second-order source correlation, distinguishability, and detector efficiency. Compile:

1. independent erasure model,
2. erasure plus measurement-flip model,
3. pair-correlated detector-error model,
4. a reference model sampled directly from the microscopic conditional distribution.

Run each through Stim/PyMatching for distances 3, 5, and 7 and at least two rounds. Report logical failure and confidence intervals.

### Full paper path

Add code distance and round scaling, source/detector calibration uncertainty, architecture placement, decoder mismatch, higher-order hyperedges, and a held-out physical parameter regime. Derive a simple perturbative explanation for the first regime in which each additional correlation order becomes necessary.

### Main risks

The optical primitive may not map cleanly to a stabilizer fault without an explicit encoding convention. Higher-order correlations may be too rare to estimate. Stim cannot represent arbitrary coherent bosonic evolution; the compiler must state exactly where a stochastic measurement-level approximation is made.

### Kill criterion

Abandon or radically narrow the project if, after fixing the primitive and calibration range, an independent model stays within the predefined tolerance (for example, 1% relative logical-error error) across all relevant distances and physical parameters.

### Evaluation

| Criterion | Score |
|---|---:|
| Novelty | 8 |
| Importance | 8 |
| Feasibility | 8 |
| Simulator integration | 10 |
| Publication potential | 8 |
| Science-fair clarity | 9 |

---

## Candidate B - Hidden-fault phase diagram for multiphoton emission and loss

**Status: VALIDATION CASE; not recommended as a standalone paper**

### Core research question

When does multiphoton emission followed by loss create enough unheralded fault probability that an erasure-only photonic QEC model becomes logically misleading?

### Physical mechanism

A two-photon event can lose one photon and produce the same detector record as a valid one-photon event. The event is no longer a flagged erasure even though its origin was a source fault.

### Why two simulators are required

- **Strawberry Fields:** retain Fock sectors above one photon and calculate conditional detector records.
- **Stim/PyMatching:** test whether the hidden events behave like measurement flips, correlated faults, or another effective mechanism at logical scale.

### Novelty boundary

Multiphoton emission and loss are known physical concerns. The potentially new part is a quantitative *logical phase diagram* showing when the usual erasure-only abstraction changes decoder ranking or code-distance scaling. This must be checked directly against papers that already include imperfect sources.

### Why it matters

It could identify a calibration regime in which improving source brightness or loss alone gives a false impression of QEC progress because hidden events dominate.

### Minimum viable experiment

Use a low-dimensional source model with vacuum, one-photon, and two-photon components. Match the marginal detected click rate across an erasure-only and a multiphoton-plus-loss model, then compare logical failure under identical Stim circuits.

### Full paper path

Add detector number resolution, dark counts, source models beyond the two-photon sector, code distance, decoder mismatch, and a resource comparison between improving transmission and improving source purity.

### Main risks

The effect may be a small correction in realistic operating regimes, or already be fully quantified in the nearest photonic QEC architecture paper. A simplistic mapping could also confuse a source event with a particular Pauli fault.

### Kill criterion

Drop it as a standalone project if the difference is below statistical uncertainty or if a careful literature search finds the same phase diagram and conclusion.

### Evaluation

| Criterion | Score |
|---|---:|
| Novelty | 5 |
| Importance | 6 |
| Feasibility | 9 |
| Simulator integration | 9 |
| Publication potential | 5 |
| Science-fair clarity | 9 |

---

## Candidate C - Multimode distinguishability as correlated syndrome noise

**Status: PROMISING; needs literature validation**

### Core research question

Does tracing over unobserved spectral or temporal modes create nonlocal correlations in photonic syndrome data that are invisible to a scalar visibility parameter but relevant to logical decoding?

### Physical mechanism

Partial distinguishability changes multi-photon interference amplitudes. If modes are not resolved by the detector, which-path information is effectively traced out. Several outcomes can therefore be correlated even when the marginal fusion-success probability is unchanged.

### Why two simulators are required

- **Strawberry Fields:** model a small multimode interferometer, mode overlap, loss, and detector coarse-graining.
- **Stim/PyMatching:** propagate the resulting detector-event distribution through repeated QEC rounds and compare a visibility-only model with a correlation-aware model.

### Novelty boundary

The literature already studies distinguishability and fusion thresholds, and temporal filtering itself is historical and not to be revived unchanged. The new boundary is testing whether *the same marginal visibility* can hide different correlation structures with different logical consequences, rather than optimizing a time window.

### Why it matters

Experimental characterization often compresses mode mismatch into one visibility number. If that number is not sufficient for logical prediction, calibration and decoder design need additional observables.

### Minimum viable experiment

Construct two microscopic mode-overlap models with matched HOM visibility and matched single-event rates but different spectral-mode mixtures. Compare their detector-event covariance and logical error for a small repeated syndrome circuit.

### Full paper path

Sweep Schmidt-mode number, mode-dependent loss, detector resolution, code distance, round count, and decoder knowledge. Identify a minimal set of optical calibration statistics that predicts logical performance.

### Main risks

The chosen Strawberry Fields backend may not represent the required multimode detector process cleanly. The correlations may disappear after the actual syndrome extraction. The premise may overlap with existing distinguishability analyses.

### Kill criterion

Abandon if matched-visibility models produce indistinguishable logical behavior across all tested distances or if the effect depends on an unphysical detector assumption.

### Evaluation

| Criterion | Score |
|---|---:|
| Novelty | 7 |
| Importance | 7 |
| Feasibility | 6 |
| Simulator integration | 9 |
| Publication potential | 7 |
| Science-fair clarity | 7 |

---

## Candidate D - Detector dead time and crosstalk as non-Markovian QEC noise

**Status: PROMISING; needs a carefully bounded physical model**

### Core research question

Can detector dead time and crosstalk change the logical-error scaling of a photonic QEC schedule even when the average detector efficiency is held fixed?

### Physical mechanism

A detection event can suppress a nearby or subsequent detection, while crosstalk can create an extra click conditional on another click. The resulting errors depend on event order, detector history, and spatial adjacency rather than only on independent per-measurement probabilities.

### Why two simulators are required

- **Strawberry Fields or a custom optical measurement layer:** generate physically timed click records from an optical primitive and detector model.
- **Stim:** represent the resulting time- and location-dependent measurement faults in a repeated stabilizer circuit.
- **PyMatching:** test whether a decoder using only average efficiency is systematically misweighted.

### Novelty boundary

Detector imperfections are known, and generic detector noise simulations are not novel. The new question is whether equal average efficiency can conceal different history-dependent logical behavior and whether schedule changes, rather than hardware upgrades, can mitigate it.

### Why it matters

It connects a controllable experimental parameter (timing and detector spacing) to QEC scheduling and calibration requirements.

### Minimum viable experiment

Use a two-detector toy primitive with a dead-time window and one crosstalk probability. Match average click efficiency across an independent model and a history-dependent model. Feed both into a small repeated Stim circuit and compare logical failure and decoder calibration.

### Full paper path

Add realistic timing distributions, detector multiplexing, dark counts, schedule optimization, distance scaling, and a decoder with/without history features. Report whether the advantage comes from physical mitigation or simply better modeling.

### Main risks

Stim's standard circuit model is not inherently a detector-history simulator. A custom sampler-to-detector-event bridge is required. The effect may be architecture-specific and not transferable.

### Kill criterion

Drop if a memoryless model with matched conditional detector probabilities reproduces logical results, or if no realistic dead-time/crosstalk regime changes decoder conclusions.

### Evaluation

| Criterion | Score |
|---|---:|
| Novelty | 7 |
| Importance | 7 |
| Feasibility | 7 |
| Simulator integration | 8 |
| Publication potential | 6 |
| Science-fair clarity | 8 |

---

## Candidate E - Leakage-aware reduction at a photonic-to-qubit interface

**Status: PROMISING; high risk**

### Core research question

When photonic population leaves the intended qubit/code subspace, is an erasure flag sufficient, or does leakage persist and create multi-round logical faults that require an explicit leakage-reduction model?

### Physical mechanism

Higher photon-number sectors, failed measurements, and imperfect state preparation can leave population outside the nominal computational subspace. A later operation may convert that population into a wrong click rather than a clean erasure.

### Why two simulators are required

- **Strawberry Fields:** track the vacuum and higher-Fock sectors through preparation, interference, loss, and measurement.
- **Stim:** evaluate candidate abstractions: immediate erasure, leakage with reset, leakage without reset, and leakage-to-measurement-flip.
- **PyMatching:** quantify decoder performance under each abstraction.

### Novelty boundary

Leakage-aware QEC is an established topic, so "photonic leakage exists" is not new. A possible contribution is a device-specific reduction showing which leakage abstraction is sufficient for a chosen photonic measurement primitive and how the answer changes with reset timing.

### Why it matters

It prevents a common modeling error: treating every out-of-subspace event as a benign flagged loss when it can persist into later rounds.

### Minimum viable experiment

Choose one photonic qubit encoding and one reset convention. Simulate one leakage-producing primitive and compare the four effective models at distances 3--7.

### Full paper path

Include several reset schedules, source and detector imperfections, leakage lifetime, decoder knowledge, and comparison to a leakage-reduction circuit. Establish a transfer criterion for the reduced model.

### Main risks

The mapping from Fock population to a discrete leakage state is encoding-dependent. The project could duplicate established leakage-QEC work without a photonic-specific insight.

### Kill criterion

Do not pursue if the selected encoding has a directly available validated leakage model that already answers the chosen question, or if all models are logically equivalent in the tested regime.

### Evaluation

| Criterion | Score |
|---|---:|
| Novelty | 6 |
| Importance | 8 |
| Feasibility | 5 |
| Simulator integration | 9 |
| Publication potential | 7 |
| Science-fair clarity | 7 |

---

# 19. Comparison and ranking

| Rank | Project | Status | Main strength | Main weakness |
|---:|---|---|---|---|
| 1 | Sufficiency maps for photonic noise compilation | PROMISING | Directly answers the abstraction-gap question and supports a rigorous error/compression result | Requires a precise physical-to-fault convention |
| 2 | Multimode distinguishability as correlated syndrome noise | PROMISING; needs validation | Tests whether a standard optical summary statistic is logically sufficient | Multimode detector modeling may be difficult |
| 3 | Detector dead time and crosstalk | PROMISING; bounded model needed | Experimentally interpretable and schedule-relevant | History-dependent noise is awkward to encode in Stim |
| 4 | Leakage-aware photonic-to-qubit reduction | PROMISING; high risk | Important logical failure mode with strong QEC relevance | Encoding-specific and close to established leakage literature |
| 5 | Multiphoton emission plus loss phase diagram | VALIDATION CASE | Clean MVP and excellent educational narrative | Too narrow unless a genuinely new regime is found |
| 6 | Existing historical temporal-filtering idea | HISTORICAL / do not revive unchanged | Clear physical tradeoff | Already sufficiently explored for this process |
| 7 | Existing allocation, asymmetric architecture, analog-decoding, burst, and generic co-design ideas | HISTORICAL | Useful background and possible components | Rejected or crowded without a new mechanism |

## Single-project recommendation

Choose **Candidate A**, the sufficiency-map version of the Physical Photonic Noise Compiler.

The first paper claim should not be "we built a compiler." It should be:

> A specified class of microscopic photonic mechanisms requires correlation information beyond the conventional independent-erasure model, and we quantify the minimum reduced model needed to predict logical performance.

This claim is falsifiable, scales naturally from a science-fair MVP to a paper, and uses each simulator for a necessary reason. Candidate B should be the first validation case because it tests a concrete higher-Fock mechanism. Candidate C should be the first expansion only if the MVP shows that correlation order matters.

## Natural research program

Candidates A, B, C, and E can form one coherent program only if they share the same model-reduction metric:

$$
\mathcal{E}
=
\left|P_L^{\rm microscopic}-P_L^{\rm reduced}\right|
$$

under matched physical calibration and a stated code/decoder family.

The program would progress from:

1. higher-Fock hidden faults (B),
2. correlation-order sufficiency (A),
3. multimode correlations (C),
4. leakage persistence and reset conventions (E).

Candidate D is related infrastructure but should remain separate unless detector history becomes the central mechanism. Do not merge projects merely because they import the same Python packages.

---

# 20. Concrete execution plan for the recommended project

## Phase 0 - Freeze definitions before coding

Select one photonic primitive, one qubit/measurement convention, one code family, one decoder, and one primary metric. Define whether a "fault" means an optical event, a detector event, or a logical observable flip. Publish the mapping convention in the methods before sweeping parameters.

## Phase 1 - Validate the microscopic primitive

Reproduce limiting cases: perfect source, zero loss, perfect detection, and deliberately injected loss. Check photon-number cutoff convergence and sampling uncertainty. Do not use a reduced model until these checks pass.

## Phase 2 - Construct nested reductions

Build independent-erasure, independent-Pauli/measurement, pair-correlated, and higher-order candidate models. Keep a held-out parameter set that is never used to fit model probabilities.

## Phase 3 - Compare at logical scale

For each reduction, run matched Stim circuits at multiple distances and rounds. Use PyMatching with both correctly informed and deliberately mismatched weights. Report logical failure, decoder failure, confidence intervals, runtime, and model size.

## Phase 4 - Identify the boundary

Find the smallest physical parameter region where each simpler abstraction violates the predefined error tolerance. Explain the transition with conditional probabilities or a low-order expansion rather than only plotting it.

## Phase 5 - Robustness and reproducibility

Repeat with detector efficiency, source statistics, and calibration uncertainty varied independently. Fix random seeds for examples, use independent seeds for confidence intervals, and release the primitive specification, model files, and scripts.

## Recommended early-stop tests

Stop the project before a large sweep if any of the following is true:

- photon-number cutoff changes the reference result materially and cannot be controlled;
- the optical-to-QEC mapping is not operationally defined;
- the full and reduced models agree within the tolerance everywhere;
- the only difference appears at probabilities too small to estimate with available compute;
- a newly found paper already reports the same physical regime, reduction metric, and conclusion.

---

# 21. Unresolved literature questions for the next model

1. Has a paper already quantified a microscopic photonic-to-DEM reduction error using the same logical-observable metric, rather than merely deriving a phenomenological noise channel?
2. Which fusion-based or cluster-state architecture gives the cleanest operational definition of an optical primitive and detector event?
3. Can a Strawberry Fields backend represent the required multimode, finite-efficiency, and number-resolving measurement model without an uncontrolled truncation?
4. What correlation structures can Stim's detector error model represent directly, and when must a custom sampler or a decomposition approximation be used?
5. Which experimentally reported source, detector, and indistinguishability ranges make the predicted discrepancy observable with feasible Monte Carlo effort?
6. Can a code-distance scaling result be made meaningful when the physical primitive is only locally simulated?
7. Is "logical error within epsilon" the right sufficiency metric, or should the study also compare decoder ranking, threshold estimate, and observable-specific distributions?
8. Should PennyLane be used at all? It is justified only if differentiable optimization is part of the scientific question; it should not be added for framework-counting.

The next handoff should answer these questions with primary papers, not search snippets, and should update every status rather than silently replacing this document.

# 22. Fresh critical iteration — 2023-present literature and project reset (2026-09-07)

## 22.1 Evidence rule and scope

This is a fresh, targeted literature pass, not an exhaustive systematic review. I separate statements supported by a primary paper or an official implementation specification from hypotheses that still require an experiment. A citation below supports the narrow result described; it does **not** establish that the proposed project is novel. Novelty remains uncertain until the exact primitive, encoding, decoder, metric, and parameter regime are searched together.

The most relevant primary sources checked in this pass are:

- Bartolucci et al., "Fusion-based quantum computation," *Nature Communications* 14, 912 (2023), https://doi.org/10.1038/s41467-023-36493-1. This establishes the FBQC resource-state/fusion framework, not a microscopic optical noise compiler.
- Sahay, Claes, and Puri, "Tailoring Fusion-Based Error Correction for High Thresholds to Biased Fusion Failures," *Physical Review Letters* 131, 120604 (2023), https://doi.org/10.1103/PhysRevLett.131.120604. This shows that fusion-basis bias and architecture-specific decoding materially affect thresholds.
- Zhang et al., "Encoding Error Correction in an Integrated Photonic Chip," *PRX Quantum* 4, 030340 (2023), https://doi.org/10.1103/PRXQuantum.4.030340. This is an experimental error-correction demonstration, but it is not a general microscopic-to-logical reduction.
- Yard et al., "On-Chip Quantum Information Processing with Distinguishable Photons," *Physical Review Letters* 132, 150602 (2024), https://doi.org/10.1103/PhysRevLett.132.150602. Time-resolved detection increased interference visibility for detuned photons; the paper does not establish the logical sufficiency of visibility for QEC.
- Aqua and Dayan, "Temporal quantum eraser: Fusion gates with distinguishable photons," *Physical Review A* 110, 043709 (2024), https://doi.org/10.1103/PhysRevA.110.043709. This supports a physical route for mitigating temporal distinguishability, not a decoder-level theorem.
- Taylor et al., "Quantum error cancellation in photonic systems - undoing photon losses," *Physical Review A* 110, 022622 (2024), https://doi.org/10.1103/PhysRevA.110.022622. This is loss mitigation, not fault-tolerant QEC or a DEM compiler.
- Chan et al., "Tailoring fusion-based photonic quantum computing schemes to quantum emitters," *PRX Quantum* 6, 020304 (2025), https://doi.org/10.1103/PRXQuantum.6.020304. This directly studies emitter-relevant loss, distinguishability, encoded fusions, and thresholds using an architecture-level model.
- Meng et al., "Temporal fusion of entangled resource states from a quantum emitter," *Nature Communications* 16, 7602 (2025), https://doi.org/10.1038/s41467-025-62130-0. This experimentally demonstrates time-like fusion and makes timing, source memory, and delay loss concrete hardware variables.
- Pettersson et al., "Deterministic Generation of Concatenated Graph Codes from Quantum Emitters," *PRX Quantum* 6, 010305 (2025), https://doi.org/10.1103/PRXQuantum.6.010305. This reinforces that source construction and resource overhead are part of the logical architecture, not an interchangeable noise parameter.
- Derks et al., "Designing fault-tolerant circuits using detector error models," arXiv:2407.13826 (2024), https://arxiv.org/abs/2407.13826. This explains what DEMs capture at circuit, schedule, and gadget levels.
- Zhou et al., "Learning to decode logical circuits," arXiv:2504.16999 (2025), https://arxiv.org/abs/2504.16999, and the drift/correlation study arXiv:2311.16214 (2023), https://arxiv.org/abs/2311.16214. These show that correlated and history-dependent decoding is an active problem outside photonics too.

For software behavior, the Stim DEM specification is the authoritative description of independent error mechanisms, multi-detector targets, and suggested decompositions: https://github.com/quantumlib/Stim/blob/main/doc/file_format_dem_detector_error_model.md. The PyMatching 2 documentation states its normal MWPM assumption explicitly: independent, graphlike mechanisms, with `decompose_errors=True` commonly used before loading a Stim DEM: https://pymatching.readthedocs.io/en/latest/. These are implementation specifications, not evidence that a photonic compiler has already been solved.

## 22.2 What the recent literature actually establishes

1. **FBQC is no longer just an abstract loss-only proposal.** The 2023 FBQC paper, the 2023 biased-fusion paper, the 2025 emitter-tailoring paper, and the 2025 temporal-fusion experiment establish a meaningful architecture in which resource-state preparation, fusion outcome bias, loss, distinguishability, timing, and feed-forward interact. **Literature-supported consequence:** a useful reduction must name an architecture and primitive; a universal photonic noise compiler is not justified.

2. **Architecture-level threshold papers use compressed physical parameters.** Chan et al. model loss and distinguishability in an encoded-fusion analysis and obtain useful thresholds. That is strong evidence that reduced models can be scientifically useful. It is not evidence that a scalar distinguishability or loss parameter preserves every detector correlation generated by a microscopic optical model. The latter is a hypothesis to test.

3. **Temporal resolution changes the physical statistics.** Yard et al. experimentally increased interference visibility by resolving detection times, and Aqua and Dayan analyze erasure of temporal distinguishability in fusion gates. Meng et al. demonstrate temporal fusion with a real emitter and delay line. **Literature-supported:** detector timing and source history can matter before the QEC layer. **Not established:** that two devices matched in average visibility and fusion-success probability have identical logical error rates.

4. **Photonic QEC has experimental demonstrations, but not a generic microscopic-to-logical bridge.** Zhang et al. demonstrate error correction on an integrated photonic chip. Taylor et al. study probabilistic loss cancellation. Neither paper supplies the exact Fock/mode/detector-record-to-DEM transfer requested here. This is a gap worth checking, not a novelty claim.

5. **Leakage is a distinct QEC concern, but a photonic leakage variable is encoding-dependent.** The 2023 leakage literature establishes that leakage can persist and correlate later faults in QEC. A vacuum, multiphoton, failed-fusion, or wrong-rail event is not automatically the same leakage process. **Hypothesis:** for a selected dual-rail primitive, a small latent state plus reset convention may outperform an erasure-only abstraction.

6. **Stim can express more than pairwise edges, but PyMatching's usual fast path cannot use arbitrary mechanisms exactly.** A DEM `error(p)` may target several detectors and observables, and separators can suggest a graphlike decomposition. The DEM is still a list of independently sampled mechanisms. PyMatching's standard matching graph requires one or two detection events per mechanism; decomposition changes the effective inference problem unless the factorization is valid. Therefore the previous wording "Stim cannot represent arbitrary correlated errors" was wrong, while the warning about exact graphlike decoding was directionally right.

7. **History is not impossible, but it is not native continuous-time detector physics.** A finite-state detector history can be encoded by extra circuit state, by a custom sampler, or by time-dependent graph weights. The practical limitation is that Stim/PyMatching will not infer dead time, afterpulsing, mode memory, or source memory from an optical record automatically. This makes a history-aware bridge a possible research tool, not a reason to claim that Stim is incapable of the task.

## 22.3 Fact-check and criticism of the previous iteration

| Previous claim or proposal | Verdict | Correction for this iteration |
|---|---|---|
| "Strawberry Fields to Stim compiler" is the active project. | Too software-centric. | Keep the project active only as a calibrated model-reduction benchmark with a specified primitive and logical metric. An API alone is not a contribution. |
| Stim cannot represent arbitrary correlated or higher-order detector events. | Inaccurate. | Stim DEM syntax can contain multi-detector mechanisms and suggested decompositions. The hard limit is exact scalable inference and the graphlike assumptions of the usual PyMatching path. |
| PyMatching ignores correlations. | Overbroad. | Standard MWPM assumes independent graphlike mechanisms; correlated mechanisms can be decomposed or handled with custom graph constructions, but this can be approximate or decoder-specific. Test the decomposition error instead of asserting impossibility. |
| Matched visibility may hide logically different multimode noise. | Plausible hypothesis, not a result. | Require two explicit mode density matrices with matched measured marginals and a held-out logical comparison. Do not call this an established effect. |
| Multiphoton emission plus loss creates hidden faults. | Mechanistically plausible, not universal. | Whether it is hidden depends on encoding, detector number resolution, feed-forward, and the chosen fault convention. Treat it as a validation case, not a theorem. |
| Detector dead time/crosstalk is a photonic QEC result. | Not established by the cited literature. | It is a synthetic stress test until detector parameters and a photonic fusion schedule are justified by a primary source. |
| Leakage-aware reduction is automatically photonic. | Too strong. | Define leakage operationally for one encoding and one reset rule. Higher Fock number, vacuum, and detector ambiguity must not be conflated. |
| Candidate A deserved novelty 8/10. | Optimistic. | Hardware-aware decoding, DEM design, and photonic fusion threshold studies narrow the novelty. The defensible novelty is a measured sufficiency/error frontier, so novelty is 6-7/10 until a targeted search is negative. |

## 22.4 Updated assessment of the active compiler

**Status: ACTIVE, but renamed "calibration-conditioned photonic model-reduction benchmark."**

The project should not promise an exact map

`arbitrary bosonic dynamics -> universal Stim circuit`.

That map is not unique: the same optical record can correspond to different logical faults under different encodings, feed-forward rules, detector resolutions, and code schedules. The testable object is instead

`physical parameters -> optical record r -> detector/history record h -> syndrome/observable sample -> reduced model M`.

For one named fusion primitive and one named logical circuit, compare a family of reductions `M` against the microscopic reference. The primary result is a Pareto frontier between model complexity and held-out error in logical observables, not the existence of a software interface.

The revised compiler assessment is:

- **Supported by literature:** reduced architecture-level noise models are useful; FBQC thresholds depend on loss, fusion bias, distinguishability, resource state, and adaptivity; DEMs are a useful abstraction for Clifford QEC; graphlike MWPM is fast but model-dependent.
- **Hypothesis requiring validation:** a small set of calibrated statistics (for example loss, `g2`, timing covariance, HOM visibility, and detector efficiency) is sufficient for logical prediction in a specified regime.
- **Required bridge:** Strawberry Fields or an equivalent Fock/mode reference generates conditional optical records; a custom measurement layer preserves time/mode/history information; Stim hosts reduced Clifford circuits; PyMatching supplies a graphlike baseline; a custom sampler or brute-force small code supplies the reference when the full distribution is not graphlike.
- **Minimum scientific claim:** identify at least one physical regime where an independent-erasure reduction fails a pre-registered logical-error tolerance, and identify the smallest richer model that passes on held-out parameters. If no such regime exists, the project should report a negative result and stop.
- **Metrics:** logical failure probability and confidence interval; conditional syndrome-distribution distance; decoder ranking; threshold or distance-scaling proxy; runtime and model size. `P_L` alone is insufficient because two models can agree on one code distance for the wrong reason.

## 22.5 Differentiated candidates for this iteration

### Candidate A - Minimal sufficient statistics for a microscopic fusion primitive

**Status:** PROMISING; refined version of the active compiler and primary recommendation.

**Research question:** For one dual-rail fusion-like parity measurement, what is the smallest calibrated statistic set that predicts logical observables within a fixed tolerance across code distances, rounds, and held-out hardware parameters?

**Physical mechanism:** Vacuum, one- and two-photon sectors, loss, detector inefficiency, dark counts, mode overlap, and coarse-grained detection jointly produce conditional records. Marginalizing before conditioning on the fusion outcome can turn a physical event into a different detector-error distribution.

**Simulator roles:** Strawberry Fields generates the truncated Fock/mode reference and conditional records. A measurement/history layer turns records into explicit outcome categories. Stim runs the reduced stabilizer circuits. PyMatching decodes the independent-erasure and graphlike candidates. A custom sampler or brute-force small code is the reference when the physical mechanism is not graphlike. PennyLane is excluded unless an optimization question is separately justified.

**Novelty boundary:** DEM construction, hardware-aware decoding, and fusion thresholds are established. The possible contribution is narrower: a reproducible, held-out *sufficiency map* comparing independent, pair-correlated, history-conditioned, and higher-order reductions under matched physical calibration. This is a hypothesis about a particular primitive, not a claim of a universal compiler.

**Why it matters:** It tells an experimentalist when a loss/Pauli abstraction is safe, when it is overconfident, and which calibration measurement buys logical predictive power.

**Minimum viable experiment:** Fix a 50/50 two-mode fusion, dual-rail input, threshold versus number-resolving detector variants, one explicit reset/feed-forward rule, and a repetition-code or small surface-code syndrome circuit. Sweep loss, `g2`, mode overlap, detector efficiency, and timing jitter. Compare (i) independent erasure, (ii) erasure plus measurement flip, (iii) pair-correlated DEM, and (iv) direct conditional-record sampling. Hold out a rectangular region of parameter space.

**Full paper path:** Add a fusion-network instance from an FBQC architecture, code distances 3, 5, and 7, repeated rounds, calibration uncertainty, decoder mismatch, and a finite-size scaling proxy. Report both positive and negative sufficiency results and release the primitive specification.

**Main risks:** The optical-to-syndrome convention may be arbitrary; Fock cutoff and mode discretization may dominate; correlations may be too rare to estimate; the chosen code may hide the difference. The full physical distribution may not be representable by a single DEM.

**Kill criterion:** Stop as a main project if the independent model stays within the pre-registered tolerance over all physically justified regimes, or if the result changes materially with an uncontrolled optical cutoff, or if an exact paper already reports the same primitive, reduction metric, and boundary.

**Evaluation:**

| Criterion | Score (1-10) |
|---|---:|
| Novelty after literature check | 7 |
| Importance | 8 |
| Feasibility | 7 |
| Simulator integration | 10 |
| Publication potential | 8 |
| Science-fair clarity | 8 |

### Candidate B - History-conditioned detector model for temporal fusion

**Status:** PROMISING but parameter-data limited.

**Research question:** Can two temporal-fusion devices with matched average efficiency and fusion-success probability have different logical performance because of detector dead time, afterpulsing, timing jitter, or source memory, and can a finite-state history model recover the difference?

**Physical mechanism:** A click changes the probability of a nearby click or later click; a delay line couples emissions from different times; time-bin overlap and source spin memory make the detector record non-Markovian at the scalar-efficiency level. The proposed logical effect is a hypothesis, not established by Meng et al.

**Simulator roles:** Strawberry Fields supplies the two-mode optical primitive and loss/interference statistics. A custom time-tagged detector layer adds a finite-state dead-time/afterpulse model. Stim hosts a repeated parity-extraction schedule. PyMatching is compared with static weights, time-dependent weights, and a state-expanded graph; a custom sampler verifies whether graph decomposition changes the answer.

**Novelty boundary:** Temporal fusion and temporal distinguishability are established, as are generic correlation-aware decoders. The possible novelty is the end-to-end comparison of equal-average detector models on a photonic QEC schedule, with a measured cost for ignoring history. It is not novel to say that detectors have dead time.

**Why it matters:** If history changes logical performance, detector calibration must report conditional statistics and QEC schedules may be co-designed with detector recovery time. If it does not, a simpler model is justified.

**Minimum viable experiment:** Use two matched click-record models with equal marginal efficiency, dark-count rate, and fusion success. Vary only dead time or afterpulse probability. Feed their time-tagged records into a small repeated circuit and compare static versus history-aware decoding.

**Full paper path:** Calibrate parameters from a detector data sheet or experiment, add temporal fusion and delay loss, compare decoder latency and model complexity, and test transfer across schedules and code distances.

**Main risks:** Synthetic detector parameters may not be representative; Stim may need an awkward state expansion; the effect may be absorbed by an empirically re-estimated time-dependent edge weight; a history-aware decoder may be more expensive than the gain.

**Kill criterion:** Kill if matched-average and history-aware models have indistinguishable logical results within uncertainty, or if a memoryless model with conditional per-time-bin weights reproduces the result, or if no defensible detector regime is available.

**Evaluation:**

| Criterion | Score (1-10) |
|---|---:|
| Novelty after literature check | 7 |
| Importance | 7 |
| Feasibility | 6 |
| Simulator integration | 9 |
| Publication potential | 7 |
| Science-fair clarity | 7 |
### Candidate C - Visibility-equivalent multimode distinguishability stress test

**Status:** PROMISING; high modeling risk and uncertain novelty.

**Research question:** Do two spectral/temporal mode mixtures with matched HOM visibility, single-click rates, and fusion-success probability nevertheless produce different syndrome correlations or logical error rates?

**Physical mechanism:** Partial distinguishability is a density matrix over hidden modes. Interference and detector coarse-graining trace over those modes, while time-resolved detection can reveal or erase information. The logical discrepancy is a hypothesis; Yard et al. establish that temporal resolution changes visibility, not that visibility is insufficient for QEC.

**Simulator roles:** Strawberry Fields represents a small discretized multimode interferometer and Fock cutoff. A mode-density-matrix or distinguishability-matrix layer constructs matched-marginal counterexamples. Stim carries the reduced repeated fusion circuit. PyMatching compares visibility-only and correlation-aware graphlike models; direct sampling checks the full conditional distribution.

**Novelty boundary:** Multimode interference, visibility, and distinguishability mitigation are established. The possible contribution is a controlled *equivalence-class* test: identical commonly reported optical summaries but different logical predictions, with a minimal additional calibration statistic. This must be checked against the closest fusion-threshold papers before claiming novelty.

**Why it matters:** A single visibility number is attractive experimentally. If it is not logically sufficient, calibration and decoder models need mode-sensitive statistics; if it is sufficient in the selected regime, that negative result is useful too.

**Minimum viable experiment:** Construct two two-mode mixtures with equal HOM visibility and equal click/fusion marginals but different Schmidt-mode weights or mode-dependent loss. Compare detector-event covariance and logical failure in a small repeated fusion circuit.

**Full paper path:** Add time resolution, mode-dependent loss, several mode numbers, code-distance scaling, and a calibration-sufficiency bound. Compare against the distinguishability model used by Chan et al.

**Main risks:** Strawberry Fields may not represent continuous spectral wave packets faithfully; matching all marginals may be numerically ill-conditioned; the difference may vanish after syndrome extraction; the construction may duplicate an existing distinguishability analysis.

**Kill criterion:** Kill if all matched-visibility models give the same logical result within uncertainty, if the mode model is not physically realizable, or if the same equivalence-class result is already reported.

**Evaluation:**

| Criterion | Score (1-10) |
|---|---:|
| Novelty after literature check | 6 |
| Importance | 8 |
| Feasibility | 5 |
| Simulator integration | 9 |
| Publication potential | 7 |
| Science-fair clarity | 7 |
### Candidate D - Leakage persistence and reset sufficiency in dual-rail fusion

**Status:** IMPORTANT validation case; high encoding dependence.

**Research question:** For a specified dual-rail fusion primitive, when is an out-of-code-space event adequately modeled as an immediate erasure, and when does it persist or convert into a later measurement fault unless a reset is applied?

**Physical mechanism:** Loss, vacuum, multiphoton emission, imperfect number resolution, and failed fusions can leave an optical state outside the intended single-excitation subspace. A later beamsplitter or detector can transform that state into a wrong click rather than a clean flag. This conversion is encoding- and detector-dependent.

**Simulator roles:** Strawberry Fields tracks vacuum and higher-Fock sectors through preparation, interference, loss, and measurement. A discrete latent-state bridge defines leakage, reset, and conversion events. Stim compares immediate-erasure, leakage-with-reset, leakage-without-reset, and leakage-to-measurement-flip abstractions. PyMatching evaluates the decoder cost of treating all events as erasures; direct sampling validates the bridge.

**Novelty boundary:** Leakage-aware QEC is established and general leakage-removal work exists. The possible contribution is only a device-specific sufficiency result for one photonic encoding, primitive, and reset timing. "Photonic leakage exists" is not novel.

**Why it matters:** It can prevent a serious modeling error in which an apparently heralded loss is assumed benign even though population survives into a later round.

**Minimum viable experiment:** Use vacuum, one-photon, and two-photon input sectors with a threshold detector and an explicit reset/no-reset choice. Compare the four effective models at distances 3 and 5 and two syndrome-round counts.

**Full paper path:** Add number-resolving detection, dark counts, source `g2`, leakage lifetime, reset latency, and a fusion-network placement. Report the parameter boundary at which each abstraction changes decoder ranking or logical scaling.

**Main risks:** The latent leakage state may be an arbitrary bookkeeping choice; the selected dual-rail implementation may erase immediately; Fock cutoff and detector model may dominate; the result may reproduce established general leakage behavior without a photonic-specific contribution.

**Kill criterion:** Kill if the encoding has no persistent out-of-subspace state under the selected primitive, if all abstractions are equivalent within uncertainty, or if a primary paper already gives the same reset-dependent reduction.

**Evaluation:**

| Criterion | Score (1-10) |
|---|---:|
| Novelty after literature check | 6 |
| Importance | 8 |
| Feasibility | 5 |
| Simulator integration | 9 |
| Publication potential | 7 |
| Science-fair clarity | 8 |
## 22.6 Ranking and primary choice

| Rank | Candidate | Status | Reason for rank |
|---:|---|---|---|
| 1 | A. Minimal sufficient statistics | PRIMARY | Best alignment with the active question; gives a falsifiable model-complexity versus logical-error result and can use B-D as stress tests. |
| 2 | B. History-conditioned temporal fusion | BACKUP | Most directly targets detector history, but realistic parameter calibration and state expansion are uncertain. |
| 3 | C. Visibility-equivalent multimode stress test | CONDITIONAL | Important and sharply differentiated, but multimode modeling and novelty verification are difficult. |
| 4 | D. Leakage persistence and reset sufficiency | VALIDATION CASE | High importance but encoding-specific and closest to existing leakage-QEC literature. |

**Primary project:** Candidate A, with B as the first optional extension only after the static primitive is validated. The first paper claim should be:

> For one explicitly specified photonic fusion primitive, the independent-erasure abstraction is (or is not) sufficient over a stated calibration regime; when it is not, we quantify the smallest richer detector-error model that predicts held-out logical observables.

This wording deliberately allows a negative result and does not claim that the compiler is universal or that the mechanism has never been studied.

## 22.7 Concrete next-step protocol

### Phase 0 - Literature and definitions freeze

1. Build a citation matrix with columns: primitive, encoding, physical noise, detector model, logical circuit, decoder, metric, and whether the paper uses microscopic optical modes or phenomenological parameters.
2. Search the exact combination "photonic fusion + detector error model + logical error" and the reference lists of Chan, Meng, Yard, Sahay, and Zhang. Record an explicit duplicate check before using the word novel.
3. Fix one primitive: a dual-rail two-mode 50/50 fusion with a stated success/failure convention. Fix one detector model, one feed-forward/reset convention, one small stabilizer circuit, one decoder, one primary tolerance `epsilon`, and one held-out parameter region.
4. State in methods whether a full microscopic sample is injected into a custom decoder or whether Stim is used only for the reduced model. Do not silently treat a non-graphlike physical distribution as a DEM.

### Phase 1 - Microscopic reference validation

1. Implement vacuum, one-photon, and two-photon sectors first; add loss, mode overlap, detector efficiency, dark counts, and timing only after limiting cases pass.
2. Check Fock cutoff convergence, probability normalization, symmetry under exchange of identical inputs, zero-loss/perfect-detection limits, and Monte Carlo confidence intervals.
3. Store conditional records, not only aggregate fusion success: optical outcome, click pattern, time bin, mode label if resolved, and latent source sector.

### Phase 2 - Nested reductions

Fit or calculate four reductions from a training region: independent erasure; erasure plus measurement flip; pair-correlated graphlike model; and a latent/history-conditioned model. Keep model parameters derived from the training records and never refit them on the held-out region.

### Phase 3 - Logical comparison

Run matched rounds and distances in Stim for each reduced model. Decode with PyMatching under correctly calibrated and deliberately mismatched weights. For the physical reference, use direct conditional-record sampling and the same logical-observable convention. Report `P_L`, syndrome-distribution distance, decoder ranking, confidence intervals, model size, and runtime.

### Phase 4 - Stress tests and boundary search

Sweep one physical parameter at a time and then a small factorial design. Locate the first boundary where the simpler model exceeds `epsilon`. Test whether the boundary survives detector choice, code distance, number of rounds, and an independent random seed. If an error mechanism has more than two detection events, compare direct sampling with Stim's decomposition rather than assuming equivalence.

### Phase 5 - Stop/go decision

Go to the paper-scale study only if (a) the microscopic reference is converged, (b) the optical-to-logical convention is reproducible, and (c) at least one simpler abstraction fails on held-out data while a richer model passes. Stop or publish a negative result if every justified model agrees, if the difference is below estimable uncertainty, or if a targeted duplicate search finds the same primitive, metric, and conclusion.

## 22.8 Unresolved literature questions

1. Has any primary paper already compared a microscopic photonic fusion record with a reduced DEM using held-out logical observables, rather than merely inserting phenomenological loss or distinguishability into a threshold calculation?
2. In Chan et al.'s emitter-tailored model, which optical statistics are retained and which are discarded before the logical threshold calculation?
3. Do the temporal-fusion measurements of Meng et al. provide enough time-correlated data to parameterize a finite-state detector/source history model, or only a two-photon interference metric?
4. Are realistic dead-time, afterpulse, timing-jitter, and number-resolution parameters reported for the detectors assumed in current FBQC threshold studies?
5. Under what detector assumptions does a two-photon or vacuum event become a heralded erasure versus a hidden measurement fault in the dual-rail encoding used by the target architecture?
6. Can Strawberry Fields represent the required spectral/temporal density matrix and detector coarse-graining without a discretization that changes the conclusion? If not, what custom optical reference should be used?
7. For the selected physical distribution, is a multi-detector DEM mechanism an exact description, or only a list of independent sampled events? What error is introduced by `decompose_errors=True` before PyMatching?
8. Can a finite-state detector history be represented by an augmented Clifford circuit without changing the causal meaning of the optical record, or is a custom sampler unavoidable?
9. Do decoder-adaptation methods such as DGR or data-centric circuit decoders improve the result enough that the research question becomes calibration rather than model reduction?
10. Which experimentally measured ranges of `g2`, loss, mode overlap, timing jitter, and detector efficiency make the predicted discrepancy large enough to estimate with feasible shots?
11. Is the correct sufficiency target logical failure probability, the full syndrome distribution, decoder ranking, threshold estimate, or a vector of all four? A single metric can hide a wrong mechanism.
12. Does a negative result - that a small statistic set is sufficient for one primitive - transfer to another fusion network, or should transferability itself be the paper's main endpoint?

**Bottom line:** the active idea survives, but only as a bounded, falsifiable model-reduction study. The literature supports the physical importance of loss, fusion bias, timing, distinguishability, source construction, and detector-aware decoding. It does not yet, on the evidence checked here, establish the proposed sufficiency maps or a universal microscopic-to-logical compiler. That novelty boundary remains uncertain and must be rechecked before a manuscript or public claim.
