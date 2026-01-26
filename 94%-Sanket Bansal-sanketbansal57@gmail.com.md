## Sanket Bansal (sanketbansal57@gmail.com)


| Criterion                                        | Score (out of 5) | Comments                                                                                                                                                                                                                          |
| ------------------------------------------------ | :--------------: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Requirement Coverage**                         |       **5**      | Covers all required features: private, group, and public conversations; delivery and read status; file handling; proper user modeling; and scalability considerations. No major functional gaps.                                  |
| **Modeling Correctness & Normalization**         |       **4**      | Schema is well-normalized and logically structured. Separation of delivery and read status is sound. Minor issues: storing plain `password` instead of `password_hash`, and some status fields could benefit from stricter enums. |
| **Scalability & Performance**                    |       **5**      | Excellent treatment of scaling: partitioning, sharding discussion, partial indexes, async processing, caching, and multi-region read replicas. Demonstrates strong production awareness.                                          |
| **Status & Temporal Events**                     |       **4**      | Delivery and read timestamps are handled properly. Membership history is modeled. However, message immutability is weakened by `updated_at` and `deleted_at`, slightly reducing temporal purity.                                  |
| **Security & Multi-Tenancy**                     |       **5**      | Very strong security proposal: E2E encryption, JWT rotation, validation, virus scanning, and secure uploads. Well above baseline expectations.                                                                                    |
| **Files / Multimedia Handling**                  |       **5**      | Detailed and realistic file handling: metadata-only storage, validation, virus scanning, thumbnails, CDN integration. Production-ready.                                                                                           |
| **Group Membership Semantics & History**         |       **5**      | Proper handling of join/leave/kick events with auditability. Supports historical visibility and moderation workflows.                                                                                                             |
| **Public Channels Semantics**                    |       **4**      | Public channels are supported through `type`, but detailed posting/reading rules are not fully specified in the documentation. Mostly implied.                                                                                    |
| **Documentation (notes.md & proposal.md)**       |       **5**      | Comprehensive, technically detailed, and clearly structured. Includes metrics, assumptions, weaknesses, and concrete mitigations. Shows strong original reasoning.                                                                |
| **Overall Clarity, Reasoning & Professionalism** |       **5**      | Highly professional, consistent, and mature system design. Demonstrates strong engineering judgment.                                                                                                                              |


## Score: 47 / 50 (94%)


## Remarks

### Strengths:
  
- Very strong scalability and availability planning
- Security design is outstanding, especially E2E encryption and backup strategy
- Realistic operational considerations (monitoring, failover, DLQs, PITR)
- Well-documented trade-offs and assumptions
- File/media handling is detailed and practical

### Weaknesses:

- Password field should be explicitly modeled as a hash
- Message mutability and soft-deletes slightly weaken audit guarantees
- Public channel rules could be more explicitly formalized



### AI-Generated Assessment:

  Shows consistent reasoning and deep domain understanding. Does not appear to be generic AI-generated content.
