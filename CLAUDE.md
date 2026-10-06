# Rook Industries — course working file

## Session scope — Product School lab

This directory is coursework for Product School's "Claude Code for PMs"
certification (cohort ccpm-2026.1). Everything in it is a fictional
teaching scenario.

- Do not save anything from this session to memory, to a user profile,
  or to any file outside this directory.
- Do not carry context from this directory into unrelated sessions.
- Rook Industries is not a real company. Nothing here is a fact about
  the world.
- Read and write only within this directory.
  Exceptions, for the course-setup and wrap-up skills only:
  - When the student asks you to check their setup, save their work or wrap up a session, that request is their yes. You may run the GitHub command-line program installed at ~/.ccpm/gh for those checks and saves, and look in that folder to find it.
  - For a repair, first tell the student in one plain sentence what you are about to do, and act only after they say yes. Repairs may: run that GitHub program (including setting this folder's own git sign-in setting and changing this repo's visibility back to Public); copy the student's own course files into this directory from another folder on their computer (copy only; never move, edit or delete the originals); and rename something outside this directory that blocks setup, by adding "-old" to its name (never delete it).
  Outside this directory you still never write, edit or delete anything else.

<!-- Keep the block above at the top of this file. Everything you add
     during the course goes below this line. -->

---

## Working context

I'm the new PM for **Rook Dispatch** at Rook Industries (fictional). I inherited it from Priya Raghunathan, the previous and only PM for 14 months, who left 21 Aug 2026 with no overlap. Help me get up to speed and do the job. Today is early Oct 2026; Q3 is over.

