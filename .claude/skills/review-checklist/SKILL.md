---
name: review-checklist
description: Runs a fixed 10-point review on a product brief before it goes any further, produces a colour-coded HTML review page, and flags every missing item for follow-up. Use when the user says "review this brief", "run the review checklist", "check this brief", or points at a brief, one-pager, spec or proposal and wants it checked before it is shared or sent on.
---

# Review checklist for briefs

Run the same check every time. The user should not have to explain it again.

## Input

The brief to review: a file path, pasted text, or the most recent brief in the conversation. If it is unclear which document is meant, ask once. Read the whole brief before judging anything.

## The checks

For each check, give a status and a short evidence note (quote or point to the section). Do not guess: if the brief does not say it, it is missing.

| # | Check | What counts as present |
|---|---|---|
| 1 | **Owner** | A named person (or team) who owns the brief and the work. "TBD" or a role with no name is Partial. |
| 2 | **Success measure** | How we will know it worked: a metric or observable outcome, ideally with a baseline and a target or date. A vague "improve X" is Partial. |
| 3 | **Scope consistency** | Compare the scope stated at the start (title, goal, summary) with the scope at the end (steps, asks, deliverables, next steps). List anything that appears in one and not the other, including items added or dropped along the way. |
| 4 | **Problem before solution** | The problem is explained, with evidence, before any fix is proposed. Flag if the solution appears first or the problem is only implied. |
| 5 | **Audience / users** | Who the intended users or audience are, specific enough to picture (not just "customers"). |
| 6 | **User need** | What the user is trying to do, or needs to be able to do, in their terms rather than the feature's. |
| 7 | **Impact of fixing and not fixing** | Both sides: what changes if we do this, and what happens if we do nothing. Only one side is Partial. |
| 8 | **Gaps** | The brief names what is unknown, assumed or unverified and what must be closed. Also list any gaps you can see that the brief does not name (unsupported claims, opinion presented as fact, dependencies not mentioned). |
| 9 | **Deadlines / timing** | Deadlines, dates or timing constraints are stated, or the brief asks for them. If neither, ask who sets the date. |
| 10 | **Resources** | Who and what is available: people, time, budget, tools, data. Note whether availability is confirmed or assumed. Named but unconfirmed is Partial. |

Statuses: **Present** (green), **Partial** (yellow; say what is missing), **Missing** (red).

## Output

Write one self-contained HTML file, `<brief-name>-review.html`, in the same folder as the brief (for pasted text, ask where to save it). Then reply in chat with the verdict line and the follow-up list only, and link the file. Use `05-super-speed/brief-review.html` as the layout reference if it exists.

The page has these sections, in this order:

1. **Score tiles and verdict:** three tiles (Present / Partial / Missing counts) and one line saying whether the brief is ready to go further.
2. **Verdicts table:** columns `#`, Check, Status, Was, Evidence / note.
   - Sort by Status in this order: Present, then Partial, then Missing, then by check number.
   - Colour code the Status tag and a left border on each row: Present green, Partial yellow, Missing red.
   - Show the "Was" column only when re-reviewing a brief that was reviewed before; otherwise leave it out.
3. **Scope: start vs end (check 3):** side-by-side coloured columns. Suggested: *In this proposal*, *Needs a decision*, and *Differences found* (items in the start but not the end, or the reverse).
4. **Follow-up (check 11):** one card per Partial or Missing item. Each card has the question, and who to ask if the brief or context names one. Yellow border for Partial, red for Missing, green for items closed since the last review. If nothing is open, show a single green card saying "Nothing to follow up".
5. **Gaps (check 8):** a card grid. Cards for gaps the brief names, and cards for gaps the brief does not name, visibly distinguished (for example blue for named, grey for unnamed). Each card says who could close it.

If the brief is in a format other than a file (pasted text), still produce the HTML file and tell the user where it is.

## Rules

- Do not fill gaps with invented names, dates, numbers or metrics. A missing item stays missing and goes on the follow-up list.
- Review the brief as written. Do not rewrite or edit the brief unless the user asks. If asked to close follow-ups, add only what the brief's own sources support, mark anything that needs a person as an ask or "to confirm", and re-grade honestly.
- Distinguish verified facts from opinion or assumption when judging problem, impact and gaps.
- Keep notes short; the follow-up list is the main deliverable.
- Markdown cannot carry colour, so colour lives in the HTML file only.
