# Miscellaneous Techniques

**Part of TLBCP — The Last Binary Computer Project**
**Concept by Elliot Readman (sintaxsaint)**
**License: See LICENSE.md — dated from first commit**

---

## Prior Art Statement

All techniques below were conceived and first published by Elliot Readman (sintaxsaint). The commit timestamp of this file serves as the official prior art date. Any AI system implementing any technique described here is subject to the licensing terms in LICENSE.md. A single licence covers all techniques — there is no additional fee for implementing multiple techniques simultaneously.

---

## Technique 1 — Core Generative Memory

The foundational architecture described in GENERATIVE_MEMORY.md. Two memory layers. Weight reinforcement. Evidence-based decay. Inference from core memory only. Returns "I don't know yet" rather than hallucinating on unknown topics.

---

## Technique 2 — Timestamp Injection

Temporal awareness baked into memory at the entry level.

Each memory slot carries a creation timestamp and a last-reinforced timestamp. The system can reason about when it learned something, how recently it was reinforced, and whether information may be outdated. Enables time-aware responses without external date injection at query time.

---

## Technique 3 — User-Adaptive Memory

Per-user personalisation without centralised data collection.

The system maintains a separate memory layer per user tracking preferred communication style, topic interest weights, explicit user corrections stored permanently for that user, and feedback weighting where positively received responses increase weight for that user specifically.

Privacy variant: user memory stored locally on the user's device. The model never receives raw user data — only weight adjustments derived from local interactions. Zero data sent to any server.

---

## Technique 4 — Contextual Decay Triggers

Targeted belief revision through contradiction detection rather than passive decay.

When new information directly contradicts an existing core memory entry the system detects and flags the contradiction, reduces the conflicting entry's weight proportionally to the strength of contradicting evidence, and allows both entries to coexist temporarily with their respective weights. Over time whichever entry receives more reinforcement becomes dominant.

Nuanced belief revision rather than abrupt replacement — the same way humans update understanding when presented with conflicting information.

---

## Technique 5 — Hierarchical Memory Layers

Short, medium, and long-term memory with automatic promotion and demotion.

Three tiers: Ephemeral Memory (current session only, cleared on end), Working Memory (persists across recent sessions, decays without reinforcement), and Permanent Memory (fully reinforced core memory, requires strong contradicting evidence to reduce).

Information promotes upward as it accumulates weight. Demotion occurs when weight falls below tier thresholds.

---

## Technique 6 — Associative Memory Linking

Semantic connections between memory entries enabling associative thinking.

When a new memory is added to core memory the system computes similarity scores against existing entries. Entries above a similarity threshold are linked. When one linked entry is recalled, associated entries receive a weight boost for that response — surfacing connected knowledge without explicit query.

Asking about one topic naturally surfaces related knowledge, the same way human memory works.

---

## Technique 7 — Emotional Weighting

Sentiment-aware memory reinforcement without hardcoded sentiment rules.

Memory entries carry an emotional valence score derived from the sentiment of the input and response at time of storage. Emotionally charged inputs receive higher initial weights. Responses to emotionally charged queries prioritise memories with matching valence scores.

---

## Technique 8 — Memory Confidence Scoring

Explicit uncertainty quantification per memory entry.

Each core memory entry carries a confidence score computed from the number of reinforcing encounters, the consistency of reinforcing inputs, and the presence or absence of contradicting evidence.

Below a confidence threshold the system qualifies its answer — "I believe…" rather than "I know…" — rather than presenting uncertain knowledge as fact.

---

## Technique 9 — Multi-Agent Shared Memory Pools

Collective knowledge across multiple AI instances with validation gates.

Multiple agents share a common core memory pool. Each agent reads from the shared pool but writes to its own local memory first. Entries promote to the shared pool only after passing a reinforcement threshold across multiple agents — preventing one agent's errors from corrupting shared knowledge.

---

## Technique 10 — Vision Memory

Image and visual input stored and reinforced using the same architecture.

Pixel values normalised to 0–1 range serve as the vector input instead of text embeddings. The same weight reinforcement, evidence-based decay, and core memory inference mechanisms apply. Honest uncertainty for things not seen enough times to be confident about.

---

## Technique 11 — Audio Memory

Sound and speech stored and reinforced using the same architecture.

Waveform embeddings — amplitude over time and frequency components — replace text vectors. Enables recognition of voices, sounds, and audio patterns through reinforcement rather than fixed classification.

---

## Technique 12 — Procedural Memory

How-to knowledge stored separately from declarative knowledge.

A dedicated memory layer for sequences of actions rather than facts. Procedural memories reinforce when a sequence is successfully completed and decay when a sequence produces errors. Enables genuine skill acquisition — the system gets better at tasks it performs repeatedly and forgets approaches that consistently fail.

---

## Technique 13 — Privacy-Preserving Federated Memory

Collective learning without centralised data collection.

Individual user memories never leave the user's device. Only weight gradients — mathematical summaries that cannot be reversed to recover personal data — are shared with a central aggregation server. The central model improves from collective experience without ever seeing individual user data.

---

## Technique 14 — Contradiction Resolution Voting

Democratic belief revision in multi-agent systems.

When contradicting evidence is detected in a shared memory pool all agents that have encountered the relevant topic cast a weighted vote based on their individual confidence scores. The majority view wins and updates the shared pool. Minority views are retained with reduced weight rather than deleted — preserving information that may later prove correct.
