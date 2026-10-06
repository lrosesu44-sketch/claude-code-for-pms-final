# Consolidated draft messages: one per person (not sent)

Drafted 6 Oct 2026. This set replaces the drafts in `4-2-follow-up-drafts.md`, `nadia-ravi-questions.md` and `follow-up-questions-outages-and-sources.md`. No emails have been sent. Before sending, add your name, dates and meeting times.

Data referenced: rook-database (callouts and pings to 6 Sep, tickets to 7 Sep), the four September interviews, and the 4.2 page comments.

**Suggested order:** Nadia and Ravi first (they hold the newest data), then Marcus and Wen, then Sofia, Halloran and Helen.

**Corrections from the earlier Marcus and Wen draft:**
- It said the handlers of the four starved responders were the ones writing in about phones that never go off. Only Farlight's and The Undertow's handlers filed those tickets. Vesper's and Meteor Mite's handlers raised it in interviews and filed none.
- It didn't mention Halfmoon and Corporal Ashgrove, whose handlers filed "quiet" tickets but whose pings dropped only about 20%.

---

## 1. To Nadia Hoffmann

**Subject:** Tickets since 7 Sep, and a few things I can't tell from the data (15 minutes?)

Hi Nadia,

I'm the new PM for Dispatch. I've been through the ticket extract (it stops on 7 Sep) and your notes on the 4.2 page. I'd like your read before I draw conclusions. The first three matter most.

1. **Tickets since 7 Sep, by week.** Rough counts are fine, split between "phone never goes off" and "gone before I could answer", plus anything new. The latest tickets in my extract still describe responders with almost no pings (The Undertow had one in seven days).
2. **The handler who emailed you directly on 26 Aug.** You said that never happens. Could you share what they said, or the gist, in whatever way you're comfortable with? It isn't in the wiki.
3. **Which responders keep coming up.** In the extract, the handlers for Farlight, The Undertow, Corporal Ashgrove and Halfmoon filed "quiet" tickets. Handlers for Vesper and Meteor Mite told our designer the same in interviews but filed none. Have you heard from them or others outside the ticket queue?
4. **What "about 3x normal" meant.** I can't reproduce it from the extract, which shows almost no callout-type tickets before 12 Aug. What was the baseline, and how did you count?
5. **Repeated ticket text.** The 147 tickets have only 96 distinct subject lines, with identical wording from different handlers. Is that a template, a macro or copy-and-paste? I want to know how much weight the counts can bear.
6. **Do handlers know the ping wait changed?** Two tickets (3047 on 14 Aug and 3065 on 19 Aug) ask "Is there a set amount of time before it moves on?" Have handlers been told it went from 90 to 60 seconds? If not, I'd like to agree the wording with you.
7. **Outages.** Did any handler mention an app error, an outage, slow notifications or a signal problem from 12 Aug on?
8. **Routing overrides.** The March one-pager says you'd hit complaints where nobody could confirm an override happened, and the 4.0 notes say an audit log shipped. Can you confirm one now?
9. **Leave.** The console has no leave status, and two tickets ask for one. How do handlers tell you a responder is away, and does anyone track it?

Could we take a standing 15 minutes, say [day/time]?

Thanks,
[Your name]

---

## 2. To Ravi Menon

**Subject:** Dispatch acceptance numbers 7 Sep to date, and a few checks on definitions

Hi Ravi,

I'm the new PM for Dispatch. I've been working from the database extract (callouts and pings stop on 6 Sep). Could you send the following, ideally by [date]? A rough cut is fine, and a partial answer sooner is better. The first three matter most.

1. **Weekly acceptance, 29 Jun to date.** Please give taken, turned down and missed separately. In the extract it stepped down in the week of 10 Aug (54%) and was about 73% for 31 Aug-6 Sep. The drop is almost entirely missed pings.
2. **Pings per responder per week, with each responder's missed share.** All responders, especially:
   - Vesper, Farlight, The Undertow and Meteor Mite: down from about 11-14 pings a week to 3-5, with 53-64% missed after 4.2.
   - Halfmoon and Corporal Ashgrove: down about 20%, with 14-15% missed. Their handlers have filed tickets, so I want to see whether they sit with the first four or the rest.
3. **Response time per ping.** Seconds from ping sent to answer, or to timeout. The extract has no such column, so I can't test the 90-to-60 second wait directly. If it isn't recorded, is any push delivery or receipt logged?
4. **Acceptance and unfilled callouts by area.** Unfilled means no ping was taken. The extract shows each area with one responder (Eastgate two).
5. **Last year's weekly acceptance, July to September**, and who holds it if it isn't you.
6. **How the weekly figure is built.** Does a re-sent ping count as a new ping? 4.2 fixed a duplicate-push bug on re-sent pings, so counts may shift around that date. Are responders marked unavailable or on leave excluded from "offered"?
7. **Availability and leave.** Is there any availability, tag or leave data in the warehouse that isn't in the extract?
8. **Routing overrides, if logged.** How often a handler picked someone other than the recommended responder, by week.

Thanks,
[Your name]

---

## 3. To Marcus Oyelaran and Wen Li

**Subject:** 4.2: what the data shows, a few questions, and any release-week incidents

Hi both,

I've spent my first weeks going through the 4.2 picture. I'd like your read before I decide anything. This is from the database extract, which ends 6 Sep.

