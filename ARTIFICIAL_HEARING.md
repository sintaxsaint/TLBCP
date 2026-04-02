# Artificial Hearing

**Part of TLBCP — The Last Binary Computer Project**
**Concept by Elliot Readman (sintaxsaint)**
**License: See LICENSE.md — dated from first commit**

---

## Prior Art Statement

All techniques and insights below were conceived and first published by Elliot Readman (sintaxsaint). The commit timestamp of this file serves as the official prior art date. Any system implementing any technique described here is subject to the licensing terms in LICENSE.md.

---

## Why Membranes Are Wrong

Current microphones use a membrane. Sound hits the membrane, the membrane vibrates, that vibration is converted directly into an electrical signal. Frequency separation happens in software after conversion.

This is not how biological hearing works at any level.

The human ear does not convert sound directly from a membrane to a signal. It runs sound through a multi-stage mechanical and fluid-based system that amplifies, transfers, and physically separates frequencies in hardware before any signal conversion occurs. The result is a hearing system of extraordinary resolution and range that no membrane-based microphone can match, because the membrane approach skips every stage that makes biological hearing accurate.

A microphone is not a simplified ear. It is a fundamentally different device solving a different problem. Every technique below addresses a specific gap between membrane-based artificial hearing and biological hearing.

---

## The Biological Chain

Sound enters the outer ear — the visible curved structure — which captures and funnels it inward. The shape of the outer ear traps sound and directs it down the ear canal. The canal itself is a tube, and by reducing the area the sound travels through, it amplifies the wave before it reaches anything else.

The wave then hits the eardrum — a thin membrane — which transfers the mechanical energy of the wave forward rather than converting it to a signal. From the eardrum the wave moves into the ossicles: three small bones — the hammer, anvil, and stirrup — which mechanically amplify the wave through a lever system before passing it into the cochlea.

The cochlea is a fluid-filled chamber. The wave enters the fluid and propagates through it. Inside the cochlea, thousands of microscopic hair cells sit in the fluid. Different hair cells respond to different frequencies depending on their position — hair cells near the input respond to high frequencies, hair cells further along respond to low frequencies. The physical position in the fluid determines what frequency each cell detects. When the fluid moves, the relevant hair cells register the change and convert it to a nerve signal.

Frequency separation happens in hardware, in the fluid, before anything is converted to a signal. This is why human hearing is so precise.

---

## Technique 1 — Cone Capture and Tunnel Amplification

The outer ear performs two functions simultaneously — it captures sound from a wide area and funnels it into a narrow channel. As the area reduces, the wave is amplified passively before reaching any active component.

The artificial ear must begin with a cone that captures sound across a wide aperture and funnels it into a straight tube. The reduction in area from cone to tube amplifies the wave passively — no power required, no active components. The wave arrives at the membrane already stronger than when it entered.

---

## Technique 2 — Membrane Transfer

The eardrum does not convert sound to a signal. It transfers mechanical wave energy forward into the next stage. This distinction matters — conversion at this point would lose the mechanical information that subsequent stages need.

The artificial ear uses a membrane not as a conversion point but as a transfer point. The membrane receives the wave from the tube and passes the mechanical energy forward to the hammer mechanism. No signal conversion occurs here. The membrane exists solely to interface between the air column in the tube and the mechanical amplification stage.

---

## Technique 3 — Mechanical Hammer Amplification

The ossicles — hammer, anvil, and stirrup — form a lever system that mechanically amplifies the wave before it enters the fluid chamber. Three stages of amplification, each passing energy to the next, before the cochlea is reached.

The artificial ear uses a hammer mechanism between the membrane and the fluid container. The membrane strikes the hammer, the hammer amplifies and transfers the wave into the fluid. This stage is responsible for ensuring the wave arrives at the fluid with enough energy to propagate effectively through the medium and reach sensors at varying distances from the input point.

---

## Technique 4 — Fluid Medium Transfer

