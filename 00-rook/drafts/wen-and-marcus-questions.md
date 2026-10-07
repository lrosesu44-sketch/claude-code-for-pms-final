# Questions for Wen and Marcus (not sent)

Drafted 7 Oct 2026. These split section 3 of `consolidated-drafts.md` into two separate messages and add the Eastgate comparison from the callout-history cross-check. Wen prefers direct messages, so hers is short and technical. Marcus is the first stop for rough numbers, so his is about access and decisions. Before sending, add your name and dates.

Policy 4.1 reminder: every question about the four is about the system, not about any individual's circumstances. Nobody should be asked why a specific responder isn't answering.

---

## 1. Direct message to Wen Li

Hi Wen,

I'm the new PM for Dispatch, and I'm starting to write down how ping ranking works because nothing exists. You're the only person who can tell me how it actually behaves. Four questions, most important first. Short answers are fine.

1. **How does a missed ping feed the score?** Does it lower recent acceptance as much as a turn-down? Priya's notes and the 4.2 release notes don't say.
2. **Is there a floor, decay or reset?** In the data, Vesper, Farlight, The Undertow and Meteor Mite went from about 49 pings a week combined to 3 within three weeks of 4.2. Over the same weeks the other 12 went from about 123 to 162. The four were normal until the release week (take rate 74-80%). Can a responder with a short run of misses end up with nobody pinging them, and stay there?
3. **Did 4.2 change the recent-acceptance window or weight?** I know proximity was weighted up. Was the history input changed too, or only its share of the total?
4. **How are required tags set on an incident?** The database has no tags, so I can't see whether tags explain who gets skipped.

Two smaller things I'd like to understand:

- In the data, the share of pings going to a responder from the callout's own area fell from 83% to 61% after 4.2, the opposite of what I expected. I know area is "usually covers", not live location, so does that number mean anything?
- Did the 4.2 duplicate-push fix change how a missed ping is recorded?

Could we find 30 minutes for you to walk me through the ranking? I'll write it up and send it back for you to correct.

Thanks,
[Your name]

---

## 2. Message to Marcus Oyelaran

Hi Marcus,

I'm the new PM for Dispatch. Thanks for flagging the ranking question on 14 Aug. Nobody answered it, so I'd like to close it. I also need rough numbers only engineering has.

**The finding in brief.** After 4.2, acceptance fell from 75-78% to 54% in release week and has recovered to about 73%. The drop is in missed pings, not turned-down ones. Four responders (Vesper, Farlight, The Undertow, Meteor Mite) stopped being offered work, with most of their pings missed.

**Your 14 Aug question.** Was the ranking change meant to apply the same way to responders who miss pings? I think the starved four are a result of misses, not turn-downs. I'd like to treat that as an open design choice, not a mistake, unless you know it was decided. I'm asking Wen how the score handles misses.

**What I need from engineering** (rough is fine, link is fine):

1. **Incident or deploy log for 12 Aug to 6 Sep.** Misses jumped on 12 Aug (7 of 25) and peaked on 13 Aug (12 of 25, across 8 responders). I can't see an outage pattern in my data, but it only shows outcomes.
2. **Push delivery or receipt data for 12 Aug onward**, especially for the four responders. A count of pings sent against pings delivered would help. If it isn't logged, that's worth knowing.
3. **Response time per ping**, or confirmation it isn't recorded. I can't test the 90s to 60s change directly without it.
4. **Email delays.** Two tickets (14 and 22 Aug) report password reset emails taking nearly an hour. Probably unrelated, but 14 Aug is the day after the worst missed-ping day. Was there an email or auth provider issue?

**One decision I'd like your read on.** I'm leaning towards testing a 75 or 90 second ping wait. It's one release config value, not a revert of 4.2. How much lead time would a config-only release need, and is there any risk to the Responder Availability Record that Supply reads?

Nothing here needs a change before we've talked. Could we take 30 minutes this week?

Thanks,
[Your name]

---

## Notes for you

- **Eastgate is a useful comparison.** Meteor Mite and The Gale share a handler (Kip) and an area (Eastgate). The Gale's pings rose from 13 to 21 a week while Meteor Mite's fell from 11 to 1. That points away from handler-level and area-level causes. I left it out of the messages so they stay short. It's worth raising with Wen if she wants to see the evidence.
- **Don't send the earlier section 3 as well.** This replaces it and avoids asking both of them the same thing.
- **Marcus's last question** assumes config-only releases are possible. The brief says routing config ships with the release, so confirm that with him rather than assuming.
