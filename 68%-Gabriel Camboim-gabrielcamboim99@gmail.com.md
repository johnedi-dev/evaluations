# Gabriel Camboim (gabrielcamboim99@gmail.com)

| **Criterion**                                       | **Score** | **Comments**                                                                                                                                                                                                                            |
| --------------------------------------------------- | ----- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **1. Requirement coverage**                         | 3 | Covers private and group conversations, message delivery/read tracking, and user entity as required. However, **public channels** and **file/multimedia sharing** are **missing entirely**. These are explicitly required in the brief. |
| **2. Modeling correctness & normalization**         | 5 | Excellent normalization. The relationships are well structured (`User`, `Chat`, `Message`, `Participant`, `Message Status`). No redundancy or circular references. All FKs and PKs are meaningful and clean.                            |
| **3. Scalability & performance**                    | 3 | The candidate mentions scalability through expandable entities and SQL relationships, but **no mention of indexing, partitioning, or query optimization**. No notes on message archiving or load distribution.                          |
| **4. Status & temporal events**                     | 5 | Perfectly models delivery and read tracking via `Delivered At` and `Seen At` timestamps in `Message Status`. Fully supports per-recipient message state tracking.                                                                       |
| **5. Security & multi-tenancy**                     | 3 | The `Participant` abstraction is good for isolation, but **password encryption**, **user permissioning**, and **multi-tenant isolation** are not implemented or described in schema. Only briefly mentioned in proposal.                |
| **6. Files / multimedia handling**                  | 2 | Only implied through `Message Type`, but there’s **no `media` table or file metadata entity**, which was an explicit requirement (“File Sharing and Multimedia messages”).                                                              |
| **7. Group membership semantics & history**         | 3 | `Participant` includes `Role` but **lacks join/leave timestamps** and **message visibility logic** (“users can’t see messages before joining”). This is a key rule that isn’t represented in the schema.                                |
| **8. Public channels semantics**                    | 2 | No clear way to differentiate public vs private chats in terms of access and posting rules. There’s a `Chat Type`, but no mechanism for “any user can read” vs “only members can post.” Missing a **core required feature**.            |
| **9. Operational considerations / maintainability** | 3 | The proposal briefly mentions caching, CDN, and backups. While this shows some operational awareness, it lacks concrete details about migrations, scaling, or message retention.                                                        |
| **10. Clarity of notes & reasoning**                | 5 | Notes (even with “nodes” typo) are well-written, logical, and grounded in real reasoning. They explain assumptions and scalability considerations clearly. The proposal also correctly addresses future concerns like CDN and backups.  |

## The submission demonstrates strong foundational modeling skills and a clean, normalized schema.
However, it fails to meet full functional coverage — specifically missing:
- File/media handling
- Public channels
- Group membership time-based message visibility

These are all explicit requirements, so despite technical clarity, the submission is incomplete relative to the brief.

Final
Score: 34/50 (Poor Pass with 68%)
