# Himanshu Poonia's Evaluation — Database Modeling & System Design

## Evaluation Table

| Criterion                                   | Score (out of 5) | Comments                                                                                                                                                                                                              |
|---------------------------------------------|:----------------:|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **1. Requirement Coverage**                  | **5**            | Covers private/group/public, read receipts, delivery, attachments.                                      |
| **2. Modeling Correctness & Normalization**  | **4**            | SQL modeling mostly correct. Mixing SQL for metadata and NoSQL for messages causes fragmentation. `messages` underspecified (no reply_to, type, soft-delete). Missing FK constraints on NoSQL side.                   |
| **3. Scalability & Performance**             | **4**            | Good justification for hybrid SQL/NoSQL. Understands message throughput, partitioning, replicas, caching. Could specify NoSQL type (Cassandra/DynamoDB) and clearer sharding strategy.                                 |
| **4. Status & Temporal Events**              | **4**            | Delivery/read status modeled but overly simple: no timestamped events, minimal read tracking, missing created_at/updated_at in event tables.                                                                          |
| **5. Security & Multi-Tenancy**              | **4**            | Covers auth, HTTPS, RBAC, rate limiting. Lacks encryption at rest, E2EE, audit logs, or secure file handling. Mentions `password_hash` but no enforcement or rotation strategy.                                       |
| **6. Files / Multimedia Handling**           | **4**            | Good attachment metadata, S3/GCS usage. Missing thumbnails for videos, streaming logic, or signed URLs.                                                                                                               |
| **7. Group Membership Semantics & History**  | **4**            | Has joined_at, exit_at, removed_at, last_read_at. Missing left_at equivalent restricting history visibility. No soft-delete flag for membership.                                                                      |
| **8. Public Channels Semantics**             | **3**            | Only `is_public` boolean. No notion of restricted posting, moderation roles, or visibility layers. Minimal implementation.                                                                                            |
| **9. Documentation Quality**                 | **4**            | Clear and structured. Hybrid rationale well explained. Some statements slightly generic but overall technically solid.                                                                                                 |
| **10. Overall Clarity & Professionalism**    | **4**            | Reasoning is coherent, architecture well organized. Lacks depth in message schema evolution, consistency guarantees, and operational complexity. Still strong overall.                                                |

---

## Total Score: 40 / 50  ( 80% - Not Selected for next round)

---

## Technical Remarks

### Strengths
- Strong understanding of hybrid SQL + NoSQL for high-volume chat workloads.
- Proper relational modeling for users, conversations, participants.
- Realistic availability plan (replicas, Redis, partitioning).
- Clear distinction between metadata and message storage.
- Sensible reliability considerations (queues, idempotency).

### Areas to Improve
- NoSQL message schema too minimal needs type, soft delete, reply_to, attachment linkage clarity.
- Delivery/read tracking lacks timestamp granularity.
- Public channel model shallow (no posting permissions or moderation roles).
- NoSQL structures lack detail: key design, partition keys, indexing.
- Security section missing E2EE, storage encryption, rotation, auditing.

### AI-Generated Likelihood
- Some generic phrasing, but architectural reasoning seems genuine.
- Not strongly AI-written; minimal deductions applied.
