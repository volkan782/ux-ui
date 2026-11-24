---
week: 2
neptun: C09332
---

# Homework 2 — User research, persona, and user journey

## Status: Completed — one participant, exploratory findings

[Barber Booking — Homework 2: FigJam research board](https://www.figma.com/board/HXGTBORGvPtG4K8eBLLKtx/Barber-Booking-%E2%80%94-Homework-2)

## Research plan

**Design decision:** Which service information, availability choices, and confirmation details should the booking flow prioritize?

**Research questions:** How do customers currently arrange appointments? What information matters when choosing a service and time? What difficulties, if any, arise and how are they handled? How do customers recognize a confirmed booking?

**Assumption investigated:** Homework 1 proposes that calls/messages cause significant difficulties. Seek contradictory evidence as well as support; do not presume this claim is true.

**Method:** One interview about the participant's last actual barber booking, using seven open questions. The student supplied the written responses and confirmed they came from a real person. The plan allowed 10–15 minutes; actual duration, interview date, and exact booking date were not recorded.

**Participant P1:** Returning customer of a familiar barber; arranges appointments using Instagram messages; knows approximate pricing from a previous visit. No name, contact details, age, or device were collected in the supplied material. The participant's relevance follows from their reported booking experience.

**Data handling and consent:** The student confirmed the participant agreed to anonymous answers being included in the public GitHub repository and shareable FigJam board. The briefing permits skipping questions and stopping. Use anonymous written notes, not recordings or private screenshots.

**Limitations:** One retrospective self-report, not direct observation of booking behavior. It cannot establish prevalence, the severity for other customers, or measured usability. Exact timing and demographics are unknown. The responses are student-supplied accounts, not an independently verified transcript.

## Evidence legend

- **O1–O7:** Participant-reported accounts, kept separate from direct observation. Answers below are supplied written summaries; no verbatim quotation is claimed.
- **Q:** Reserved for an exact recorded quotation. None used in this submission.
- **I1–I3:** Researcher interpretations tied to source IDs.
- **D1–D2:** Proposed design directions, not tested improvements.
- Unverified details are identified as unknown or assumptions.

## Interview questions and supplied answers

### O1 — Booking channel

**Question:** How did you book your last haircut — phone, messages, website, or another way?

**Supplied answer:** I booked my last haircut by sending a message to the barber on Instagram. I asked if he had any available appointments that week.

### O2 — Actual sequence

**Question:** What happened step by step, from deciding to get a haircut until the booking was confirmed?

**Supplied answer:** First, I noticed my hair was getting too long, so I decided to get a haircut. I checked my barber's Instagram page and sent him a message asking about available times. He replied with a few options. I chose the one that worked best for me, and he confirmed my appointment.

### O3 — Information needed

**Question:** What information did you need, such as price, service, or available times? How did you find it?

**Supplied answer:** I mainly wanted to know the price, available times, and whether he could do the haircut I wanted. I already knew the approximate price from my previous visit, but I asked him about the available times through Instagram.

### O4 — Appointment availability

**Question:** How did you find a suitable appointment time? What happened if your preferred time wasn't available?

**Supplied answer:** I told him which day I was free and asked what times he had available. The time I originally wanted was already taken, so he suggested another time later that day. It wasn't perfect, but I accepted it.

### O5 — Difficulty and workaround

**Question:** Was anything difficult or unclear? If everything went smoothly, what worked well?

**Supplied answer:** The main problem was waiting for a reply. I couldn't see his available appointments myself, so I had to wait for him to message me back. It would have been easier if I could just see all the available times online.

### O6 — Confirmation

**Question:** How did you know your appointment was confirmed?

**Supplied answer:** The barber sent me a message confirming the day and time. I didn't receive any email or automatic reminder, so I just kept the Instagram conversation to remember my appointment.

### O7 — Feelings and stated preference

**Question:** How did you feel during the process, and why?

**Supplied answer:** Overall, I felt okay because I already knew the barber and trusted him. However, waiting for replies was a little annoying. I would prefer a website where I could choose a time, see the price, and confirm everything immediately without having to message anyone.

## Affinity map

The FigJam board groups source notes by theme and distinguishes evidence from interpretation.

| Theme | Source notes — reported accounts | Interpretation |
| --- | --- | --- |
| Availability and delay | O1: asks for appointments by message. O4: preferred slot taken, accepts another. O5: waits for replies and cannot see slots independently. | **I1:** Choosing an available time depends on an exchange of messages. |
| Decision information | O3: needs price, availability, and haircut suitability; has approximate price knowledge. | **I2:** Price and service details are relevant to choosing an appointment; existing familiarity partly compensates for missing information. |
| Trust and confirmation | O6: confirmed day/time is retained in the conversation. O7: trusts the familiar barber and feels okay overall. | **I3:** Confirmation works, but the booking record is embedded in a conversation rather than a dedicated summary. |

O2 supplies the sequence for the journey map. Notes sharing a source are not counted as separate participants.

## Two design-relevant insights

### Insight A — Make availability understandable before confirmation

**Observation/report (O4, O5):** P1's preferred time was taken. They waited for replies to obtain alternatives and described that waiting as annoying.

**Interpretation (I1):** The difficulty concerns access to availability and coordination, rather than evidence that P1 cannot complete a booking.

**Design consequence (D1, untested):** Show bookable times and alternatives before confirmation. Test whether users can choose a suitable available slot without help. Accurate availability remains an operational assumption for the prototype.

### Insight B — Preserve clarity and make details easy to retrieve

**Observation/report (O6, O7):** P1 received a day/time confirmation, retained the Instagram conversation, and trusted the familiar barber.

**Interpretation (I3):** A clear confirmation already exists. A dedicated booking summary could make details easier to retrieve, but P1 did not report a lost booking, missed appointment, or failed confirmation.

**Design consequence (D2, untested):** Provide an explicit confirmation and persistent summary including service, price, date, and time. Check whether users correctly understand the booking and can locate those details. Do not claim reminders are necessary solely because none were received.

## Research-based persona

**P1 — Returning barber customer.** A task-focused persona based on one interview, not a representative demographic profile.

| Required field | Description | Evidence |
| --- | --- | --- |
| Situation | Arranging a haircut with an existing barber through Instagram messaging. | O1, O2, O7 |
| Goal | Find a suitable service and appointment time, and know the booking is confirmed. | O2, O3, O4, O6 |
| Knowledge | Familiar with the barber, Instagram messaging, and approximate previous pricing. Device and age unknown. | O1, O3, O7 |
| Constraint | Preferred time unavailable; availability depends on the barber's replies. | O4, O5 |
| Risk | **Interpretation:** Extra coordination and later retrieval of details from the conversation. No actual lost booking was reported. | I1/I3, O5/O6 |

P1's preference for a website is a reported preference, not proof that a proposed website is usable. Broader adoption and other customers' needs remain unverified.

## User journey — arrange one haircut appointment

| | 1. Need haircut | 2. Contact barber | 3. Negotiate time | 4. Confirm | 5. Keep details |
| --- | --- | --- | --- | --- | --- |
| Steps | Decides a haircut is needed. | Checks Instagram and asks for available appointments. | Considers options; accepts a later time because preferred slot is taken. | Receives a message with confirmed day/time. | Retains the conversation as a reference. |
| Evidence | O2 | O1, O2 | O4, O5 | O6 | O6 |
| Feelings | Not separately reported. | Overall trust/feeling okay; not specifically attributed to this step (O7). | Annoyance while waiting (O5, O7). | Not separately reported. | Not separately reported. |
| Pain points | None reported. | Cannot see available slots independently (O5). | Preferred time unavailable and must wait for replies (O4, O5). | None reported; confirmation received. | Must refer to chat; no email/reminder received. No actual failure reported. |
| Improvement opportunities — untested | Clear service/price information (O3, I2). | Visible availability (D1). | Show alternative times (D1). | Explicit confirmation (D2). | Persistent booking summary (D2). |

Feelings not supplied by P1 are left unknown. Suggested opportunities are interpretations or hypotheses, not existing features or validated results.

## Lessons and effect on Homework 1 assumptions

- Availability visibility and waiting merit investigation for this participant.
- Price and service suitability matter, but P1 already knew approximate pricing.
- The current approach did complete the booking and supplied confirmation. Trust and familiarity were strengths.
- The claim of **significant difficulties for customers in general** remains unproven; P1 described mild annoyance and an overall acceptable experience.
- The next design work should investigate D1/D2, rather than treat a stated website preference as validation of the whole product.

## Existing success criterion — unchanged and not tested

Homework 1 proposes at least 4 of 5 participants completing service selection, time selection, and confirmation within 60 seconds without assistance. This interview does not test that criterion. Homework 8 requires at least three participants, but three participants cannot substantiate a 4-of-5 result.

## Verification against the official Homework 2 requirements

- [x] Separate shareable FigJam board.
- [x] Concise research plan: decision, questions, method, participant, data handling.
- [x] Anonymous participant background, questions, important answers, and lessons.
- [x] Grouped raw notes in FigJam, with reported evidence and interpretations separated; no fabricated exact quotes.
- [x] Two insights in observation → interpretation → design consequence form.
- [x] Research-based persona: situation, goal, knowledge, constraint, risk.
- [x] Journey for one task: steps, feelings, pain points, opportunities.
- [x] Unknowns, sample limitations, and untested assumptions stated.
- [x] No participant identifiers or sensitive personal data.