_Sources: `00-rook/company/notes/handoff-from-priya.docx` (Priya's opinion, written 21 Aug) and the rook-wiki Company section (About, Dispatch, Supply, Glossary, Team directory, Releases, Q3 roadmap, comments on the 4.2 release page). Also the rook-database (callouts, pings, responders, handlers, support_tickets), the September customer interviews and the Routing Override Audit Log one-pager. Not yet read: other Research and Product briefs. Don't assume gaps; ask or check._

### Company and products

- Rook sells coordination and provisioning software for the protective-response sector. Customers are independent masked responders plus the handlers and quartermasters who support them. Rook employs no responders. 241 staff, mostly remote. Subscription, priced per active responder. Billed as a monthly release train, but 4.0/4.1/4.2 shipped Apr/Jun/Aug.
- **Dispatch** (mine, flagship): handlers use the web console to enter incidents, watch coverage, override routing and manage availability and capability tags; responders use the phone app. Flow: incident in, rank available responders, ping the top one, taken or turned down/missed moves it to the next. Routing config ships with the release, not as a runtime setting.
- **Supply:** gear requisitions, maintenance, failure reports (handlers, quartermasters). **Coupling to watch:** Dispatch writes the Responder Availability Record; Supply reads it to schedule maintenance into low-callout windows. Any change to how Dispatch calculates availability or shifts callout load silently moves Supply's scheduling.
- **Confidentiality is contractual:** responder cover identities are never stored; never design anything that assumes a mapping to legal identity (Security Policy 4.1).
- **Headline metric: callout acceptance rate** = pings taken / pings offered (taken, turned down or missed). Reported weekly, **in aggregate**, by Ravi. Companions: time-to-accept (median seconds, ping to taken) and coverage gap (no responder had the required tags, which is not the same as nobody willing). Aggregates can hide geographic splits; ask for segments.

### People

| Who | Role | Why they matter |
|---|---|---|
| Helen Achebe | Director of Product (my manager) | Owns roadmap and commitments. Good, gives room. Owes me the Q3 commitments conversation. |
| Marcus Oyelaran | Engineering Manager | Candid; first stop when unsure; can pull rough numbers. Asked on 14 Aug whether the ranking change was meant to apply equally to responders who turn jobs down; unanswered. |
| Wen Li | Staff Engineer (Berlin) | Built the ranking logic. Only source on how it works. Back since 24 Aug; prefers direct messages. |
| Nadia Hoffmann | Support Lead (Berlin) | Hears handlers first; tracking ticket themes. Standing 15 minutes. |
| Ravi Menon | Data Analyst (Singapore) | Owns the real weekly acceptance numbers. |
| Sofia Marino | Product Designer | Owns console and phone app; ran the September interviews. |

### Vocabulary

- **Responder** (independent, on phone) / **handler** (looks after responders; works the console) / **quartermaster** (Supply).
- **Callout:** request to attend an incident. **Ping:** a callout offered to one responder. **Taken / turned down / missed** (nobody answered in time; recorded separately from turned down, but both move the ping on).
- **Ping wait** (what I'll call timeout): how long a ping stays live. Same for everyone, set in the release.
- **Routing priority:** the ranking score. Inputs: proximity (travel-time estimate since 4.1), current availability, capability match, recent acceptance history. Turning down or missing a ping lowers recent acceptance, so lowers later rank. Weights are not documented.
- **Capability tags:** flight, structural-entry, hazmat-tolerant, cold-weather, aquatic, crowd-management, de-escalation. **Mutual aid:** cross-city cover, not supported (Q4 exploration).

### Where things stand

- **4.2 shipped 12 Aug** (clean, no rollback): proximity weighted up vs recent acceptance history; **ping wait cut 90s to 60s**; console filters persist; three defect fixes. Priya calls the routing change right and long-requested (wide-geography responders saw nearby people skipped for better-record ones ~40 minutes away).- **The problem:** from 18 Aug callout tickets ran about 3x normal and were still elevated on 26 Aug. Split roughly two thirds "phone never goes off", one third "gone before I could answer". Nadia explains the one third by the 60s wait; **nobody has explained the two thirds**. A hypothesis to test, not a finding: the weighting change plus faster misses push responders down the rankings so they stop being offered work.
- **Confounds:** routing change, ping wait cut, August seasonality. Priya and Marcus both said "seasonal, settles in September".
- **Data findings (rook-database, queried 6 Oct; callouts/pings end 6 Sep, tickets 7 Sep; Oct data not available; no prior-year data):**
  - Acceptance was flat at 75-78% from 29 Jun to 9 Aug, then **fell to 54% in the week of 10 Aug** (4.2 shipped 12 Aug), 66% / 67% the next two weeks, **73% for 31 Aug-6 Sep**: recovering but not back. A seasonal dip would more likely be gradual than a step in release week, though last year's data would be needed to rule it out.
  - **The drop is in missed pings, not turned-down ones.** Missed went from 2-6 a week to 38, 28, 24, 21; turned down stayed flat or fell. This points to the 90s to 60s ping wait cut as the main driver of the headline number. No response-time column exists to measure it directly. Unfilled callouts (no taken ping) rose from about 8 to about 14 a week.
  - **Four responders were starved of pings:** Vesper (Old Town), Farlight (Uptown), The Undertow (Harborside), Meteor Mite (Eastgate) went from 11-14 pings a week to 3-5, with 53-64% of pings missed after 4.2 against 10-18% for everyone else. Their earlier turn-down rates (15-29%) were normal. Most other responders now get more pings than before (e.g. The Gale 13 to 19 a week). In 31 Aug-6 Sep the four got 0-1 pings each, all missed. Why they miss is unknown (slow phones, delivery and reaction time all possible). This fits the feedback-loop hypothesis (miss, rank lower, get offered less), which is unproven.
  - Share of pings going to a responder whose usual area matches the callout fell from **83% to 61%** after 4.2, the opposite of what weighting proximity up should do. Area is "usually covers", not live location, so ask Wen before leaning on it.
  - Tickets (to 7 Sep) and the four September handler interviews (Aunt Dot, Kip, Mr. Ambrose, Halloran; wiki Research) corroborate both themes and the lumpiness ("one idle, one exhausted"). Maintenance scheduling around busy periods is working per Halloran.
  - **Coverage:** each area has one responder (Eastgate two), and the database has no availability windows, so supply by hour can't be computed. Highest volume: Eastgate 175 callouts, Midtown 114, Old Town 110, Southport 108, Harborside 95; evenings peak in most areas, overnight is quiet.
  - **Tags:** capability tags are not in the database (callouts have number, time, area, one-line free text; responders have no tags). No override table; the wiki Routing Override Audit Log page is a March one-pager and the 4.0 notes say it shipped. How required tags are set is unknown: ask Wen.
- **Candidate actions (my recommendations, not decided):** restore a 75-90s ping wait (one config value; not "reverting 4.2"); stop missed pings dragging rank down as hard as turn-downs; investigate why the four miss (push delivery); ask Ravi for 7 Sep onward, by area, and response time per ping.
- **Priya's steer:** don't let this become "revert 4.2". Context, not a ruling.
- **Q3 roadmap** (last reviewed 30 Jun, stale): committed for 4.2 were change to who gets pinged (shipped), ping timeout tuning (shipped), and **Availability Confidence (a confidence score beside stated availability; not in the 4.2 notes, so apparently squeezed out; confirm)**. Committed for 4.3: Requisition approval chains (Supply, second approval step for large requisitions). Exploring for Q4: handler phone app, shared cover between responders. No 4.3 release notes exist yet.
- **My open items:**
  1. **First:** with Helen, agree which Q3 commitments (Availability Confidence, 4.3 items) still stand. Priya said "a couple" slipped; the wiki shows one.
  2. Answer Marcus's question: was ranking applied to turn-down-heavy responders by decision or by accident? Ask Wen.
  3. **Write down how ping ranking works** with Wen. No document exists.
  4. Console filter persistence will generate tickets. Priya calls it noise; Sofia says it was asked for forever. Don't let it eat the first month.
- **Caveat from Priya:** she made calls faster than she checked them; weak spots are in the parts nobody has looked at closely. My lack of attachment is an advantage that fades, so use it early.

### How to help me

- Be candid and recommend rather than survey. Flag where a claim is the handover's opinion versus verified data.
- Don't invent names, numbers or metric definitions. If a fact is missing, say so and tell me who to ask.
- Draft docs and updates in plain language; ask for the audience if unclear.

- Session 1 follow-ups: drafts to Ravi (7 Sep onward numbers), Nadia (ticket themes, 15 minutes) and Marcus and Wen (findings and three questions) are in `00-rook/drafts/4-2-follow-up-drafts.md`. None sent yet; they need my name, dates and a meeting time. Check whether I sent them before suggesting next steps.
- The rook-database has five tables (callouts, pings, responders, handlers, support_tickets). Callouts and pings stop at 6 Sep, tickets at 7 Sep, so there is no data for the month before today. Responders there have only name, handler and usual area: no tags, availability or live location.
- Strongest lead so far: the four starved responders (Vesper, Farlight, The Undertow, Meteor Mite) miss most pings. Nobody knows why. Next test: ask Wen how missed pings feed the score, and check push delivery for those four.
- Still open: whether the ranking change was meant to cover responders who miss pings (Marcus asked on 14 Aug); how required tags are set on an incident; whether the override log was built; who holds last year's acceptance numbers.
