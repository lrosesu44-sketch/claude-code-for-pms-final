# Quiet responders: four changes, three recommended add-ons, and extras to choose from

**To:** Helen Achebe  **From:** Laurie  **Date:** October 9, 2026  **Status:** Draft. Prototype built (`prototype.html`); nothing sent.
**Proposal owner:** Laurie. **Delivery owners:** to confirm with you (see "What I need from you").

## The problem
After 4.2, four responders (Vesper, Farlight, The Undertow, Meteor Mite) went from about 49 pings a week combined to 8. They miss a ping, their rank drops, they're offered less, and nothing lets them climb back. Callouts nobody took doubled (5.1% to 10.8%). Handlers see "one card dead quiet, the other on fire" (Kip). Responders see "gone before I got a thumb on the screen" (Aunt Dot).

## Who needs what
| Who | What they need to be able to do |
|---|---|
| **A quiet responder** (Farlight) | Know why offers stopped, and get back into the order without waiting for a miss-free run that never comes. |
| **A responder who reaches for a ping** (Aunt Dot) | Get long enough to answer before the ping moves on. |
| **A handler** (Kip, Linda Pruitt) | See which of their responders has gone quiet, and tell them something true. |

## What happens if we do nothing
- The four stay at about 8 pings a week combined. Farlight has had 0 of the last 20 Uptown callouts (to 6 Sep), and neighbours cover them.
- Callouts nobody took stay near 10.8%, against 5.1% before 4.2 (6 weeks before vs 17 Aug on).
- Handlers keep a lumpy roster and no answer for the quiet ones; the "phone never goes off" tickets are the visible cost.
- The same rule applies to everyone: the other 12 responders' missed share also rose, from 2.1% to 13.9%. They are not starved yet.
- **Supply:** unknown. Supply schedules maintenance into low-callout windows, so lumpy load could move its schedule. Not measured; ask Marcus.

## Scope at a glance
- **In this proposal:** core a-d, telling responders (not just handlers) about the Step 1 change, and the recommended add-ons (e) and the first three fields of (f).
- **For you to decide:** extras g-k, and whether Availability Confidence folds into Step 2.

## Core proposal
Both steps are needed. A longer wait alone won't help the four, because they're no longer being offered pings.

| Step | Change | Who notices |
|---|---|---|
| **1. Ease the pressure** | **a. Ping wait from 60s to 75-90s.** Not a revert. Exact value to be picked with Wen. | Responders stop losing jobs they were reaching for. |
| | **b. A miss costs less standing than a turn-down.** Weights for Wen. | Responders with a few misses stop sliding out of the order. |
| **2. Close the loop** | **c. A way back.** The app says why offers dropped; a one-tap "I'm here" opens a recovery window where misses aren't penalised. Answers the 2019 TODO in `history.py`. | A quiet responder like Farlight is told why, and has a way back. |
| | **d. A "quiet" line on the handler's card:** offers vs. usual, recent outcomes, generic checks only (Policy 4.1). | A handler like Kip can tell a quiet responder something true. |

## Recommended add-ons and extras
Add-ons (e) and the first three fields of (f) are in my suggestion. The rest are for you to pick from.

| | Extra | In my suggestion? | Needs |
|---|---|---|---|
| e | **Countdown timer** for handler and responder | Yes | App shows a live timer |
| f | **Ping details for the responder** (what, where, type, people, needs, travel) | First three fields only | Only what, where and when exist today |
| g | **Handler extends a live ping +30s**, with a logged reason | Later | New control; limits from Wen |
| h | **Incident details after taking**, plus Active, Resolved, Closed status | Later | Status model; touches the availability record Supply reads |
| i | **Test ping** when a responder goes quiet | Later | App must report delivery; we have none today |
| j | **Simpler weekly view** (this week vs. usual, one chart) | Later | Console and app design |
| k | **Handlers see only their own responders** | Later | Check the console can enforce it |

## What I need from you
1. **Dates.** What ship date do you need for Step 1, and what target for the Step 2 design? Is it tied to 4.3 or the Q4 plan? I haven't set any.
2. **Step 1 ships first**, announced to handlers *and* responders (4.2 told handlers only). (b) waits on Wen.
3. **Go-ahead to design Step 2** with Wen and Sofia.
4. **Owners.** I own the proposal. Who owns delivery of Step 1 and Step 2? I'd expect Wen on the scoring changes (a, b, c) and Sofia on screens (d, e, f), but that is not agreed.
5. **Which extras** are in, out or later.
6. **Fold Availability Confidence into Step 2** (squeezed out of 4.2; (d) is close to it). It could double as our Q3 commitments conversation.

## Resources (assumed, none confirmed)
| Who | What I'm assuming they can do | Confirmed? |
|---|---|---|
| Wen Li | Scoring weights, recovery window, ping-wait value | No |
| Sofia Marino | Screens for (c), (d), (e), (f) | No |
| Marcus Oyelaran | Release slot, engineering effort, delivery data | No |
| Ravi Menon | Data from 7 Sep, by area | No |
Effort, budget and design time are unknown. Marcus can give a rough size.

## How sure are we, and what's open
- **Verified (ping log, to 6 Sep):** the four's missed share rose from 3% to 59%; turn-downs flat. **From the code:** only a taken callout raises a score (+0.08); a miss or turn-down costs 0.12; nothing decays.
- **Not known:** live scores, why the four miss, anything after 6 Sep, whether ranking everyone alike was a decision (Marcus asked 14 Aug).
- **Other gaps:**
  - August seasonality was offered as the cause (Priya, Marcus). We have no prior-year data, but the drop began in release week, not gradually.
  - Callouts per week fell 11% (139 to 124), unexplained.
  - The 75-90s range isn't a single value; Wen picks it.
  - Which person in Supply to tell about load changes is not known.
  - Whether the check-in and recovery window are compatible with Policy 4.1 is unchecked; ask Wen and the policy owner.
- **Questions (none sent):** *Wen:* live scores; recovery window length and expiry. *Marcus and Sofia:* can the app show messages, a timer and delivery status? *Marcus:* effort and release slot. *Ravi:* data from 7 Sep, by area.
- **Risks:** Supply schedules maintenance around callout load. The check-in could be gamed. The extras widen scope. No responders interviewed yet.

## Success looks like
Measured against the six weeks before 4.2 (starting point: the four at about 49 pings a week, missed share 3%, callouts nobody took 5.1%, callout tickets 0 before 12 Aug vs 45 after, to 7 Sep):
- No responder below half their usual offers for two weeks.
- The four's missed share near the others' (about 14%).
- Callouts nobody took back toward 5%.
- Callout tickets ("phone never goes off", "gone before I could answer") back toward zero; target to agree with Nadia.
- **By when:** to be set with you (ask 1).

## Prototype
`prototype.html` shows this happening to Farlight, from Linda's console and Farlight's phone, including every extra. The layout is illustrative until rebuilt from screenshots of the live screens; weekly counts are real, the rest is demo.
