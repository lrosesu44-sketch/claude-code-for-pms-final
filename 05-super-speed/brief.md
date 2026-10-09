# Quiet responders: four changes, plus seven extras to choose from

**To:** Helen Achebe  **From:** Laurie  **Date:** October 9, 2026  **Status:** Draft. Prototype built (`prototype.html`); nothing sent.

## The problem
After 4.2, four responders (Vesper, Farlight, The Undertow, Meteor Mite) went from about 49 pings a week combined to 8. They miss a ping, their rank drops, they're offered less, and nothing lets them climb back. Callouts nobody took doubled (5.1% to 10.8%). Handlers see "one card dead quiet, the other on fire" (Kip). Responders see "gone before I got a thumb on the screen" (Aunt Dot).

## Core proposal
Both steps are needed. A longer wait alone won't help the four, because they're no longer being offered pings.

| Step | Change | Who notices |
|---|---|---|
| **1. Ease the pressure** | **a. Ping wait from 60s to 75-90s.** Not a revert. | Responders stop losing jobs they were reaching for. |
| | **b. A miss costs less standing than a turn-down.** Weights for Wen. | Responders with a few misses stop sliding out of the order. |
| **2. Close the loop** | **c. A way back.** The app says why offers dropped; a one-tap "I'm here" opens a recovery window where misses aren't penalised. Answers the 2019 TODO in `history.py`. | A quiet responder like Farlight is told why, and has a way back. |
| | **d. A "quiet" line on the handler's card:** offers vs. usual, recent outcomes, generic checks only (Policy 4.1). | A handler like Kip can tell a quiet responder something true. |

## Extras in the prototype, beyond the original scope
Please tell me which you want. None are in the core proposal.

| | Extra | Needs |
|---|---|---|
| e | **Countdown timer** for handler and responder | App shows a live timer |
| f | **Ping details for the responder** (what, where, type, people, needs, travel) | Only what, where and when exist today |
| g | **Handler extends a live ping +30s**, with a logged reason | New control; limits from Wen |
| h | **Incident details after taking**, plus Active, Resolved, Closed status | Status model; touches the availability record Supply reads |
| i | **Test ping** when a responder goes quiet | App must report delivery; we have none today |
| j | **Simpler weekly view** (this week vs. usual, one chart) | Console and app design |
| k | **Handlers see only their own responders** | Check the console can enforce it |

**My suggestion:** a-d, plus (e) and the first three fields of (f). The rest are follow-ups.

## What I need from you
1. **Step 1 ships first**, announced to handlers *and* responders (4.2 told handlers only). (b) waits on Wen.
2. **Go-ahead to design Step 2** with Wen and Sofia.
3. **Which extras** are in, out or later.
4. **Fold Availability Confidence into Step 2** (squeezed out of 4.2; (d) is close to it). It could double as our Q3 commitments conversation.

## How sure are we, and what's open
- **Verified (ping log, to 6 Sep):** the four's missed share rose from 3% to 59%; turn-downs flat. **From the code:** only a taken callout raises a score (+0.08); a miss or turn-down costs 0.12; nothing decays.
- **Not known:** live scores, why the four miss, anything after 6 Sep, whether ranking everyone alike was a decision (Marcus asked 14 Aug).
- **Questions (none sent):** *Wen:* live scores; recovery window length and expiry. *Marcus and Sofia:* can the app show messages, a timer and delivery status? *Ravi:* data from 7 Sep, by area.
- **Risks:** Supply schedules maintenance around callout load. The check-in could be gamed. The extras widen scope. No responders interviewed yet.

## Success looks like
No responder below half their usual offers for two weeks; the four's missed share near the others' (about 14%); callouts nobody took back toward 5%; fewer "phone never goes off" tickets.

## Prototype
`prototype.html` shows this happening to Farlight, from Linda's console and Farlight's phone, including every extra. The layout is illustrative until rebuilt from screenshots of the live screens; weekly counts are real, the rest is demo.
