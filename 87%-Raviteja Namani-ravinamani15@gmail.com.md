## Raviteja Namani (ravinamani15@gmail.com)



| Criterion                                            | Score (out of 5) | Comments                                                                                                                                                                                                                                        |
| ---------------------------------------------------- | :--------------: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **1. Requirement Coverage**                          |       **5**      | All core requirements are covered: private, group, and public conversations; message delivery and read status; attachments; and proper user modeling. No major functional gaps.                                                                 |
| **2. Modeling Correctness & Normalization**          |       **4**      | Schema is clean and well-normalized. Use of `ConversationMember` and `MessageStatus` is correct. Minor issue: `active` as string instead of boolean, and `message_id` type mismatch in `Attachment` (string vs integer).                        |
| **3. Scalability & Performance**                     |      **4.5**     | Strong awareness of scale: partitioning by `conversation_id`, write-heavy workloads, caching, and hybrid SQL/NoSQL considerations. Slight deduction because concrete indexing and sharding strategies are discussed but not explicitly modeled. |
| **4. Status & Temporal Events**                      |       **5**      | Delivery/read modeled correctly with timestamps. Join/leave history (`joined_at`, `left_at`) is a strong design choice enabling correct message visibility over time.                                                                           |
| **5. Security & Multi-Tenancy**                      |       **4**      | Password hashing, token-based auth, access checks, and presigned URLs are clearly addressed. Multi-tenancy is implicitly supported but not explicitly discussed (e.g., tenant isolation strategy).                                              |
| **6. Files / Multimedia Handling**                   |      **4.5**     | Attachments separated cleanly with metadata only; external object storage assumed correctly. Could mention MIME validation or virus scanning for full marks.                                                                                    |
| **7. Group Membership Semantics & History**          |       **5**      | Excellent handling of membership lifecycle, roles, and historical correctness. Explicitly addresses “no access before join” requirement.                                                                                                        |
| **8. Public Channels Semantics**                     |       **4**      | Public channels are supported via `type=public`, but semantics rely entirely on application-layer rules. Acceptable, but lacks explicit read-without-membership modeling or clarity on posting rules.                                           |
| **9. Documentation (notes.md & proposal.md)**        |       **4**      | Clear, well-structured, and relevant. Shows understanding of trade-offs and weaknesses. Some phrasing and structure feel somewhat generic and polished, slightly reducing perceived originality.                                                |
| **10. Overall Clarity, Reasoning & Professionalism** |      **4.5**     | Submission is coherent, technically sound, and professionally written. Reasoning is logical and consistent across schema and architecture.                                                                                                      |


## Score: 43.5 / 50 (87%)

## Remarks

### Strengths

 - Solid, industry-aligned data model for chat systems
 - Correct handling of message states and group membership history
 - Good scalability thinking (partitioning, async processing, caching)
 - Architecture proposal is realistic and well-scoped

### Weaknesses

  - Minor schema inconsistencies (data types, booleans vs strings)
  - Public channel behavior is underspecified at the data level
  - Multi-tenancy and indexing strategies could be more explicit

### AI-Usage Analysis
 The documentation is clear and well written, but some parts use general technical language that is often seen in AI-assisted writing.

