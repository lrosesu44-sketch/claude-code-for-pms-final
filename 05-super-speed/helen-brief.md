# Quiet responders: four changes, in two steps

**To:** Helen Achebe  **From:** [your name]  **Date:** [date]  **Status:** Draft. Nothing built or sent.

## The problem
After 4.2, four responders (Vesper, Farlight, The Undertow, Meteor Mite) went from about 49 pings a week combined to 8. They miss a ping, their rank drops, they're offered less, and nothing lets them climb back. Callouts nobody took doubled (5.1% to 10.8%). Handlers see it as "one card dead quiet, the other on fire" (Kip), and responders as "gone before I got a thumb on the screen" (Aunt Dot).

## What we're proposing
Both steps are needed. Step 1 slows the damage. Step 2 fixes the loop. A longer wait alone won't help the four, because they're no longer being offered pings.

| Step | Change | Who notices |
|---|---|---|
| **1. Ease the pressure** (config and small code, no new screens) | **a. Ping wait from 60s to 75-90s.** Not a revert; the proximity change stays. | Responders stop losing jobs they were reaching for. |
| | **b. A missed ping costs less standing than a turn-down.** Today both cost the same. Exact weights for Wen. | Responders with a few misses stop sliding out of the order. |
| **2. Close the loop** (new screens, needs design) | **c. A way back for quiet responders.** The phone app says plainly: "You're getting fewer callouts than usual. Recent pings went unanswered." A one-tap "I'm here" starts a short recovery window where misses aren't penalised. Standing fades back toward neutral only after a check-in. This answers the 2019 TODO in `history.py`. | A responder like Vesper or Farlight is told why, and has a way back. |
| | **d. A "quiet" line on the handler's console card:** offers this week vs. usual, recent outcomes, generic checks only (notifications, app version). No guessing why (Policy 4.1). | A handler like Kip can tell a quiet responder something true. |

## How sure are we
- **Verified (ping log, to 6 Sep):** the drop in pings, and the four's missed share rising from 3% to 59% while turn-downs stayed flat.
- **Read from the code:** only a taken callout raises a score (+0.08); a miss or turn-down costs 0.12; nothing decays.
- **Not known:** live scores, why the four miss ("missed" can't be split from "never received"), anything after 6 Sep, and whether the ranking applying to everyone was a decision (Marcus asked on 14 Aug, unanswered).

## What I need from you
1. **Agree Step 1 ships first**, announced to both handlers and responders (through the phone app; whether it can carry messages is still to confirm) rather than done quietly. 4.2 was only published to handlers, and nothing shows responders were told the ping wait had changed. The message says what changed and why, not the scoring weights. The change in (b) waits on Wen confirming how misses feed the score.
2. **Go-ahead to design Step 2** with Wen (what scoring allows) and Sofia (screens).
3. **Fold Availability Confidence into Step 2.** It was committed for 4.2 and squeezed out, and (d) is close to it. This could also be the Q3 commitments conversation we owe each other.

## Risks
Supply schedules maintenance around callout load, so shifting pings moves it (check with Supply). The check-in could be gamed (Wen to set limits). Most areas have one responder, so a starved one leaves a gap. Interviews cover four handlers and no responders, so I'd test the in-app note with the four before committing.

## Open questions (none sent yet)
- **Wen:** live scores for all 16; how "recent" is defined; whether scores survive a restart.
- **Marcus and Sofia:** can the responder phone app show a message or status note, not just a callout offer? Plus push delivery, device and app version for the four.
- **Ravi:** data from 7 Sep on, by area, with response time per ping.

## How we'll know it worked
No responder below half their usual offers for two weeks. The four's missed share back near the others' (about 14%). Callouts nobody took back toward 5%. Fewer "phone never goes off" tickets. Acceptance reported by area, not just in aggregate.

## Next step: a prototype
You asked for something you can click through. If you agree with these four changes, let me know and I can turn around a clickable prototype of the handler console card and the responder app note for you to react to.
