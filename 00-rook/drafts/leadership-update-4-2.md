# Leadership update: Dispatch since 4.2 (not sent)

Drafted 7 Oct 2026. Add your name and the recipient before sending. Numbers come from the rook-database and `00-rook/data/callout-history.csv` (29 Jun to 6 Sep; nothing later is available).

---

**Subject:** Dispatch since 4.2: unfilled callouts roughly doubled, now recovering

Hi [Helen / name],

A short update on Dispatch since 4.2 shipped on 12 Aug.

**The headline:** since 4.2, about 1 in 9 callouts went unfilled, up from 1 in 20.

| | Before 4.2 (6 weeks) | After 4.2 (3 weeks, 17 Aug on) |
|---|---|---|
| Callouts nobody took | 43 of 837 (5.1%) | 40 of 372 (10.8%) |
| Acceptance rate | 76.8% | 68.5% |

**What's behind it**
- The drop is in missed pings, not turned-down ones. Responders aren't refusing work; more pings are timing out.
- Four responders went from about 49 pings a week to about 8 and took almost none of them. The other 12 saw a small dip and got more pings.
- The step lines up with 4.2, which cut the ping wait from 90 to 60 seconds and weighted proximity up in routing. I haven't yet confirmed which change is responsible, and August seasonality isn't ruled out.

**Where it stands**
- It's recovering. The unfilled share was 14.0%, 12.9% and then 5.5% in the latest week I have (31 Aug), back near the old level. Acceptance was 72.7% that week against 75-78% before.
- My data stops on 6 Sep, so I can't yet say whether the recovery held.
- Callouts entered also fell about 11% after 4.2. I don't know why, and I'm treating it as unexplained.

**What I'm doing next**
- Asking engineering how missed pings feed the routing score, and for delivery and timing data for the four responders.
- Asking Ravi for numbers from 7 Sep onward, split by responder and area, and for last year's figures to test seasonality.
- Considering a test of a 75-90 second ping wait. It's one config value, not a revert of 4.2. Nothing is decided.

**Where I'd like your input:** whether you're comfortable with a ping wait test once the data is in, and how you'd like me to report acceptance going forward (I'd suggest by responder as well as in aggregate, since the aggregate hid the split).

Thanks,
[Your name]
