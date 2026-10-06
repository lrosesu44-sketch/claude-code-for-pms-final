# Follow-up questions: source gaps, outages, and answering constraints (drafts, not sent)

> **Superseded by `consolidated-drafts.md`.** Use that file.

Drafted 6 Oct 2026. Add your name, dates and meeting times before sending. These add to `4-2-follow-up-drafts.md` (Marcus and Wen) and `nadia-ravi-questions.md` (Nadia and Ravi), which are also unsent. Where a message below overlaps with those, send one combined message, not two.

Data referenced: rook-database (callouts and pings to 6 Sep, tickets to 7 Sep) and the four September interviews.

---

## 1. To Marcus Oyelaran, cc Wen Li

**Subject:** 4.2 release week: any incidents, and push delivery data?

Hi Marcus,

I'm trying to rule out anything outside our control around the 4.2 release. In the ping data, missed pings jumped on release day, 12 Aug (7 of 25), and peaked on 13 Aug (12 of 25, across 8 responders). They stayed elevated through 16 Aug. Missed pings are spread across the day, not clustered in a window, so I don't see an outage pattern, but my data can't show delivery. You said 4.2 "went clean, no rollback, no overnight pages". Could you help with these?

1. **Incidents.** Was there any incident, degraded service or deploy problem from 12 to 16 Aug, or on 19, 21 and 23-24 Aug (smaller bumps)? A link to the incident log is enough.
2. **Push delivery and receipt.** Can engineering pull delivery and receipt data for those dates? In particular I'd like to see it for Vesper, Farlight, The Undertow and Meteor Mite, who went from about 11-14 pings a week to 3-5 and missed 53-64% after 4.2.
3. **Email delays.** Two tickets (14 and 22 Aug) report password reset emails taking nearly an hour. I expect it's unrelated to push, but 14 Aug is the day after the worst missed-ping day. Was there an email or auth-provider issue?
4. **Wen:** has push delivery changed since 4.1's reliability work? 4.2 also fixed a duplicate-push bug on re-sent pings. Could that have changed how a missed ping is recorded?

If the answer to all of these is "nothing", that's useful to know. It would make the ping wait cut and the ranking change the main suspects.

Thanks,
[Your name]

---

## 2. To Nadia Hoffmann (add to the existing Nadia draft)

**Subject:** (add to my earlier note) Two more things about handlers and outages

Hi Nadia,

Two additions to my earlier questions:

1. **Do handlers know the ping wait?** Two tickets (3047 on 14 Aug and 3065 on 19 Aug) say a phone went off and the job had moved on, and ask "Is there a set amount of time before it moves on?" Have handlers been told it changed from 90 to 60 seconds? If not, could we tell them? I'd like to agree the wording with you first.
2. **Outages.** Did any handler mention an app error, an outage, slow notifications or a signal problem, by phone, email or chat, from 12 Aug on? Nothing in the tickets says so, but I'd like to be sure.

Thanks,
[Your name]

---

## 3. To Sofia Marino

**Subject:** Could we add a few follow-up conversations to the September research?

Hi Sofia,

I've read the four September interviews alongside the ticket extract. The interviews and tickets barely overlap. The four interviewees filed one ticket between them, and the handlers who filed the most "quiet" tickets (for Farlight, The Undertow, Corporal Ashgrove and Halfmoon) weren't interviewed. We also haven't heard from a quartermaster. Could you help with two things?

1. **Short follow-ups (15 minutes each).** With the handlers for Farlight (Linda Pruitt), The Undertow (Desmond Okafor), Halfmoon (Simone Fischer) and Corporal Ashgrove (Yusuf Demir), plus Aunt Dot and Kip if they're willing. I'd like to hear in their words what the quiet weeks look like and whether the 60-second wait leaves enough time to answer.
2. **One question for each, kept generic:** "Is the ping wait long enough for your responder to answer safely and comfortably, or do they sometimes need more time?" Please don't ask why, and don't ask about anything that could point to a responder's identity. Security Policy 4.1 rules that out.
3. **A Supply voice.** Is there a quartermaster you could talk to about the requisition queue, failure reports and maintenance scheduling?

Thanks,
[Your name]

---

## 4. To Halloran (maintenance scheduling)

**Subject:** Maintenance scheduling since mid-August

Hi Halloran,

Thanks again for your time on 5 Sep. You said maintenance scheduling had gotten smarter about busy periods. Since then I've seen four tickets from other handlers (15 Aug to 2 Sep) about servicing booked on the city marathon day, and reminders arriving after the service date. Could you tell me:

1. Has anything been booked badly for Sgt. Bulwark since the middle of August?
2. Who is the right quartermaster contact for questions about how maintenance dates are chosen?

Thanks,
[Your name]

---

## 5. To Helen Achebe (one line, if the quartermaster contact isn't clear)

Hi Helen,

Who is the right person in Supply to talk to about requisition approvals, failure-report follow-up and maintenance scheduling? None of the research so far includes a quartermaster, and I'd like to include one before we agree what stands for 4.3.

Thanks,
[Your name]
