---
week: 08
neptun: C09332
---
# Barber Booking — Homework 8
**Status: Updated with five reported stopwatch-measured tests; original booking target met in this sample. Instructor assessment remains separate.**

[Separate Figma file](https://www.figma.com/design/DHR5u6Y4Fr0VAX58i2DU2a/Barber-Booking-%E2%80%94-Homework-8)
[Testing prototype](https://www.figma.com/proto/DHR5u6Y4Fr0VAX58i2DU2a/Barber-Booking-%E2%80%94-Homework-8?node-id=2-2&scaling=scale-down&page-id=0%3A1&starting-point-node-id=2%3A2)

## Current result — five stopwatch-measured follow-up tests
The student explicitly confirmed that all five participants took **60 seconds each, measured with a stopwatch**, completed booking without help, identified all appointment details, recognized confirmation and handled the unavailable-date task without help. No pauses, mistakes or comments were reported.

**Result: 5/5 meet the original at-least-4/5 within ≤60-seconds target in this reported sample.** [Full follow-up record and limitations](follow-up-tests.md). This is not independent observation or a controlled before/after comparison. The original three-person notes below remain historical; participant overlap is unknown and samples are not added together.

## Test plan

**Participant background:** The student clarified that the testers book haircut appointments by phone and reported a good experience with no problems. This is a collective description of relevant booking experience, not individual profiles. Booking frequency, demographics and participant-specific differences were not recorded.

Learning goals:
1. Can relevant users book the intended appointment unaided and recognize confirmation and correct details?
2. Can they recover from a date with no available appointments?

Recruit three people who arrange their own haircuts and would plausibly use online booking. Run each separately. Anonymize as P1/P2/P3; note booking experience and consent, date/device if known. The previous Homework 7 trial is prior evidence, not three new Homework 8 tests.

### Consent / verbal briefing
“This is a student prototype, not a real booking. We are testing the design, not you. Taking part is voluntary; you can stop at any time. May I take anonymous notes about your actions and comments for my coursework?”
Record consent; stop if declined. No audio/video without separate agreement.

### Tasks
Read one task at a time without explaining the controls.

**T1:** “You want a haircut with Barber A on 7 December 2026 at 10:00, budget 600 CZK. Arrange it and tell me when you believe it is booked and what details confirm that.”

**T2, after restart:** “You want the same haircut on 8 December, but can also attend 7 December at 10:00. Arrange an appointment that works.”

### Success and metrics
T1 passes if the participant completes the correct appointment unaided, recognizes confirmation and identifies service, barber, date, time and price accurately.
T2 passes if they recover from no availability to the suitable alternative and complete unaided.
Record task outcome; elapsed seconds from task read to completion/abandonment; assistance; errors, pauses and backtracks; details identified. Record the original 60-second benchmark separately. The original sample of three could not establish the four-of-five target; the later five-person follow-up now evaluates it.
Afterward ask what was unclear and what made them believe booking succeeded. Record exact quotes only when captured; label paraphrases. Missing measurements are “not recorded,” never guessed.

## Original three-person observations — historical
Source: the student reported all three participants completed both tasks unaided, consented to anonymous notes, recognized the confirmation, and showed no unusual behavior. These are reported observations, not direct observation by the assistant. Participant-specific differences were not supplied.

| Participant | Consent | T1 | T2 | Observation | Quote | Interpretation |
| --- | --- | --- | --- | --- | --- | --- |
| P1 | Yes, reported | Completed without help | Completed without help | Recognized confirmation; no unusual behavior reported | Not captured | Basic completion and recovery supported |
| P2 | Yes, reported | Completed without help | Completed without help | Recognized confirmation; no unusual behavior reported | Not captured | Basic completion and recovery supported |
| P3 | Yes, reported | Completed without help | Completed without help | Recognized confirmation; no unusual behavior reported | Not captured | Basic completion and recovery supported |

In that original round, individual experience differences, dates/devices, elapsed seconds, exact clicks, errors counts, and complete detail-recall responses were **not recorded**. The report supports 3/3 reported completion and confirmation recognition, but **does not establish the entire T1 criterion or the original speed target**. Do not infer zero pauses/errors from “no unusual behavior.” Small convenience sample, brief second-hand records, no recordings: findings are preliminary.

## Original findings ordered by consequence
No blocker, major or minor usability defect was reported. A severity-ranked defect list would invent problems.
- **U1 — evaluation gap (not a UI defect):** full appointment detail recall and timing were not recorded. Affects evaluation of booking accuracy/speed; consequence: no full success-criterion or efficiency claim. Resolved for the reported follow-up outcome; retained here as a historical gap.
- **F1 — positive:** all three reportedly completed booking unaided and recognized confirmation. Affects T1; consequence: preserve the flow and explicit success heading.
- **F2 — positive:** all three reportedly completed the unavailable-day task unaided. Affects T2; consequence: retain the recovery path.

## Selected refinement and accessibility rationale
The review screen reminder now says: “Check service, barber, date, time and price above. Then confirm once.”
Evidence: full detail recall is unknown in HW8; HW7 also recorded direct confirmation. Hypothesis: explicitly naming the details supports deliberate review. This is a preventative comprehension refinement, not a participant-reported failure or proven improvement. It was initially checked visually for fit. The later five-person follow-up checked the post-iteration flow; no isolated improvement effect is claimed. Main flow and explicit success wording are retained because reported tests did not identify a blocker.

## Mini UI guideline in Figma
A clearly labeled guideline section documents:
- Native variables: `surface/default = #FFFFFF`, `text/primary = #1A1A1A`, `action/primary = #1A1A1A`.
- Native styles: `Body / 18` (Inter Regular 18/25) and `Heading / Section`, saved from established section headings.
- Spacing: 8px base, 24px group gaps, 20px mobile edge inset.
- Buttons: one primary per step, explicit labels, outlined secondary, no activation when disabled with adjacent reason.
- Input/selection rules: persistent labels, selected values in words, price/duration visible, implementation focus outline and textual errors.
- Icons: decorative beside labels; accessible names for icon-only controls.
- Light mode only; dark mode was optional and is not claimed.

### Contrast check
Calculated using standard sRGB relative luminance: `(Llighter + .05)/(Ldarker + .05)`.
| Pair | Ratio | Check |
| --- | --- | --- |
| #1A1A1A on #FFFFFF | 17.40:1 | AA normal text passes |
| #595959 on #FFFFFF | 7.00:1 | AA normal text passes |
| #1A1A1A on #E8E8E8 | 14.20:1 | AA normal text passes |

These checked pairs occur in the grayscale screens/annotations. This is not a complete accessibility audit, keyboard test or user retest.

## Prototype limitations
Fixed sample appointments; no live availability/backend/payment/messages. E2 slot-conflict and desktop are reference screens. Static alternatives are not fully interactive. All bookings are fictional demonstration data.

## Official requirement verification
- [x] Separate shareable Figma file and updated prototype.
- [x] Goals, participant description, scenario tasks, success criteria and metrics.
- [x] Consent briefing and reported consent.
- [x] Anonymized reported notes from three tests, with observation/quote/interpretation separate.
- [x] Findings prioritized by consequence; no invented defects or severity.
- [x] Justified review refinement supporting comprehension.
- [x] Figma role-named color variables, native text styles, spacing/button/input/icon rules and calculated contrast checks.
- [x] Evidence and measurement limitations explicit.

[Prepared test plan preview](test-preparation.jpg) · [Original layout](completed-overview.jpg) · [Timed follow-up layout](timed-tests-overview.jpg)

Official source: [Homework 8](https://pte-mik.github.io/info/ux-ui-en/content/08/08-00-homework/).
