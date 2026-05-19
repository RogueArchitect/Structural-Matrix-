Mathematical Foundations of the Structural Matrix Framework
The Structural Matrix is a behaviour‑first analytical method for extracting universal structure from symbolic systems.
This document defines the mathematical model, vectors, heuristics, and pipeline that govern the method.

1. Formal Input Definition
Let a symbolic sequence be:

𝑆
=
(
𝑠
1
,
𝑠
2
,
…
,
𝑠
𝑛
)
Where each 
𝑠
𝑖
 is a symbol from an arbitrary alphabet 
Σ
.
The Structural Matrix does not assume semantics — only behaviour.

Optionally, a set of 3D proximity relationships may be provided:

𝑃
=
{
(
𝑖
,
𝑗
,
𝑤
𝑖
𝑗
)
}
Where:

𝑖
,
𝑗
 are indices in the sequence

𝑤
𝑖
𝑗
∈
𝑅
+
 is a spatial cohesion weight

2. Symbol Vector (SV)
The Symbol Vector maps each symbol to a numeric representation.

Define a mapping function:

𝑓
:
Σ
→
𝑅
The mapped sequence is:

𝑆
𝑉
=
(
𝑓
(
𝑠
1
)
,
𝑓
(
𝑠
2
)
,
…
,
𝑓
(
𝑠
𝑛
)
)
Mapping strategies may include:

ordinal mapping

frequency‑based mapping

embedding‑based mapping

custom domain‑specific encodings

The Structural Matrix is agnostic to the mapping method as long as it is consistent.

3. Behaviour Vector (BV)
The Behaviour Vector captures positional behaviour, transitions, and local entropy.

3.1 Positional Weight
For each symbol:

𝑝
𝑤
𝑖
=
𝑖
𝑛
Normalised position in the sequence.

3.2 Transition Frequency
Define:

𝑇
(
𝑠
𝑖
,
𝑠
𝑗
)
=
count of transitions 
𝑠
𝑖
→
𝑠
𝑗
Normalised transition probability:

𝑃
(
𝑠
𝑖
→
𝑠
𝑗
)
=
𝑇
(
𝑠
𝑖
,
𝑠
𝑗
)
∑
𝑘
𝑇
(
𝑠
𝑖
,
𝑠
𝑘
)
3.3 Local Entropy
For each position:

𝐻
𝑖
=
−
∑
𝑗
𝑃
(
𝑠
𝑖
→
𝑠
𝑗
)
log
⁡
𝑃
(
𝑠
𝑖
→
𝑠
𝑗
)
Entropy is used to detect:

anchors (low entropy)

content blocks (high entropy)

terminators (entropy collapse)

The Behaviour Vector is:

𝐵
𝑉
=
(
𝑝
𝑤
𝑖
,
𝐻
𝑖
,
{
𝑃
(
𝑠
𝑖
→
𝑠
𝑗
)
}
)
4. Spatial Cohesion Vector (SCV)
The SCV introduces 3D structure into the model.

For each pair 
(
𝑖
,
𝑗
)
∈
𝑃
:

𝑆
𝐶
𝑉
𝑖
𝑗
=
𝑤
𝑖
𝑗
Define the cohesion score for symbol 
𝑠
𝑖
:

𝐶
𝑖
=
∑
𝑗
𝑤
𝑖
𝑗
This measures how strongly a symbol participates in 3D proximity structures such as:

loops

domains

boundaries

folding‑driven interactions

The SCV is:

𝑆
𝐶
𝑉
=
(
𝐶
1
,
𝐶
2
,
…
,
𝐶
𝑛
)
5. Role Assignment
Each symbol is assigned a behavioural role based on thresholds and relative comparisons.

Anchor
𝐻
𝑖
<
𝜏
𝐴
and
𝐶
𝑖
 optional
Frame
𝑝
𝑤
𝑖
≈
0
or
𝑝
𝑤
𝑖
≈
1
Transition
max
⁡
𝑗
𝑃
(
𝑠
𝑖
→
𝑠
𝑗
)
>
𝜏
𝑇
Content Block
𝐻
𝑖
>
𝜏
𝐶
Terminator
𝐻
𝑖
→
0
and
𝑃
(
𝑠
𝑖
→
𝑠
𝑗
)
 collapses
Thresholds 
𝜏
𝐴
,
𝜏
𝑇
,
𝜏
𝐶
 are adaptive and derived from sequence statistics.

6. Motif Detection
Motifs are detected by scanning for patterns of roles, entropy, and transitions.

Examples:

Anchor‑Driven Cycle
anchors repeat with periodicity 
𝑘
Cluster Burst
𝐻
𝑖
 spikes across a contiguous region
Boundary Frame
𝑠
1
,
𝑠
𝑛
 are frames
Entropy Cascade
𝐻
𝑖
>
𝐻
𝑖
+
1
>
𝐻
𝑖
+
2
>
…
3D‑Driven Motif
𝐶
𝑖
 dominates behaviour over 
𝐻
𝑖
Motifs are labelled based on rule‑based pattern recognition.

7. Classification Logic
Classification is based on aggregated metrics:

Natural
High entropy, irregular transitions
Engineered
Stable anchors, predictable cycles
Constructed
Modular blocks, low entropy
Random
No stable structure
3D‑Driven
SCV dominates BV
A final score vector determines the class:

𝐶
𝑙
𝑎
𝑠
𝑠
=
arg
⁡
max
⁡
{
𝑁
,
𝐸
,
𝐶
,
𝑅
,
𝐷
3
}
8. Full Pipeline Summary
𝑆
→
𝑆
𝑉
→
𝐵
𝑉
→
𝑆
𝐶
𝑉
→
𝑅
𝑜
𝑙
𝑒
𝑠
→
𝑀
𝑜
𝑡
𝑖
𝑓
𝑠
→
𝐶
𝑙
𝑎
𝑠
𝑠
Each stage is modular and testable.

9. Implementation Notes
All thresholds are adaptive

SCV is optional but recommended for biological or spatial systems

The method is deterministic given fixed mappings

The system is domain‑agnostic
