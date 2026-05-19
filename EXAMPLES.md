Structural Matrix — Worked Examples
This document provides concrete demonstrations of how the Structural Matrix identifies structural behaviour in symbolic systems.
Each example shows the method applied step‑by‑step: numeric mapping, pattern detection, role identification, and system classification.
1. Example: Simple Symbolic Sequence
Input Sequence
Code
A B B C A B C C C A
Step 1 — Numeric Mapping
Assign each symbol a numerical value:

Code
A = 1
B = 2
C = 3
Mapped sequence:

Code
1 2 2 3 1 2 3 3 3 1
Step 2 — Pattern Detection
The Structural Matrix looks for:

Clusters

2 2

3 3 3

Transitions

1 → 2

2 → 3

3 → 1

Rhythms

The cycle 1 → 2 → 3 repeats three times.

Step 3 — Role Identification
From behaviour:

A (1) consistently starts cycles → Anchor

B (2) bridges anchor to content → Transition

C (3) forms dense clusters → Content Block

Step 4 — System Classification
The system shows:

stable anchor

predictable transitions

consistent content clustering

This behaviour matches an engineered system.

2. Example: Irregular Natural‑Language‑Like Pattern
Input Sequence
Code
X Y X Z Y X Y Y Z X Y Z
Numeric Mapping
Code
X = 1
Y = 2
Z = 3
Mapped:

Code
1 2 1 3 2 1 2 2 3 1 2 3
Pattern Detection
Clusters: 2 2

Transitions: highly irregular

No repeating cycle

No stable anchor

No consistent cluster length

Role Identification
X (1) appears often but not in a stable position → Floating Anchor

Y (2) forms occasional clusters → Variable Content

Z (3) appears unpredictably → Irregular Transition

System Classification
The irregularity and organic variation match a natural system.

3. Example: Artificial Construct / Hoax Pattern
Input Sequence
Code
Q W E R T Y U I O P
Numeric Mapping
Code
Q=1 W=2 E=3 R=4 T=5 Y=6 U=7 I=8 O=9 P=10
Mapped:

Code
1 2 3 4 5 6 7 8 9 10
Pattern Detection
No clusters

No repetition

No cycles

No structural rhythm

No transitions that repeat

Role Identification
No symbol exhibits consistent behaviour.
No anchors, no frames, no content blocks.

System Classification
This is structurally indistinguishable from random noise or a hoax system.

4. Example: Constructed Language Pattern
Input Sequence
Code
A A B A A B C C A A B
Numeric Mapping
Code
A=1 B=2 C=3
Mapped:

Code
1 1 2 1 1 2 3 3 1 1 2
Pattern Detection
Clusters: 1 1, 3 3

Repeating cycle: 1 1 → 2

Occasional insertion of 3 3 as a block

Role Identification
A (1) = Anchor + Frame

B (2) = Transition

C (3) = Inserted Content Block

System Classification
This behaviour matches a constructed system with deliberate modularity.

Summary of Examples
Example	Behaviour	Classification
Simple ABC cycle	Stable roles, predictable transitions	Engineered
Irregular XYXZY	Organic variation	Natural
QWERTY sequence	No structure	Hoax / Random
AAB AAB CC AAB	Modular, deliberate	Constructed