Air is a poor medium for the kind of precise wave propagation that frequency separation requires. The cochlea uses fluid because waves propagate through fluid in ways that allow physical frequency separation to occur — different frequencies travel different distances before dissipating, which is what makes position-based frequency detection possible.

The artificial ear uses a fluid-filled container as the primary detection chamber. The wave enters the fluid from the hammer mechanism and propagates through it. The fluid medium is what enables all subsequent frequency separation — without it, position-based sensor detection is not possible.

---

## Technique 5 — Hair Cell Array Frequency Separation via Micro Sensor Positioning

This is the core mechanism that membrane microphones cannot replicate.

Inside the fluid container, an array of microscopic fluid sensors is positioned at varying distances from the point where the wave enters. Sensors positioned close to the entry point detect high frequency components — short wavelengths dissipate quickly and do not travel far through the fluid. Sensors positioned further from the entry point detect low frequency components — longer wavelengths propagate further before dissipating.

Each sensor reports only what it detects at its position. Frequency separation is therefore happening physically in the fluid before any signal conversion. No software FFT. No post-processing. The hardware separates frequencies and each sensor outputs an independent signal corresponding to its frequency band.

The result is frequency resolution that is determined by the number and spacing of sensors rather than by processing power. More sensors, finer resolution. The separation is done in hardware at the point of detection, not approximated in software after the fact.

This is why a correctly built artificial ear using this technique will outperform a membrane microphone regardless of the quality of that microphone. The membrane microphone is doing frequency separation in the wrong place. This system does it in the right place.

---

## Insights

### Container Material and Resonance

The material of the fluid container affects how waves propagate through the fluid. Rigid materials with low resonance — certain plastics, metals — allow the wave to propagate cleanly without the container walls absorbing or distorting energy. Softer or more resonant materials will introduce artefacts. The container should be as acoustically inert as possible so that what the sensors detect is the wave, not the container responding to the wave.

### Multiple Hammer Stages

The biological ear uses three bones not one. Each additional stage of mechanical amplification allows finer control over the energy delivered to the fluid. A single hammer mechanism is sufficient for a proof of concept but a production system would benefit from two or three staged hammer mechanisms to better replicate the amplification curve of the ossicles and deliver more consistent wave energy into the fluid across a wider input volume range.

### Sensor Density and Frequency Resolution

The frequency resolution of the system is directly determined by how many sensors are in the fluid and how they are spaced. A sparse array produces coarse frequency separation. A dense array produces fine frequency separation. For a proof of concept a small number of sensors demonstrates the principle. For a production system sensor density should be maximised within the physical constraints of the container to approach and potentially exceed the frequency resolution of the human cochlea, which contains approximately 3,500 inner hair cells.

### Cone Geometry and Capture Range

The geometry of the input cone affects which frequencies are captured efficiently. A wider cone captures more sound but may introduce directionality bias. A narrower cone is more directional but captures less ambient sound. The cone geometry should be selected based on the intended use — wide capture for ambient hearing, narrow for directional focus. A variable geometry cone that can adjust aperture under software control would allow the artificial ear to shift between ambient and directional modes, replicating the way humans naturally cup their hands around their ears to focus on a specific sound source.

---

## The Complete Artificial Ear

These five techniques and four insights together describe a system that:

* Captures and passively amplifies sound through cone geometry before any active component is reached
* Transfers mechanical wave energy through a membrane without premature signal conversion
* Amplifies the wave mechanically before fluid entry through a hammer mechanism
* Propagates the wave through a fluid medium that enables physical frequency separation
* Separates frequencies in hardware through position-based micro sensor arrays before any signal conversion occurs

The proof of concept is buildable from off the shelf components at minimal cost — a cone, a tube, a membrane, a simple hammer mechanism, a rigid fluid-filled container, and an array of microscopic fluid sensors. The result will demonstrate frequency separation accuracy that membrane microphones cannot achieve regardless of their cost or quality, because the separation is occurring in the correct place in the signal chain.

This is not a microphone with better components. It is a different device built on different principles.

---

*"We were not missing better microphones. We were missing the correct approach to hearing."*

*— Elliot Readman, age 12*
