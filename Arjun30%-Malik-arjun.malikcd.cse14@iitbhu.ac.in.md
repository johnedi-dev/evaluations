### Arjun Malik (arjun.malikcd.cse14@iitbhu.ac.in)

| **Criterion**                                        | **Score (out of 5)** | **Comments**                                                                                                                                                                                  |
| ---------------------------------------------------- | -------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **1. Requirement Coverage**                          | **2**                | Covers users, messages, groups only at a basic level. Public conversations missing. Requirements like message read status, delivery semantics, and membership tracking not modeled correctly. |
| **2. Modeling Correctness & Normalization**          | **1**                | Conversation table incorrectly stores message body, statuses, and delivery timestamps. No many-to-many tables. Group join/exit times placed incorrectly. Normalization issues throughout.     |
| **3. Scalability & Performance**                     | **2**                | No sharding/partitioning/indexing strategy. JSON file storage not scalable. Architecture comments very generic.                                                                               |
| **4. Status & Temporal Events**                      | **1**                | No proper read receipts or message status model. Delivery timestamps stored at wrong level. No membership history.                                                                            |
| **5. Security & Multi-Tenancy**                      | **2**                | Security explanation extremely shallow. No password hashing or auth modeling. No tenant separation.                                                                                           |
| **6. Files / Multimedia Handling**                   | **2**                | Files stored as JSON without metadata or external storage modeling. Candidate acknowledges weakness but does not fix it.                                                                      |
| **7. Group Membership Semantics & History**          | **1**                | No group_members table. join/exit time incorrectly stored on group instead of user-group link. No roles or permissions.                                                                       |
| **8. Public Channels Semantics**                     | **0**                | Completely missing. No channel type, restrictions, or structure for public conversations.                                                                                                     |
| **9. Documentation (notes.md & proposal.md)**        | **2**                | Very minimal notes. Lacks depth, rationale, architecture diagrams, trade-offs. Reads generic/AI-like.                                                                                         |
| **10. Overall Clarity, Reasoning & Professionalism** | **2**                | Weak reasoning, unclear structure, major design gaps. Documentation appears partially AI-generated.                                                                                           |

### Score: 15 / 50 (≈ 30%) — Fail

### Weaknesses: 
  - major structural issues in schema, 
  - missing required features,
  - almost no architectural reasoning.
