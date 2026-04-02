# Artificial Voice

**Part of TLBCP — The Last Binary Computer Project**
**Concept by Elliot Readman (sintaxsaint)**
**License: See LICENSE.md — dated from first commit**

---

## Prior Art Statement

All techniques and insights below were conceived and first published by Elliot Readman (sintaxsaint). The commit timestamp of this file serves as the official prior art date. Any system implementing any technique described here is subject to the licensing terms in LICENSE.md.

---

## Why Speakers Are Wrong

Current speakers are microphones in reverse. An electrical signal drives a membrane to vibrate, the membrane moves air, and that moving air is the sound. The membrane is fixed in geometry, fixed in structure, and produces sound by varying the speed and amplitude of its vibration in response to an electrical signal.

This is not how biological speech works at any level.

The human voice does not produce sound by vibrating a fixed surface. It produces sound by forcing air through a tube whose geometry is actively changing in real time under muscular control. The shape of the passage at the moment air moves through it determines the character and frequency of the sound produced. Volume and intensity are controlled independently by regulating the pressure and speed of the air itself.

A speaker is not a simplified voice box. It is a fundamentally different device solving a different problem. Every technique below addresses a specific gap between membrane-based artificial sound production and biological speech.

---

## The Biological Chain

Air is stored in the lungs and expelled by the diaphragm — a large muscle beneath the lungs that contracts to push air upward through the airway. The diaphragm controls the pressure and speed of the air moving through the system. More diaphragm force produces faster moving air at higher pressure, which produces louder sound. Less force produces quieter sound. The diaphragm is the volume and intensity control.

The air moves up through the trachea and into the voice box — the larynx. The voice box is a tube whose walls are formed by muscle and cartilage. Muscles surrounding and within the voice box contract and relax to change the shape of the passage the air moves through. The geometry of that passage at any given moment — how wide, how narrow, where it constricts, where it opens — determines the frequency and character of the sound the passing air produces.

The result of combining variable air pressure from the diaphragm with variable tube geometry from the voice box muscles is the full range of human speech — every vowel, every consonant, every tonal quality, every volume level — produced by two independent variables working in coordination in real time.

No membrane. No fixed geometry. No vibrating surface. Just shaped air.

---

## Technique 1 — Pressure Reservoir and Variable Flow Control

The lungs act as a pressure reservoir — a constant supply of air available on demand. The diaphragm does not produce air, it controls how much of the reservoir is released and at what pressure at any given moment.

The artificial voice uses a compressor as the pressure reservoir. The compressor maintains constant pressure output — the equivalent of full lungs. Between the compressor output and the voice tube sits a proportional solenoid valve. The valve controls how much air passes through at any moment and at what flow rate. Opening the valve more increases air speed and pressure into the tube — louder sound. Restricting the valve reduces flow — quieter sound.

The proportional solenoid valve is the correct component choice because solenoid actuation is fast enough to track the continuous rapid changes in air pressure that natural speech requires. Slower valve types would introduce lag that makes speech sound mechanical and unnatural.

---

## Technique 2 — Soft Body Variable Geometry Tube

The voice box is not a rigid tube. It is a soft structure whose geometry changes continuously under muscular control. The sound is produced by the shape of the passage at the moment air moves through it — the hardware is doing the work, not processing applied after the fact.

The artificial voice uses a soft flexible tube as the voice passage. Silicone is the correct material — it deforms cleanly under compression, returns to shape reliably, does not crack or fatigue under repeated deformation, and produces minimal acoustic artefact from the material itself. The tube must be soft enough to deform significantly under actuator pressure but rigid enough to return to neutral geometry immediately when pressure is released.

---

## Technique 3 — Solenoid Array Geometry Control

A single point of compression on the tube produces a single constriction — a crude approximation of voice box geometry. The biological voice box changes shape across its entire length simultaneously, creating complex 3D passage geometries that produce the full range of phonemes.

The artificial voice surrounds the soft tube with an array of solenoids positioned at multiple points around the circumference and along the length of the tube. Each solenoid fires independently, compressing the tube at its specific position. The combination of which solenoids are active, how much compression each applies, and the timing relationships between them determines the 3D geometry of the passage at any moment.

Solenoids are the correct actuator choice for two reasons. First, actuation speed — solenoids switch fast enough to track the rate at which human speech geometry changes, which is extremely rapid. Servo motors and other actuator types are too slow and would produce unnatural speech. Second, consistency with the rest of the artificial hearing and voice system — solenoids are used throughout, simplifying sourcing, control architecture, and maintenance.

