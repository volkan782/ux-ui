---
week: 09
neptun: C09332
---
# Barber Booking — Homework 9
**Status: Design-system deliverables and follow-up booking check recorded. Iteration evidence and chronology clarified; the test-derived scope limitation below remains open.**

[Separate Figma file](https://www.figma.com/design/R2lUWTNhtN1qjitk6AM9LK/Barber-Booking-%E2%80%94-Homework-9)
[Clickable prototype](https://www.figma.com/proto/R2lUWTNhtN1qjitk6AM9LK/Barber-Booking-%E2%80%94-Homework-9?node-id=1-4&scaling=scale-down&content-scaling=fixed&starting-point-node-id=1%3A4)

The file is in Drafts because the Starter team folder reached its three-Design-file limit. 

## Follow-up task check against the original criterion
[Full five-person record](../08/follow-up-tests.md): the student confirmed stopwatch-measured **60 seconds for each of FT1–FT5**, unaided completion, correct detail identification, confirmation recognition and unaided unavailable-date recovery. No pauses, mistakes or comments were reported.

The original criterion requires at least 4/5 within ≤60 seconds: **5/5 qualify in this reported sample**. This post-iteration task check includes the componentized appointment-summary screen; it does not isolate the effect of a component or prove keyboard accessibility. It complements, rather than replaces, the technical focus check below.

## Original evidence before the follow-up
The following describes the evidence available when the design was first submitted. Missing timing/detail outcomes at that stage are now supplemented by the linked follow-up; other limits still apply.

Homework 8 records the student's report of P1–P3: anonymous-note consent, both tasks completed without help, confirmation recognized and no unusual behavior reported. No exact quotes, timings, individual action traces, devices/dates or full appointment-detail recall were supplied.

This supports basic reported completion and recovery, not the original four-of-five-within-60-seconds target. No reported failure justifies a wholesale redesign. The iterations address reusable states and gaps in validation/handoff coverage. They are design-structure findings, not invented participant complaints. No new human test or before/after usability improvement is claimed.

## Decision log

These entries distinguish the review refinement inherited from HW8 from the HW9 component/state work. Positive findings support retaining successful behavior. Coverage gaps and technical findings are identified separately from participant observations.

| Iteration | Evidence / finding | Checkable hypothesis | Change | Rejected alternative / trade-off | Expected effect | Open question |
| --- | --- | --- | --- | --- | --- | --- |
| I1 — deliberate appointment review | Original HW8 T1 reported completion and confirmation recognition, but full detail checking was not recorded | Naming the five details beside Confirm supports deliberate review | Reminder: “Check service, barber, date, time and price above. Then confirm once.” Implemented in HW8 refinement and retained in HW9 | Another review screen adds steps without a reported need | Preserve completion while prompting an explicit detail check | Does this improve checking compared with earlier wording? The later result does not isolate its effect |
| I2 — reusable appointment summary | HW8 users reportedly completed and recognized confirmation; technical inspection found a local summary group | One reusable component can retain the understood information order and reduce inconsistent edits | Date/time summary converted to a main component; library instance demonstrates reuse; service, barber, date, time, duration and price retained | Redesigning the successful summary lacks evidence; independent copies risk divergent edits | Preserve recognition and provide a reusable detail contract | Can future editors reuse it correctly? Booking tests do not assess editing the library |
| I3 — explicit date-input states | HW8 T2 recovery worked by report; missing-date validation and keyboard focus were untested | Default/Focus/Error variants with textual recovery rules clarify invalid states and implementation | DateInput variants; 2px focus/ring outline; No date / Required; adjacent helper and Continue disabled until valid date AND time | Red-only errors rely on color; an unrelated form expands scope | Consistent recovery and non-color-only state meaning | Can users recover from missing-date validation in a keyboard-enabled implementation? Not yet user-tested |

I1 is an inherited refinement, not a new change after the five-person follow-up. I2/I3 are preservation and coverage decisions informed by positive tests and technical inspection. **The strict interpretation that all three must be new HW9 fixes directly demonstrated necessary by HW8 tests remains open.** Rewriting this log does not create additional research evidence.

## Check of I3 against a criterion
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
- [x] Three actual iteration records with all six required fields and explicit chronology/evidence sources.
- [ ] Strict test-derived iteration scope: I1 was refined in HW8; I2/I3 address reuse and untested state coverage. Three new HW9 fixes directly necessary from HW8 test problems are not claimed.
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
