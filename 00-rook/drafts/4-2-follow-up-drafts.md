# 4.2 follow-up: draft messages (not sent)

> **Superseded by `consolidated-drafts.md`.** Use that file.

Drafted 6 Oct 2026. Add your name and a date before sending. Data referenced is from the rook-database extract, which ends 6 Sep (tickets 7 Sep).

---

## 1. To Ravi Menon

**Subject:** Dispatch acceptance numbers, 7 Sep to date

Hi Ravi,

I'm the new PM for Dispatch. I've been through the database extract (it stops on 6 Sep) and want to see how things have moved since. Could you send the following when you have a chance, ideally by [date]?

1. **Weekly acceptance, 7 Sep to date.** Please split taken, turned down and missed, not just the headline rate. I'd also like the weeks since 29 Jun in the same format so I can line it up with the pre-4.2 baseline.
2. **Pings per responder per week.** I'd like to see whether the responders who got far fewer pings after 4.2 (Vesper, Farlight, The Undertow, Meteor Mite) have recovered.
3. **Acceptance and unfilled callouts by area.** Unfilled means no ping was taken.
4. **Response time per ping**, if it's recorded: seconds from ping sent to answer, or to timeout. The extract doesn't include it, and I'd like to see how people answer against the 60-second wait.
5. **Last year's weekly acceptance for July to September**, if you have it, so we can judge how much of the dip is normal seasonality.
6. **Routing overrides**, if they're logged: how often a handler picked someone other than the recommended responder, by week.

If any of these aren't available, tell me and I'll work around it. A rough cut is fine, and I'd rather have a partial answer sooner.

Thanks,
[Your name]

---

## 2. To Nadia Hoffmann

**Subject:** Callout ticket themes since 7 Sep, plus 15 minutes?

Hi Nadia,

I'm the new PM for Dispatch. I read your notes on the 4.2 release page and have seen the ticket extract up to 7 Sep. Could you help with two things?

1. **Your ticket breakdown from 7 Sep to date.** I'm interested in the split you were tracking: "phone never goes off" against "gone before I could answer". Rough weekly counts are enough. Please also say whether any responders keep coming up by name.
2. **A standing 15 minutes.** I'd like to hear what handlers are saying first-hand before I make recommendations. Would [day/time] work?

One thing it would help to know now: have any handlers been told anything about the ping wait or the ranking change, and if so, what? I want to be consistent in what we say to them.

Thanks,
[Your name]

---

## 3. To Marcus Oyelaran and Wen Li

**Subject:** 4.2: what the data shows, and three questions

Hi both,

I've spent my first weeks going through the 4.2 picture. I want to share what I found and get your read before I decide anything. This is from the database extract, which ends 6 Sep, so I haven't seen anything newer.

**What I found**
- **Acceptance stepped down in the week 4.2 shipped.** It had been flat at 75-78% since late June, fell to 54% in the week of 10 Aug, and was back to about 73% by the week of 31 Aug. September is recovering but isn't back to baseline. I can't rule seasonality out without last year's data, but a step in release week doesn't look like a gradual seasonal dip.
- **The drop is in missed pings, not turned-down ones.** Missed pings went from 2-6 a week to 38, 28, 24 and 21. Turned-down pings stayed flat or fell. That points to the ping wait cut from 90 to 60 seconds as the main driver of the headline number.
- **Four responders have been starved of pings.** Vesper, Farlight, The Undertow and Meteor Mite went from about 11-14 pings a week to 3-5. Between 53% and 64% of their pings were missed after 4.2, against 10-18% for everyone else. Their turn-down rates before 4.2 were normal. In the first week of September they got 0 or 1 ping each. Several other responders now get more than before. Their handlers are the ones writing in about phones that never go off.
- **Pings to a responder from the callout's own area fell from 83% to 61%.** I expected proximity weighting to push that up, so I'm unsure what it means. Area is where a responder usually covers, not their live location, so I'm not leaning on it.

**Questions**
1. **Marcus, your 14 Aug question:** was the ranking change meant to apply the same way to responders who miss or turn down pings? I couldn't find a decision. If it fell out that way, I'd like to treat it as an open design choice.
2. **Wen:** does a missed ping lower a responder's recent-acceptance score as much as a turned-down one? And is there any floor, decay or reset that stops a responder who misses a few pings from ending up unoffered for days?
3. **Both:** why might those four miss so often? I can't tell from the data whether it's slow or failing push delivery, the shorter wait, or their usual response times. Can we look at delivery and timing for them specifically?

**What I'm leaning towards (not decided)**
- Test a ping wait of 75 or 90 seconds. It's one config value and it isn't "reverting 4.2".
- Weight missed pings less than turn-downs in the recent-acceptance score, or let them age out faster.
- Keep the proximity weighting as it is. It was a long-requested change and I don't want to undo it.

I'd value a push-back. Could we set aside 30 minutes this week to go through it? Wen, I'd also like to start writing down how ranking works, and this is a good place to begin. Nothing here needs a change before we've talked.

Thanks,
[Your name]
