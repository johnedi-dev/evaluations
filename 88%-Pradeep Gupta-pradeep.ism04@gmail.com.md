## Pradeep Gupta (pradeep.ism04@gmail.com)



| Criterion                                        | Score (out of 5) | Comments                                                                                                                                                                                                                                                         |
| ------------------------------------------------ | ---------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1. Requirement Coverage                          | 5                | Covers private, group, and public conversations. Includes per-user delivery and read tracking, soft delete, attachments, membership lifecycle, and scalability considerations. Fully addresses required features.                                                |
| 2. Modeling Correctness & Normalization          | 4                | Clean relational design with proper separation of entities. Status tables modeled per-user per-message. However, no strict sequence_number for guaranteed ordering, and some constraints (e.g., composite unique keys on status tables) are not clearly defined. |
| 3. Scalability & Performance                     | 4                | Mentions partitioning, sharding, replicas, caching, batching, and archiving. Good awareness of scale challenges. Slightly less detailed than stronger submissions in handling hot partitions and ordering under high concurrency.                                |
| 4. Status & Temporal Events                      | 5                | Explicit per-user read and delivery tables. Membership join/leave timestamps enforce visibility window. Soft delete supports lifecycle management. Strong temporal modeling.                                                                                     |
| 5. Security & Multi-Tenancy                      | 4                | Mentions hashing, TLS, RBAC, rate limiting, signed URLs. Good architectural coverage. Multi-tenancy isolation not explicitly modeled at DB level.                                                                                                                |
| 6. Files / Multimedia Handling                   | 5                | Proper separation of attachment metadata from message. Uses object storage and signed URLs. Includes file type and size. Clean and scalable design.                                                                                                              |
| 7. Group Membership Semantics & History          | 5                | conversation_members includes role, joined_at, left_at, is_active. Historical tracking supported. Strong lifecycle modeling.                                                                                                                                     |
| 8. Public Channels Semantics                     | 4                | Public read / restricted write clearly explained. Enforcement at application layer acknowledged. DB-level enforcement not modeled explicitly.                                                                                                                    |
| 9. Documentation (notes.md & proposal.md)        | 4                | Well structured, logical flow, clear headings. Trade-offs and weaknesses discussed. However, some sections feel templated and generic in phrasing. Still shows solid understanding.                                                                              |
| 10. Overall Clarity, Reasoning & Professionalism | 4                | Clear and professional. Demonstrates solid backend thinking. Slightly less depth than top-tier submission but still strong and coherent.                                                                                                                         |



## Score: 44 / 50 (88%)



## Remarks

### Strengths:

  - Very complete requirement coverage.
  - Strong per-user status modeling (read + delivery).
  - Good handling of membership history and visibility rules.
  - Proper file storage separation with metadata.
  - Clear trade-off discussion (SQL vs NoSQL).
  - Solid architectural proposal (security, availability, reliability).

### Weaknesses:

  - No explicit strict ordering mechanism (e.g., sequence_number).
  - Status tables may require composite unique constraints to prevent duplicates.
  - Some scalability discussion remains high-level.
  - Public channel semantics enforced only at application layer.

### AI-Generated Assessment:

This likely reflects partial AI assistance for wording, but the technical substance appears coherent and internally consistent. Minor deduction applied in documentation scoring.
