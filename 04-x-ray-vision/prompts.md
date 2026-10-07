# 04 · X-Ray Vision — prompts

**Context:** You joined Rook two weeks ago as PM on Dispatch.
Release 4.2 shipped on 12 August, just before you arrived, and
landed badly. Last session the numbers showed you what happened: a
ping used to wait ninety seconds and now it waits sixty, people
missed pings they used to catch, and missing one counts the same as
turning one down — so four responders stopped hearing from us
altogether.

At the end of the session, type wrap up, and Claude Code saves the
prompts you wrote yourself below — not the starter prompt — updates
CLAUDE.md, and saves your work to GitHub. By Module 6 this file is a
prompt library built from your own questions.

---

### 1.
Is there anything in the change logs that points to pre-4.2 code that mitigated the current problems?

### 2.
We know the change in ping wait was intentional. Was the change in Proximity from .45 to .6 also intended /part of the requirements?
Is there anything point to whether the change in proximity is impacting the four responders who've gone silent?

### 3.
Is there anything in the 4.2 code that introduced the issue experienced by the four responders?

### 4.
Is there something in the code that would account for pings going to someone whose usual area matched the callout falling from 83% to 61%? Is there an issue with the proximity?

### 5.
In plain English, based on the code what is your hypothesis as to why the four responders were starved for pings and the others were not impacted (as much)?

### 6.
Can we get a score pre-4.2 vs. post 4.2 of the sixteen responders?

### 7.
knowing that only the handlers were notified of the change and it is unclear whether responders were notified, write a 1-3 sentence summary of what you think the issue is based on that info, what changes were made in the code in 4.2, and what might be impacting the 4 responders.

### 8.
Are there inconsistencies between what you see as these gaps in the code and things the readme indicates should be there?

### 9.
Over a week ago, Marcus asked: "Quick one, did the change to who gets asked first apply to responders who'd already been turning jobs down, or just new ones? Can't tell from the code and don't want to guess on this. Anyone know?"

Which file has last session's numbers in it? Read that along with the code and let me know whether it supports our findings so far. Also let me know if it answers Marcus's questions above.

### 10.
Before I respond to Marcus is there anything in the code that indicates how the ping looks, sounds, or feels in addition to the shortened ping length that might be impacting the four responders?

### 11.
You said "The one function that puts a ping on a phone is push_to_device in offer.py. It is an empty placeholder with the comment "Send the offer to whatever device they're signed in on."  - are you able to tell what device a responder is signed in on?

### 12.
Please draft the response to Marcus's question again

### 13.
Please re-write the response to Marcus's questions with a succinct answer that can be shared in Slack

### 14.
I believe we covered some of this before, but find me the part of this code that takes points off somebody when they miss a ping or turn one down. Show it to me and explain it in plain English. Then find me every single thing in this code that puts points back on.

### 15.
Can you search the override log and see if there is anything in there that would also impact scores?

### 16.
is there anything contradictory in the code itself or compared to the audit log that points to an impact on scores?

### 17.
please provide a summary of the contradictions you found in plain English and what their impacts could be to a handler or responder. Create a visual to tell the story of what is expected vs. where the contradictions pop up and flag anything out of the norm from what is expected.

### 18.
If somebody has been quiet for a month, walk me through, step by step, exactly what would have to happen for them to start getting work again. Tie this to any of the most recent finding of contradictions /what is out of the norm.

### 19.
Summarize very tightly these findings, using this framework: "According to my findings in the code, for someone who's gone quiet, they would need to: ____________" (fill in the blank)
