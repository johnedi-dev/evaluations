## Ankur Kumar Singh (ankurksingh1312@gmail.com)

| **Criterion**                                        | **Score (out of 5)** | **Comments**                                                                                                                              |
| ---------------------------------------------------- | -------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| **1. Requirement Coverage**                          | **5**                | Covers all chat types private, group, and public — with clear message, read, and delivery tracking; includes file/media handling.       |
| **2. Modeling Correctness & Normalization**          | **4**                | Well-structured overall, but a few naming inconsistencies (`converSation_id` typo, public tables split unnecessarily). Slight redundancy. |
| **3. Scalability & Performance**                     | **4**                | Mentions sharding, replicas, and Cassandra for heavy writes — good awareness, though lacks explicit index or query optimization detail.   |
| **4. Status & Temporal Events**                      | **4**                | Read and delivery tables exist, but not clearly modeled with composite keys or unique constraints for event tracking.                     |
| **5. Security & Multi-Tenancy**                      | **5**                | Excellent awareness, rate limiting, encryption, validation, HTTPS, and secure tokens all mentioned.                                      |
| **6. Files / Multimedia Handling**                   | **5**                | Smart design choice,  media handled via CDN/blob with centralized metadata. Practical and scalable.                                       |
| **7. Group Membership Semantics & History**          | **5**                | Correctly models admin roles, join times, and active states; solid understanding of group management dynamics.                            |
| **8. Public Channels Semantics**                     | **4**                | Public conversation tables exist but slightly over-modeled (split into two). Conceptually clear but could be simplified.                  |
| **9. Documentation (notes.md & proposal.md)**        | **4**                | Covers reasoning and trade-offs well but has minor grammatical and spelling errors, suggesting rushed or less polished writing.           |
| **10. Overall Clarity, Reasoning & Professionalism** | **4**                | Technically solid and human-written, but structure and tone lack refinement compared to top submissions.                                  |


## Score: 44 / 50 (88% — Pass)

### Remarks
 Strengths:

  - Comprehensive design capturing all core chat app requirements.
  - Excellent awareness of security, availability, and resilience aspects.
  - Realistic use of hybrid architecture ideas (e.g., SQL + Cassandra for scaling).
  - Good practical understanding of distributed systems and cloud media handling.

 Areas to Improve:

  - Slight redundancy in public conversation tables — could unify schema.
  - Needs more explicit mention of indexing and constraints for status tables.
  - Documentation could be clearer and more polished — minor typos reduce professional impression.

  
