---
week: 09
neptun: C09332
---
# Barber Booking — Homework 9
**Status: Deliverables and follow-up booking check recorded; five reported unaided 60-second completions meet the original target in this sample. Instructor acceptance is separate.**

[Separate Figma file](https://www.figma.com/design/R2lUWTNhtN1qjitk6AM9LK/Barber-Booking-%E2%80%94-Homework-9)
[Clickable prototype](https://www.figma.com/proto/R2lUWTNhtN1qjitk6AM9LK/Barber-Booking-%E2%80%94-Homework-9?node-id=1-4&scaling=scale-down&content-scaling=fixed&starting-point-node-id=1%3A4)

The file is in Drafts because the Starter team folder reached its three-Design-file limit. Sharing was verified as **Anyone can view**. No paid upgrade was used. The completed Homework 8 canvas was copied into this separate file. Homework 1–7 are preserved.

## Follow-up task check against the original criterion
[Full five-person record](../08/follow-up-tests.md): the student confirmed stopwatch-measured **60 seconds for each of FT1–FT5**, unaided completion, correct detail identification, confirmation recognition and unaided unavailable-date recovery. No pauses, mistakes or comments were reported.

The original criterion requires at least 4/5 within ≤60 seconds: **5/5 qualify in this reported sample**. This post-iteration task check includes the componentized appointment-summary screen; it does not isolate the effect of a component or prove keyboard accessibility. It complements, rather than replaces, the technical focus check below.

## Original evidence before the follow-up
The following describes the evidence available when the design was first submitted. Missing timing/detail outcomes at that stage are now supplemented by the linked follow-up; other limits still apply.

Homework 8 records the student's report of P1–P3: anonymous-note consent, both tasks completed without help, confirmation recognized and no unusual behavior reported. No exact quotes, timings, individual action traces, devices/dates or full appointment-detail recall were supplied.

This supports basic reported completion and recovery, not the original four-of-five-within-60-seconds target. No reported failure justifies a wholesale redesign. The iterations address reusable states and gaps in validation/handoff coverage. They are design-structure findings, not invented participant complaints. No new human test or before/after usability improvement is claimed.

## Decision log

| Iteration | Evidence / finding | Checkable hypothesis | Change | Rejected alternative / trade-off | Expected effect | Open question |
| --- | --- | --- | --- | --- | --- | --- |
| I1 — reusable actions | HW8's reported flow worked; action controls were independent frames | A native set can expose Primary, Secondary and Disabled while retaining the understood flow | Button set with three State variants, 18px labels, 16px padding and minimum 56px height | Wholesale restyling lacks evidence. A local library still requires deliberate adoption on later screens | Reduce inconsistent maintenance; preserve comprehension | Can future editors apply the correct state without guidance? |
| I2 — visible focus | HW8 did not test keyboard use; no separate focus specimen existed | A 2px outline with ≥3:1 contrast can distinguish focus from selection | DateInput Focus variant with stroke bound to focus/ring | Fill-only focus could be mistaken for selection; an outline adds visual weight | Make active input identifiable and specify implementation | Does focus remain visible with zoom and real keyboard use? |
| I3 — invalid date | Recovery worked by report, but missing-date validation and detailed actions were unstudied | Explicit default/focus/error input states and textual recovery rules reduce implementation ambiguity | DateInput Default / Focus / Error; Error says No date / Required; handoff defines adjacent helper and disabling Continue until date+time valid | Red-only errors or an unrelated personal-data form; selected approach stays within existing date selection | Make validation comprehensible without color and reduce guessing | Can users recover from this additional validation state unaided? |

These are state/component and handoff iterations, not three discovered usability failures.

## Check of I2 against a criterion
- Criterion: outline at least **2px**, contrast at least **3:1** against white.
- Inspected native DateInput Focus: **2px** stroke bound to **focus/ring #1A1A1A**.
- Calculated standard sRGB relative-luminance contrast against #FFFFFF: **17.40:1**.
- Result: **passes the stated width/contrast design criterion**.
- Limits: other technical evidence, not a participant retest, complete accessibility claim, keyboard implementation test or proof of faster completion.
- Next check: keyboard-enabled implementation with relevant participants, recording focus identification and unaided validation recovery.

## Mini design system — separate page
Page **02 · Mini design system** contains native reusable assets and separate usage notes.

| Asset | Native implementation | Screen relationship |
| --- | --- | --- |
| Button | Component set; State = Primary, Secondary, Disabled | Recurring booking action treatments; library standardizes reuse |
| DateInput | Component set; State = Default, Focus, Error | Existing segmented date input; added focus/error are handoff specimens |
| Card / AppointmentSummary | Main component on the date/time screen; library instance on page 02 | Existing selected-appointment summary |

Button specimens share a sample label, overridden by context when reused. Disabled has no prototype interaction. Library specimens are not a second live booking flow. Added date states are specified for implementation, not claimed as reachable user-tested routes. The date input is a segmented calendar control; no unrelated contact form was added.

### Variables
| Native name | Value | Verified use |
| --- | --- | --- |
| surface/default | #FFFFFF | Bound to selected date/time screen fill |
| text/primary | #1A1A1A | Available token; not every text node is claimed bound |
| action/primary | #1F1F1F | Bound to Primary component fill |
| focus/ring | #1A1A1A | Bound to Focus variant stroke |

Grayscale appearance, 8px spacing base, 24px group gaps, 20px mobile inset, established readable body/heading typography. Local library, not a published team library. No dark mode claim.

## Selected screen handoff
**M-S3 Choose a date and time** is marked **Ready for dev** in Figma. Mobile width 390, native vertical Auto Layout, 20px padding and 24px group gap.

| State | Design source | Required behavior |
| --- | --- | --- |
| No time selected | M-S3-0 | Chosen date, no time; Continue disabled |
| Valid selection | M-S3 | 7 Dec 2026, 10:00–11:00, Haircut, Barber A, 60 min, 600 CZK; Continue enabled |
| Empty date | M-S3-E1 | 8 Dec has no slots; clear time; explanation/recovery; Continue disabled |
| Default / focus / invalid input | DateInput variants on page 02 | Chosen day; 2px focus outline; No date / Required and adjacent helper “Choose a date with availability” |
| Action enabled / disabled | Button variants | Disabled never activates; valid selection enables Continue; review precedes success |

Changing date clears time. Selecting 10:00 updates the summary. Continue opens review, not success. Back retains service/barber. Keep price, duration and shop-local time visible. Reference E2 requires real server-conflict handling and remains outside the main flow.

### Accessibility / implementation contract
Use labeled single-choice date/time groups. Tab enters/leaves; arrow keys change options. Focus stays visible and differs from selected fill. Announce textual errors, empty availability and meaningful summary changes. Preserve explicit labels and at least 44px interaction targets in implementation. Disabled controls do not fire. Icon-only controls need accessible names. These are developer requirements, not implemented keyboard/screen-reader abilities of Figma.

Variables used are named above and on the canvas. Full screen states and component examples are cross-referenced so implementation does not depend on guessing.

## Functional verification
Actually checked in the Homework 9 player:
- Service → barber → date/time with no time selected.
- Disabled Continue did not navigate.
- 8 December opened No available slots.
- Choose another date returned to 7 December with no time selected.
- Selecting 10:00 updated the summary.
- Continue opened review with the refined five-detail reminder and correct appointment.
- Confirm opened Booking confirmed, matching details and sample reference BB-DEMO-01.
- Restart returned to the beginning.

Static alternatives remain: Beard trim, other barbers, 11:00/14:00 and 9 December. Desktop/E2 are reference designs. No live appointment, backend, payment, email or SMS.

## Concrete next step
Test a keyboard-enabled implementation with relevant users, focusing on visible focus and required-date validation. The reported follow-up now covers the booking-time/detail outcome; no further booking test is claimed or invented here.

## Official requirement verification
- [x] Separate shareable Figma file.
- [x] At least three decision-log iterations with all six required fields.
- [x] At least one modification checked against a criterion, with limitations.
- [x] Separate clear mini design system page.
- [x] Native Primary, Secondary and Disabled buttons.
- [x] Native Default, Focus and Error date-input variants.
- [x] Relevant appointment-summary component and instance.
- [x] Relevant state variants.
- [x] Selected screen, state map, behavior/accessibility notes, variable names and Ready for dev.
- [x] Concrete next step.
- [x] Follow-up task check against the original booking criterion, with source and limits recorded.
- [x] GitHub Projects task/status update completed during this evidence update.

Official source: [Homework 9](https://pte-mik.github.io/info/ux-ui-en/content/09/09-00-homework/).

Homework 10 is available in [the presentation submission](../10/README.md).

[Updated follow-up evidence in Figma](follow-up-overview.jpg)
