# Individual Validation Run — Student A

| ID | Item | Answer | Evidence | Where question came from |
| :--- | :--- | :--- | :--- | :--- |
| **CL-001** | Does each requirement contain only one “shall” or “may” statement? | No | R-07 has three actions (cancel, update schedule, notify) | Rule: Clear |
| **CL-002** | Is every requirement free of undefined vague words (e.g. “quickly”, “user-friendly”, “securely”, “normal”, “policy”)? | No | R-02, R-08, R-09, R-12, R-13 | Rule: Clear |
| **CL-003** | Does every speed or time requirement state a number and a unit? | No | R-02 has no number; R-12 has no hours | Rule: Testable |
| **CL-004** | Could a pass/fail test be written for every requirement? | No | R-08 ("user-friendly") and R-09 ("securely") cannot be objectively tested. | Rule: Testable |
| **CL-005** | Are all requirements free of direct contradictions regarding appointment durations? | No | R-04 fixes appointments at 15 minutes, contradicting R-05 (10–30 minutes). | Rule: Free of contradictions |
| **CL-006** | Does the document state the exact lead time before an appointment when reminders are sent? | No | R-06 says "before appointments" without specifying hours or days. | Rule: Complete / Risk: Missed appointments |
| **CL-007** | Does the document define the minimum cancellation notice required before an appointment starts? | No | R-07 allows cancellation "at any time" with no cutoff window. | Risk: Last-minute empty slots |
| **CL-008** | Does the document specify how simultaneous booking requests for the same slot are resolved? | No | R-03 says "prevent double bookings" without locking or tie-breaker rules. | Risk: Double booking concurrency |
| **CL-009** | Does the document state the minimum number of concurrent users supported during peak Monday morning hours? | No | R-02 and R-12 omit any concurrent user or peak capacity metrics. | Risk: Peak load crash |
| **CL-010** | Does the document specify the exact encryption standard for storing medical records? | No | R-09 says "stored securely" without naming an encryption standard. | Risk: Data breach / DPO |
| **CL-011** | Does the document specify accessibility standards (such as minimum font size or screen-reader support) for elderly users? | No | R-08 mentions "all age groups" but omits measurable UI standards. | User: Patient (Elderly) |
| **CL-012** | Does the document state how emergency walk-in patients are prioritized over standard bookings? | No | R-10 allows booking walk-ins but defines no emergency override rules. | User: Receptionist |
| **CL-013** | Does the document allow doctors to block off unavailable time slots on their schedules? | No  | R-14 only allows doctors to view their schedule, not block breaks/leave. | User: Doctor |
| **CL-014** | Does the document allow the clinic administrator to configure clinic working hours? | No | R-12 mentions "normal working hours" with no admin configuration feature. | User: Clinic administrator |
| **CL-015** | Does the document specify which user roles are permitted to view patient medical records? | No | R-09 mentions records, but no requirement defines role-based access control. | User: Data protection officer |
| **CL-016** | Does the document define the exact system behavior when a patient attempts to book a fourth active appointment? | No  | R-11 sets a limit of 3 active appointments but omits the rejection behavior. | Rule: Complete |
