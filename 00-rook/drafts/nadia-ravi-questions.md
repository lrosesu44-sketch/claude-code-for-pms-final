# Questions for Nadia and Ravi (draft, not sent)

> **Superseded by `consolidated-drafts.md`.** Use that file.

Drafted 6 Oct 2026. These replace the Ravi and Nadia drafts in `4-2-follow-up-drafts.md`, which are unsent. They add what the tickets, interviews and database comparison turned up since. Add your name, dates and a meeting time before sending. The Marcus and Wen draft in the old file still stands.

Data referenced: rook-database (callouts and pings to 6 Sep, tickets to 7 Sep), the four September interviews, and the 4.2 page comments.

---

## 1. To Nadia Hoffmann

**Subject:** Tickets since 7 Sep, and a few things I can't tell from the data (15 minutes?)

Hi Nadia,

I'm the new PM for Dispatch. I've been through the ticket extract (it stops on 7 Sep) and your notes on the 4.2 page. I'd like your read before I draw conclusions. Could you help with these? The first three matter most.

1. **Tickets since 7 Sep, by week.** Rough counts are fine, split between "phone never goes off" and "gone before I could answer", plus anything else that's new. My extract ends on 7 Sep, and the most recent tickets still describe responders who had almost no pings (for example The Undertow, one ping in seven days).
2. **The handler who emailed you directly on 26 Aug.** You said that never happens. Could you share what they said, or the gist, in whatever way you're comfortable with? It isn't in the wiki.
3. **Which responders keep coming up.** In the extract, the handlers for Farlight, The Undertow, Corporal Ashgrove and Halfmoon filed "quiet" tickets. Handlers for Vesper and Meteor Mite told our designer the same thing in interviews but filed no tickets. Have you heard from them or others outside the ticket queue?
4. **What "about 3x normal" meant.** I can't reproduce it from the extract: it shows almost no callout-type tickets before 12 Aug. What was the baseline, and how did you count?
5. **Repeated ticket text.** The 147 tickets have only 96 distinct subject lines, and many have identical text from different handlers (for example "Dark mode, again" and the vest-plate ticket). Is that a template, a macro or copy-and-paste? I want to know how much weight the counts can bear.
6. **Routing overrides.** The March one-pager says you'd hit complaints where nobody could confirm an override happened. The 4.0 notes say an audit log shipped. Can you confirm one now, and have you needed to since?
7. **Leave.** The console has no leave status. Two tickets ask for one. How do handlers tell you a responder is away, and does anyone track it anywhere?

Separately, have handlers been told anything about the ping wait or the ranking change? I want to be consistent in what we say.

Could we take a standing 15 minutes, say [day/time]?

Thanks,
[Your name]

---

## 2. To Ravi Menon

**Subject:** Dispatch acceptance numbers 7 Sep to date, and a few checks on definitions

Hi Ravi,

I'm the new PM for Dispatch. I've been working from the database extract (callouts and pings stop on 6 Sep). Could you send the following, ideally by [date]? A rough cut is fine, and a partial answer sooner is better than a full one later. The first three matter most.

1. **Weekly acceptance, 29 Jun to date.** Please give taken, turned down and missed separately, not just the headline rate. In the extract it stepped down in the week of 10 Aug (54%) and was about 73% for 31 Aug-6 Sep. The drop is almost entirely missed pings, not turned-down ones.
2. **Pings per responder per week, with each responder's missed share.** All responders, but especially:
   - Vesper, Farlight, The Undertow and Meteor Mite: they went from about 11-14 pings a week to 3-5 after 4.2, with 53-64% of pings missed.
   - Halfmoon and Corporal Ashgrove: down about 20%, with 14-15% missed. Their handlers have been filing tickets, so I want to see whether they sit with the first four or with everyone else.
3. **Response time per ping.** Seconds from ping sent to answer, or to timeout. The extract has no response-time column, so I can't test the 90-to-60 second ping wait directly. If it isn't recorded, is anything logged about push delivery or receipt?
4. **Acceptance and unfilled callouts by area.** Unfilled means no ping was taken. The extract says each area has one responder (Eastgate two), so I'd like to see it split by area.
5. **Last year's weekly acceptance, July to September**, and who holds it if it isn't you. I can't tell seasonality from a step in release week without it.
6. **How the weekly figure is built.** Does a re-sent ping count as a new ping? 4.2 fixed a duplicate-push bug on re-sent pings, so counts may shift around that date. Are responders marked unavailable or on leave excluded from "offered"?
7. **Availability and leave.** Is there any availability, tag or leave data in the warehouse that isn't in the extract? The responders table has only name, handler and area.
8. **Routing overrides, if logged.** How often a handler picked someone other than the recommended responder, by week.

If any of these aren't available, tell me and I'll work around it.

Thanks,
[Your name]
