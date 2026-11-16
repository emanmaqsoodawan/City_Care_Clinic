# MediTrack SRS Validation Findings

Following our independent validation runs (`run-A.md` and `run-B.md`), we reconciled our results and identified **13 confirmed defects** across the MediTrack SRS. **CityCare Clinic should not sign the vendor contract until these issues are resolved.**

## 1. Direct Contradictions
* **Conflicting Appointment Durations (R-04 vs. R-05):** R-04 mandates that every appointment must last exactly 15 minutes, whereas R-05 allows doctors to set durations between 10 and 30 minutes. This must be resolved (e.g., 15 minutes as a default that doctors can override).

## 2. Ambiguous & Untestable Requirements
* **Unquantified Response Speed (R-02):** "Respond quickly" has no measurable target (e.g., `< 2 seconds` under peak load of 50 concurrent users on Monday mornings).
* **Undefined Reminder Timing (R-06):** "Before appointments" lacks a specific lead time (e.g., 24 hours and 2 hours prior) and notification channel (SMS/email).
* **Unmeasurable Accessibility (R-08):** "User-friendly for all age groups" cannot be tested objectively; it requires concrete standards (e.g., WCAG 2.1 AA, minimum 16px font, high contrast).
* **Vague Security Requirement (R-09):** "Stored securely" omits encryption standards (e.g., AES-256 at rest, TLS 1.3 in transit) and audit logging.
* **Undefined Operating Hours (R-12):** "Normal working hours" lacks specific days/times and leaves 24/7 online booking availability ambiguous.
* **External Unreferenced Policy (R-13):** "As per clinic policy" hides functional rules inside an unattached document; the SRS must explicitly state whether overdue payments block new bookings.

## 3. Compound & Incomplete Rules
* **Compound Requirement (R-07):** Combines three separate actions (patient cancellation, schedule update, receptionist notification) into one requirement, complicating testing and traceability.
* **Unrestricted Last-Minute Cancellations (R-07):** Allowing cancellations "at any time" without a cutoff window (e.g., 2 hours prior) leaves doctors with unfillable empty slots.
* **Missing Concurrency Control (R-03):** States the goal to prevent double bookings but omits slot-locking rules when a patient and receptionist book the same slot simultaneously.
* **Missing Boundary Behavior (R-11):** Caps active appointments at 3 without defining the error message or receptionist override procedure when a 4th booking is attempted.

## 4. Missing Stakeholder Capabilities
* **No Emergency Walk-In Priority (R-10):** Receptionists can book walk-ins, but there is no mechanism to prioritize urgent emergencies or reserve buffer slots.
* **Missing Doctor & Admin Controls (R-12, R-14):** Doctors can only view schedules (R-14) without blocking off breaks/leave, and no requirement lets the Clinic Administrator update working hours or manage user roles (Data Protection Officer concern).

## 5. Reconciliation of Uncertain Items 
* **CL-007 (Cancellation cutoff):** Student B marked  wondering if "at any time" was intentional; both agreed it creates a major financial risk of last-minute no-shows and must be flagged.
* **CL-013 (Doctor schedule blocking):** Student A marked  to confirm if blocking time belonged in another section; both confirmed no such requirement exists anywhere in the SRS.
* **CL-014 (Admin working hours) & CL-016 (4th booking behavior):** Both partners confirmed these omissions create untestable edge cases for administrators and patients.