---

## Technique 4 — 64-Dimensional Coordinated Control

The artificial voice has two primary control variables — valve position and solenoid array state — but the solenoid array itself contains many independent actuators each representing its own control dimension. Coordinating all of them simultaneously in real time to produce target phonemes is a high dimensional control problem.

The control system operates in 64 dimensions. Each dimension corresponds to an independent controllable element — individual solenoids, valve state, timing parameters. 64-dimensional control provides enough simultaneous independent channels to manage a full solenoid array plus valve coordination without bottlenecking, at the speed required for natural sounding speech.

This is not arbitrary. 64 dimensions of control is the minimum required to replicate the complexity of human voice box geometry changes across the full phoneme range at natural speech rates. Lower dimensional control produces robotic or limited speech. 64-dimensional control produces natural speech.

This control requirement is itself an argument for dimensional computing hardware as described in DIMENSIONAL_COMPUTING.md. A binary processor handling 64 simultaneous independent control channels at the timing precision required for natural speech is doing something genuinely hard. A higher base processor handles 64-dimensional problems natively. The artificial voice is one of many systems that demonstrates why higher base hardware is necessary rather than merely preferable.

---

## Technique 5 — Phoneme Geometry Mapping

The control system must know what solenoid array state and valve position produces each target phoneme. This is a mapping problem — for every sound the system needs to produce, there is a corresponding set of solenoid states, compression values, and valve positions that produces it.

This mapping is established through calibration. The system produces sounds across the full phoneme range, records the output, and adjusts the solenoid and valve parameters until each phoneme matches the target. Once calibrated the map is stored and the system can produce any phoneme on demand by looking up the corresponding control state and applying it.

The mapping is not universal — it depends on the specific tube material, tube dimensions, solenoid positions, and compressor pressure of the individual build. Each build requires its own calibration. A standardised build specification reduces calibration complexity by ensuring consistent geometry across builds.

---

## Insights

### Tube Length and Fundamental Frequency

The length of the soft tube affects the fundamental frequency range of the voice. A longer tube produces a lower fundamental frequency — a deeper voice. A shorter tube produces a higher fundamental frequency. Tube length should be selected based on the intended voice character of the system. A variable length tube — one that can extend or contract — would allow the system to shift its fundamental frequency range dynamically, replicating the difference between chest voice and head voice in human singers.

### Solenoid Spacing and Phoneme Resolution

The spacing of solenoids along the tube length determines how precisely the passage geometry can be shaped. Solenoids spaced too far apart produce coarse geometry changes that limit phoneme accuracy. Closer spacing produces finer geometry control and more accurate phoneme reproduction. Spacing should be minimised within the physical constraints of the tube diameter and solenoid size to maximise phoneme resolution.

### Compressor Pressure and Dynamic Range

The pressure maintained by the compressor determines the dynamic range of the system — the difference between its quietest and loudest output. Higher compressor pressure allows the valve to produce a wider range of flow rates and therefore a wider volume range. A variable pressure compressor that adjusts its output pressure under software control would allow the system to operate efficiently at low volume without maintaining full pressure continuously, reducing power consumption during quiet speech.

### Material Resonance and Voice Character

The acoustic properties of the silicone tube material contribute to the character of the produced sound in the same way that the tissue properties of the human voice box contribute to vocal timbre. Different silicone formulations with different hardness and resonance properties will produce subtly different voice characters from identical solenoid states. Tube material selection is therefore a voice design decision as well as a mechanical one.

---

## The Complete Artificial Voice

These five techniques and four insights together describe a system that:

* Maintains a constant pressure reservoir and controls air flow through a proportional solenoid valve equivalent to the diaphragm
* Uses a soft flexible silicone tube as a variable geometry passage equivalent to the voice box
* Shapes the passage geometry in real time through an independently controlled solenoid array surrounding the tube
* Coordinates all control variables simultaneously through a 64-dimensional control system fast enough to produce natural speech
* Maps target phonemes to specific control states through calibration, enabling the production of any sound in the human phoneme range

The proof of concept is buildable from off the shelf components — a small compressor, a proportional solenoid valve, a silicone tube, a solenoid array, and a microcontroller running the 64-dimensional control system. The result will produce speech through shaped air rather than membrane vibration — the same mechanism as biological speech — and will be capable of a naturalness and range that membrane speakers cannot achieve because they are using the wrong mechanism entirely.

This is not a speaker with better components. It is a different device built on different principles.

---

*"We were not missing better speakers. We were missing the correct approach to speech."*

*— Elliot Readman, age 12*
