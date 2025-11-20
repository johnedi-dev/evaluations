### José Tobias Souza dos Santos (tobiassouza0@gmail.com)

| **Criterion**                                        | **Score (out of 5)** | **Comments**                                                                                                                                                        |
| ---------------------------------------------------- | -------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **1. Requirement Coverage**                          | **5**                | Fully covers private, group, public chats; read/delivery status; files; membership rules. Minor gaps, but still meets assignment requirements completely.           |
| **2. Modeling Correctness & Normalization**          | **4**                | ERD is solid and normalized. Models relationships correctly. Minor issues (`messages.left_at`, nullability choices).                                                |
| **3. Scalability & Performance**                     | **3**                | Basic considerations present. Missing SQL vs NoSQL scaling rationale (required in Task 2). No indexing/partitioning discussion.                                     |
| **4. Status & Temporal Events**                      | **5**                | Strong modeling of delivery/read status and group visibility windows. Meets requirements thoroughly.                                                                |
| **5. Security & Multi-Tenancy**                      | **2**                | proposal.md barely addresses required security topics. Missing encryption, auth, RBAC, password handling, tenancy isolation.                                        |
| **6. Files / Multimedia Handling**                   | **4**                | Good entity modeling for uploads (MIME, size, metadata). Meets assignment expectations.                                                                             |
| **7. Group Membership Semantics & History**          | **4**                | join/leave behavior supports assignment rules (“cannot see earlier messages”). Missing admin kick-out logic detail.                                                 |
| **8. Public Channels Semantics**                     | **3**                | Basic modeling exists. But missing explicit write/read rules discussion & performance considerations for channel scale.                                             |
| **9. Documentation (notes.md & proposal.md)**        | **2**                | notes.md shallow; does not deeply compare SQL vs NoSQL as required. proposal.md missing required architectural suggestions for security, availability, reliability. |
| **10. Overall Clarity, Reasoning & Professionalism** | **3**                | Diagram clean and readable. docs too short for assignment expectations; reasoning not sufficiently deep.                                                            |


### Score: 35 / 50 (70% — Average)

Remarks

Strengths

  - Database diagram meets functional requirements.
  - Good modeling of message status, read receipts, and membership history.
  - Clean separation of concerns (messages, uploads, status, memberships).

Weaknesses

  - Task 2 and 3 documentation incomplete relative to assignment requirements.
  - SQL vs NoSQL trade-offs barely discussed.
  - Security, availability, reliability suggestions largely missing.
  - Minor inconsistencies in ERD.
