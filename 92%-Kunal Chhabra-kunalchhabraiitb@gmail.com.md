Kunal Chhabra (kunalchhabraiitb@gmail.com)

### Evaluation Table

| Criterion                                            | Score (out of 5) | Comments                                                                                                                                                                                                                                                                                                                  |
| ---------------------------------------------------- | ---------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **1. Requirement Coverage**                          | **5 **        | All required features are covered: private, group, and public conversations via a unified `conversation` model; message delivery and read status via `message_status`; file and multimedia handling via `message_attachment`; proper user modeling; and explicit consideration of scale. No major requirement is missing. |
| **2. Modeling Correctness & Normalization**          | **5 **        | Schema is well-normalized with clear separation of concerns. Junction table (`conversation_member`) is correctly used. No obvious redundancy or denormalization issues. Relationships are logical and enforceable.                                                                                                        |
| **3. Scalability & Performance**                     | **4 **        | Candidate demonstrates solid understanding of scale issues (message table growth, status table explosion, read replicas, partitioning). Indexing strategy is thoughtful. Lacks concrete partitioning or sharding strategy details, but acceptable for this assessment level.                                              |
| **4. Status & Temporal Events**                      | **5 **        | Delivery and read timestamps are explicitly modeled. Use of `joined_at` and `left_at` to control message visibility is correct and clean. Temporal logic is well-reasoned and supported by schema design.                                                                                                                 |
| **5. Security & Multi-Tenancy**                      | **4 **        | Security considerations are strong: password hashing, JWT lifecycle, rate limiting, encryption, account lockout. Multi-tenancy is implicitly handled via conversation membership. Slightly more explicit tenant isolation discussion could improve this.                                                                  |
| **6. Files / Multimedia Handling**                   | **5 **        | Correct separation of file metadata from message content. Supports multiple attachments per message. Proper assumption of external object storage. Clean, extensible design.                                                                                                                                              |
| **7. Group Membership Semantics & History**          | **5 **        | Excellent handling of join/leave history, roles, and visibility rules. `joined_at`, `left_at`, and `is_active` fields enable accurate historical queries and enforcement of access rules.                                                                                                                                 |
| **8. Public Channels Semantics**                     | **4 **        | Public conversations are addressed via `conversation.type` and documented assumptions. Read/write semantics are reasonable, though enforcement rules are left to application logic rather than explicitly modeled. Still acceptable.                                                                                      |
| **9. Documentation (notes.md & proposal.md)**        | **4 **        | Documentation is clear, structured, and technically sound. The tone is practical and experience-driven. While polished, it shows original reasoning and trade-off awareness. Minor risk of AI assistance due to fluency, but not excessive or generic.                                                                    |
| **10. Overall Clarity, Reasoning & Professionalism** | **5 **        | Submission is coherent, well-argued, and professional. Design choices are justified with real-world trade-offs. Reads like work from someone who has built or seriously thought about production systems.                                                                                                                 |

---

## Total Score: 46 0 (92% - Pass)
---

## Remarks

This is a strong submission with a clean, production-grade relational model and well-reasoned architectural thinking. The database schema correctly balances normalization with practical query patterns. Temporal events, membership history, and delivery semantics are handled particularly well.

The notes and proposal demonstrate genuine understanding rather than surface-level explanations. While the writing is polished enough that light AI assistance cannot be ruled out, the presence of concrete trade-offs, realistic limitations, and pragmatic prioritization strongly suggests original reasoning rather than generated boilerplate.

Overall, this candidate shows solid backend and system design maturity and would be a strong fit for roles involving data modeling and scalable application architecture.
