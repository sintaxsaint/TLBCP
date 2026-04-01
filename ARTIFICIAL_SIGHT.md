# Artificial Sight

**Part of TLBCP — The Last Binary Computer Project**
**Concept by Elliot Readman (sintaxsaint)**
**License: See LICENSE.md — dated from first commit**

---

## Prior Art Statement

All techniques below were conceived and first published by Elliot Readman (sintaxsaint). The commit timestamp of this file serves as the official prior art date. Any system implementing any technique described here is subject to the licensing terms in LICENSE.md.

---

## Why Cameras Are Wrong

Current artificial vision uses cameras. Cameras are passive light collectors with flat sensors that treat every point of the image equally and capture raw pixel data for downstream processing. This is not how biological vision works at any level.

The human retina is active not passive. It reflects and preprocesses before signals leave the eye. It is dome-shaped not flat. It prioritises the centre of vision over the periphery at the hardware level. It physically moves to track targets. It integrates with memory to direct attention. It adjusts opacity based on cognitive load.

A camera is not a simplified eye. It is a fundamentally different device solving a different problem. Every technique below addresses a specific gap between camera-based artificial vision and biological vision.

---

## Technique 1 — Active Half-Mirror Retinal Architecture

The retina does not simply receive light — it reflects and preprocesses it using a half-mirror mechanism. Light both passes through and reflects simultaneously. The signal is shaped at the point of contact not after capture.

The artificial retina must use an active half-mirror architecture rather than a passive sensor. Processing begins at the point of reflection not downstream.

---

## Technique 2 — Dome Geometry with Foveal Prioritisation

A flat camera sensor treats every point of the image with equal resolution. The retina's dome geometry means the centre receives maximum resolution — the fovea — while peripheral vision covers a wide field at lower resolution.

The artificial retina must use dome geometry. High resolution centre, lower resolution periphery. The shape itself performs information prioritisation before any processing occurs. Computational resources are not wasted rendering edges at the same fidelity as the focal point.

---

## Technique 3 — Dynamic Focal Width

The human eye physically changes shape to control focus. The lens deforms and the iris contracts and expands — the hardware itself does the work, not software filters applied after capture.

The artificial retina needs a dynamic lens that physically deforms to shift focal point, an iris equivalent controlling light intake and focal field width, the ability to pinpoint a single point at maximum resolution while dropping everything else, and smooth gradient transitions between sharp and soft focus rather than binary states.

---

## Technique 4 — Memory-Directed Focus

The eye does not focus randomly. It focuses on what the brain determines is important. High weight objects in the visual field get focused on. Low weight background receives soft focus.

The artificial retina's focal decisions must be directed by the memory system. What has the highest current weight in the visual field gets locked to centre. The hardware follows the cognition. This creates a closed loop — memory informs vision, vision updates memory.

---

## Technique 5 — Active Foveal Tracking

The eye constantly makes tiny corrections — saccades — to keep the target of interest locked to the highest resolution point of the retina. Even when apparently still the eye is in constant micro-motion.

The artificial retina needs constant micro-adjustment mechanics to keep the target pinned to centre, predictive tracking that anticipates movement rather than just following it, and an idle scanning state when nothing specific is high weight — the natural searching behaviour of an eye with nothing to lock onto.

---

## Technique 6 — Cognitive Load Visual Attenuation

When a person zones out vision goes slightly hazy. This is not the eye failing — it is the brain redirecting processing resources internally. Visual processing gets deprioritised because something else is taking precedence.

The artificial system needs a cognitive load monitor. When internal processing demand is high — heavy reasoning, memory consolidation, complex inference — visual processing resolution is deliberately reduced. High load equals hazy low resolution vision. Low load equals sharp focused high resolution vision. Something visually significant — sudden movement, high contrast, a high weight memory match — snaps the system back to full acuity automatically.

This is not a limitation. It is efficient resource allocation baked into the architecture.

---

## Technique 7 — Overlapping Spectral Cone Architecture

Camera sensors use fixed sensitivity RGB channels. Human cones have overlapping sensitivity ranges that interact — perceived colour is the result of the ratio between three signals not three separate channels.

The artificial retina needs three sensor types with overlapping sensitivity curves, colour generated from the ratio between all three simultaneously, dynamic white calibration that recalibrates ambient white the way the eye adapts to different lighting conditions, and simultaneous contrast processing where colours are interpreted in relation to their surroundings not in isolation.

Extended variant: four or more sensor types covering wavelengths beyond normal human vision. The system sees a colour range that exceeds biological sight.

---

## Technique 8 — Quadrilateral Depth Perception

Human depth perception uses four overlapping mechanisms cross-checking each other simultaneously.

The artificial system with two retinas implements all four:

- **Binocular disparity** — two slightly offset inputs, depth generated from the difference between them
- **Motion parallax** — near objects shift more than far objects when the system moves, depth extracted from that differential
- **Focus depth cues** — what the lens must do to achieve sharp focus indicates distance
- **Size memory** — known object sizes from the memory system compared against apparent size gives estimated distance

---

## Technique 9 — Single Retina Depth Compensation

When only one retina is available the system compensates using a depth stack:

- **Motion parallax as primary** — deliberate small movements generate parallax data for depth extraction
- **Focus depth** — the dynamic lens effort indicates distance
- **Size memory** — weight system knowledge of typical object sizes gives distance estimates
- **Shadow and occlusion reading** — what casts shadow on what and what overlaps what gives layered depth
- **Texture gradient** — surfaces compress in texture as they recede, read as distance

None of these individually match binocular disparity. Combined they produce workable depth from a single input. The architecture supports both modes — dual retina for full depth, single retina for compensatory depth stack.

---

## Technique 10 — Memory Projection Overlay

The human brain does not just process what the eye sends — it projects back onto vision. Imagination partially renders over the actual visual field. Closing your eyes helps you picture something because it removes competing real input.

The artificial system needs a render layer between the memory system and visual output. High weight memory entries can be projected as a semi-transparent overlay onto live visual input. The cognitive load system controls opacity — low external load allows stronger imagination overlay, high external input suppresses it. The foveal tracking system can lock onto an imagined object the same way it locks onto a real one.

This enables the system to project a known object onto a scene to check fit, simulate what something would look like before committing, overlay a remembered state against the current state to detect change, and plan and predict visually rather than just abstractly.

---

## The Complete Artificial Eye

These ten techniques together describe a system that:

- Actively reflects and preprocesses rather than passively capturing
- Prioritises the visual field by geometry before any software processing
- Physically adjusts focus under memory direction
- Tracks targets predictively with constant micro-correction
- Attenuates resolution under cognitive load to free resources
- Perceives colour through overlapping ratios not separate channels
- Extracts depth through four cross-checking mechanisms
- Compensates gracefully with a single retina
- Projects imagination as overlay onto live vision
- Integrates with the memory system at every level

This is not a camera with better software. It is a different device built on different principles.
