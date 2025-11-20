### Rishabh Katiyar (rishabhkatiyar1112@gmail.com)

| **Criterion**                                        | **Score (out of 5)** | **Comments**                                                                                                                                                                                                                                                                                                                                  |
| ---------------------------------------------------- | -------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **1. Requirement Coverage**                          | **4**                | Covers private, group, public functionality; read receipts; attachments; participants; reactions. **BUT missing critical requirement:** group members must *not* see messages before joining. No `left_at` or visibility window. Public-channel semantics partially captured but not enforced.                                                |
| **2. Modeling Correctness & Normalization**          | **4**                | Clean relational structure, well-organized tables, properly separated attachments, reads, reactions, participants. Normalization strong. Missing join/leave timestamps for group visibility logic. Public read/writerules not modeled.                                                                                                        |
| **3. Scalability & Performance**                     | **5**                | Excellent — hybrid SQL + NoSQL architecture, Cassandra partitioning, Redis caching, Elasticsearch indexing, event log reasoning, mitigation for hotspots. Goes far beyond assignment expectations.                                                                                                                                            |
| **4. Status & Temporal Events**                      | **3**                | Message reads captured. No delivery-status table (explicit requirement). No join/leave timestamps → can’t enforce “can’t see earlier messages” rule. Status modeling incomplete.                                                                                                                                                              |
| **5. Security & Multi-Tenancy**                      | **5**                | proposal.md is extremely strong: TLS 1.3, RBAC, mTLS, KMS/Vault, OWASP, audit logging, auth refresh, rate limiting. Meets and exceeds assignment expectations. Multi-tenancy not required, so not penalized.                                                                                                                                  |
| **6. Files / Multimedia Handling**                   | **5**                | Attachments modeled cleanly; object-store architecture explained; metadata separated; Cassandra timeline explains scaling; proper file_type, size, metadata. Excellent.                                                                                                                                                                       |
| **7. Group Membership Semantics & History**          | **2**                | Major missing element: **no `joined_at` used for message visibility**. Requirements state: *users cannot see messages sent before they joined*. Diagram includes `joined_at` but **Messages table has no timestamp system supporting filtering logic**, and `left_at` is missing. Participants table lacks proper semantics beyond existence. |
| **8. Public Channel Semantics**                      | **3**                | Public channels exist but missing rules: public read by all users (even non-members) not modeled; only-members-can-post not enforced by schema. Partial but incomplete.                                                                                                                                                                       |
| **9. Documentation (notes.md & proposal.md)**        | **5**                | Extremely detailed, advanced, technically deep. Explains decisions, assumptions, SQL vs NoSQL trade-offs, weaknesses, mitigations, architecture evolution model, DR, availability, reliability, robustness. This is standout documentation.                                                                                                   |
| **10. Overall Clarity, Reasoning & Professionalism** | **5**                | Highly professional. Clear reasoning, advanced architectural awareness, explicit trade-offs. Documentation reads like a senior/principal-level engineer wrote it. No indications of AI auto-generation; if anything, very high human-level sophistication.                                                                                    |


### Score: 41 / 50 (82% —  Pass)

Strengths

  - Extremely strong architectural documentation.
  - Hybrid SQL/NoSQL reasoning is advanced and realistic.
  - Proposal.md shows deep experience in reliability, availability, security.
  - ERD is clean, normalized, and easy to read.
  - Good modeling of reactions, reads, attachments.

Weaknesses

Missing core functional requirement:
  - group chat visibility restriction (no pre-join message access).
  - No delivery status table — requirement explicitly asked for delivery + read.
  - Public channel rules not enforced in schema.
  - Participants table lacks left_at (required to know when they exited).
  - Conversations missing fields for public-read/non-member semantics.

AI-Generated Suspicion

  - Notes + proposal are very high quality but show strong technical coherence, consistent style, and explicit correctness — does not resemble typical AI-generated text.
  - ERD does not show AI-tool artifacts → Low suspicion of AI generation.