**What I found**
- **Acceptance stepped down in the week 4.2 shipped.** Flat at 75-78% from late June, 54% in the week of 10 Aug, and about 73% by 31 Aug. A step in release week doesn't look like a gradual seasonal dip, though I can't rule seasonality out without last year's data.
- **The drop is in missed pings, not turned-down ones.** Missed pings went from 2-6 a week to 38, 28, 24 and 21. Turned-down pings stayed flat. For the 12 responders not starved, missed pings went from about 2% to about 14%. That points to the ping wait cut from 90 to 60 seconds.
- **Four responders have been starved of pings.** Vesper, Farlight, The Undertow and Meteor Mite went from about 11-14 pings a week to 3-5, with 53-64% of their pings missed after 4.2. Their turn-down rates are normal, and in the first week of September they got 0 or 1 ping each. Several other responders now get more pings than before.
- **Two others look milder.** Halfmoon and Corporal Ashgrove are down about 20%, with 14-15% missed. Their handlers have filed "quiet" tickets.
- **Pings to a responder from the callout's own area fell from 83% to 61%.** I expected proximity weighting to push that up. Area is where a responder usually covers, not live location, so I'm not leaning on it.

**Questions**
1. **Marcus, your 14 Aug question:** was the ranking change meant to apply the same way to responders who miss or turn down pings? The starved four turn down normally and miss far more, so I think the issue is misses, not turn-downs. If it fell out that way, I'd like to treat it as an open design choice.
2. **Wen:** does a missed ping lower a responder's recent-acceptance score as much as a turned-down one? Is there any floor, decay or reset that stops a responder with a few misses from ending up unoffered for days?
3. **Both:** why might those four miss so often? I can't tell whether it's push delivery, the shorter wait or their usual response times. Could we look at delivery and timing for them specifically?
4. **Release week.** Missed pings jumped on release day, 12 Aug (7 of 25), and peaked on 13 Aug (12 of 25, across 8 responders), with smaller bumps on 19, 21 and 23-24 Aug. They are spread across the day, so I don't see an outage pattern, but my data can't show delivery. Was there any incident, degraded service or deploy problem in those windows? A link to the incident log is enough.
5. **Push delivery and receipt data** for those dates and for the four responders, if engineering can pull it.
6. **Email delays.** Two tickets (14 and 22 Aug) report password reset emails taking nearly an hour. Probably unrelated, but 14 Aug is the day after the worst missed-ping day. Was there an email or auth provider issue?
7. **Wen:** has push delivery changed since 4.1's reliability work? Could the 4.2 duplicate-push fix have changed how a missed ping is recorded?

**What I'm leaning towards (not decided)**
- Test a ping wait of 75 or 90 seconds. It's one config value and it isn't "reverting 4.2".
- Weight missed pings less than turn-downs in the recent-acceptance score, or let them age out faster.
- Keep the proximity weighting as it is.

Could we set aside 30 minutes this week? Wen, I'd also like to start writing down how ranking works, and this is a good place to begin. Nothing here needs a change before we've talked.

Thanks,
[Your name]

---

## 4. To Sofia Marino

**Subject:** Could we add a few follow-up conversations to the September research?

Hi Sofia,

I've read the four September interviews alongside the ticket extract. They barely overlap: the four interviewees filed one ticket between them, and the handlers who filed the most "quiet" tickets (for Farlight, The Undertow, Corporal Ashgrove and Halfmoon) weren't interviewed. We also haven't heard from a quartermaster. Could you help with these?

1. **Short follow-ups (15 minutes each)** with the handlers for Farlight (Linda Pruitt), The Undertow (Desmond Okafor), Halfmoon (Simone Fischer) and Corporal Ashgrove (Yusuf Demir), and Aunt Dot and Kip if they're willing. I'd like to hear in their words what the quiet weeks look like.
2. **One question, kept generic:** "Is the ping wait long enough for your responder to answer safely and comfortably, or do they sometimes need more time?" Please don't ask why, and don't ask anything that could point to a responder's identity. Security Policy 4.1 rules that out.
3. **A Supply voice.** Is there a quartermaster you could talk to about requisitions, failure reports and maintenance scheduling?

Thanks,
[Your name]

---

## 5. To Halloran

**Subject:** Maintenance scheduling since mid-August

Hi Halloran,

Thanks again for your time on 5 Sep. You said maintenance scheduling had gotten smarter about busy periods. Since then I've seen four tickets from other handlers (15 Aug to 2 Sep) about servicing booked on the city marathon day and reminders arriving after the service date. Could you tell me:

1. Has anything been booked badly for Sgt. Bulwark since the middle of August?
2. Who is the right quartermaster contact for how maintenance dates are chosen?

Thanks,
[Your name]

---

## 6. To Helen Achebe

**Subject:** Q3 commitments, and who in Supply to talk to

Hi Helen,

Two things, starting with the one I'd like to agree first.

1. **Q3 commitments.** Which still stand? Availability Confidence was committed for 4.2 but isn't in the 4.2 notes. 4.3 has requisition approval chains, and handler feedback says the approval queue is already too slow, so I'd like your view before I defend adding a second step to it.
2. **Supply contact.** Who is the right person in Supply for requisition approvals, failure-report follow-up and maintenance scheduling? None of the research so far includes a quartermaster.

Could we find 30 minutes this week?

Thanks,
[Your name]
