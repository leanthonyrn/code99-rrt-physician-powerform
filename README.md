# Code 99 and Rapid Response Physician PowerForms — Proof of Concept

**[Launch the live demo](https://leanthonyrn.github.io/code99-rrt-physician-powerform/)**

A browser-based proof of concept for physician documentation after a Code 99 (Code Blue) or Rapid Response (RRT) event. It shows two Oracle Health PowerForms, **Code 99 Note – Physician** and **RRT Note – Physician**, built from one set of shared fields. The demo lets reviewers try the design before it goes to the build team: fill in the form, watch the conditional logic, and read the physician note it produces.

This is the physician companion to the nursing [Code Blue and Rapid Response Post-Event Documentation Builder](https://github.com/leanthonyrn/code-rapid-response-builder). Nursing records stay the source for times, medications, shocks and vital signs. The physician form records the physician's own decisions and nothing else.

## What it demonstrates

- **Minimum data set.** Each field names who uses its data. Anything the Recording Nurse, the RRT flow sheet or iView already records is referenced, not typed again. The Code 99 form has 20 fields and the RRT form has 18. Many of them appear only when they apply, so a typical note takes about 12–14 entries, three of them free text.
- **Shared fields, separate forms.** Thirteen shared fields (S1–S13) are built once and used in both forms. There are 7 Code 99 fields (C1–C7) and 5 RRT fields (R1–R5). A code and a rapid response are never combined into one record.
- **Conditional logic like a PowerForm.**
  - ROSC shows the immediate post-cardiac-arrest assessment, disposition and plan.
  - Expired shows the reason resuscitation stopped and the time of death.
  - On the RRT note, escalation to Code 99 ends the note and opens the Code 99 note with location, role and code status already filled in.
  - Choosing "Other" opens a text box that becomes required.
- **Documentation integrity.**
  - The event time (PowerForm "Performed on") is kept separate from the signature time.
  - The code status check is never pre-selected.
  - The form never adds an attestation the physician didn't make, and it places no orders.
  - Airway and vascular access items flag that a separate procedure note is required.
- **Three output views.**
  - The generated physician note.
  - A build map listing each field's control type, values, conditional rule and who uses its data.
  - A crosswalk showing which record owns each data element.

## How to use it

1. Open the live demo and accept the privacy acknowledgment.
2. Choose **Code 99 Note** or **RRT Note**, or open **Build Map & Crosswalk**.
3. Use **Load Demo Case** to fill in a fictional example, or enter fictional values yourself.
4. Select **Sign / Review** to see the generated note. Required fields still missing are listed and block signing.

## Privacy

Runs entirely in your browser. No PHI is collected, transmitted or stored. There are no accounts, no cookies, no network calls and no external libraries. Session data exists only in the open tab. The generated note is scanned for patterns that look like dates, phone numbers, SSNs or record numbers, with a warning if any appear. Use fictional data only.

## Status

Version 0.1, a proof of concept for committee review. It is not validated and not a medical record. Final field definitions, policy language and Oracle Health build feasibility are still pending. This version expires May 31, 2027.

## Use, forking and contributions

Open source under the MIT License. Free to use, adapt, fork and redistribute with attribution retained, including for institutional use. Bug reports and field requests are welcome through Issues. Pull requests are welcome.

## Disclaimer

This is an educational demonstration of an informatics design pattern, built and published as a personal project. It is not medical software, not a medical device and not clinical decision support. Generated text is a draft. Clinicians are solely responsible for documentation filed in any patient record and for compliance with institutional policy. Use only with fictional data. This application and the views expressed are my own and do not represent my employer.

LeAnthony Mathews, RN, MBA-IT, MS-I, CPHIMS - [GitHub](https://github.com/leanthonyrn) - leanthonyrn@gmail.com
