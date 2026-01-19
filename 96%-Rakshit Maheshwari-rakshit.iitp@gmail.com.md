## Rakshit Maheshwari (rakshit.iitp@gmail.com)



| Criterion                                        | Score (out of 5) | Comments                                                                                                                                                                                                                         |
| ------------------------------------------------ | :--------------: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Requirement Coverage**                         |       **5**      | Fully satisfies all stated requirements: private, group, and public conversations; per-user delivery and read status; attachments; correct user modeling; and scalability considerations. No missing functional areas.           |
| **Modeling Correctness & Normalization**         |       **5**      | Excellent relational modeling. Tables are well-normalized, relationships are correct, UUID usage is consistent, enums are appropriate, and constraints are clearly implied. No obvious schema flaws.                             |
| **Scalability & Performance**                    |       **4**      | Strong understanding of scale: partitioning, indexing, async processing, and read replicas are discussed. Slight deduction because sharding strategy and write-amplification trade-offs are not deeply explored at schema level. |
| **Status & Temporal Events**                     |       **5**      | Message immutability, per-user receipts, and timestamp-based visibility rules are handled very well. Temporal correctness is a standout strength of this design.                                                                 |
| **Security & Multi-Tenancy**                     |       **4**      | Security fundamentals are solid (JWT, hashing, TLS, signed URLs, RBAC). Multi-tenancy isolation is implied but not explicitly modeled or discussed (e.g., tenant_id, data isolation strategy).                                   |
| **Files / Multimedia Handling**                  |       **5**      | Attachments are cleanly separated, metadata-only storage is correct, and CDN/object storage usage is properly addressed. Design is production-ready.                                                                             |
| **Group Membership Semantics & History**         |       **5**      | Excellent handling of joins, leaves, re-joins, and historical visibility. Time-bound membership logic is clearly reasoned and consistently applied.                                                                              |
| **Public Channels Semantics**                    |       **5**      | Public conversation behavior is clearly defined: read without membership, write with membership. Semantics are explicitly documented and consistent with the schema.                                                             |
| **Documentation (notes.md & proposal.md)**       |       **5**      | Very strong documentation. Clear structure, concrete edge cases, explicit trade-offs, and precise reasoning. Reads as thoughtful and intentional rather than generic.                                                            |
| **Overall Clarity, Reasoning & Professionalism** |       **5**      | Highly professional submission. Reasoning is coherent, technically mature, and internally consistent across schema and architecture.                                                                                             |


## Score: 48 / 50

## Remarks

### Strengths:

  - Exceptional handling of temporal correctness and message visibility
  - Clean, normalized relational schema with realistic constraints
  - Strong justification for SQL choice with clear trade-off analysis
  - Documentation demonstrates real-world system design experience
  - Architecture proposal is pragmatic, layered, and production-oriented

### Weaknesses:

  - Multi-tenancy isolation is not explicitly addressed
  - Large-scale sharding and cross-region strategies could be expanded

### AI-Generated Assessment:

  The documentation shows strong original reasoning, concrete edge cases, and consistent design philosophy.
