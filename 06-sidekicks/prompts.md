# 06 · Sidekicks — prompts

**Context:** You joined Rook two weeks ago as PM on Dispatch.
Release 4.2 shipped on 12 August, just before you arrived, and
landed badly. You've spent five sessions on it: finding out what
went wrong, then building the fix nobody had — a working prototype,
by hand, in one sitting, for one room.

At the end of the session, type wrap up, and Claude Code saves the
prompts you wrote yourself below — not the starter prompt — updates
CLAUDE.md, and saves your work to GitHub. By Module 6 this file is a
prompt library built from your own questions.

---

### 1.

I want to save a habit as something I can reuse. When I review a brief before it goes any further, here's what I actually check for: 

1. It names who owns it 
2. It says how we'll know it worked 
3. The scope at the end matches the scope at the start 
4. It explains the problem before it proposes a fix
5. It explains the intended audience or user(s)
6. It explains the "what is the user trying to do" or what do they need to be able to do
7. It explains what the impacts are by fixing / not fixing
8. Identifies any gaps that need to be considered or closed
9. Asks for any deadlines /timing constraints
10. Identifies available resources
11. If any of the above are missing, that those items are clearly highlighted to be followed up on.

Turn that into a skill called review-checklist, so I can point it at any brief and get the same check every time, without me explaining it again.

### 2.

review this brief: /review-checklist 05-super-speed/brief.md.

### 3.

Update the brief to close those follow-ups. Also reorganize the Verdicts table sorting by Status, then Check columns. Color-code (Present -= green, Partial = yellow; Missing = red) so it is easier to identify.
Reorganize the Scope, Follow-up, and Gaps so those sections are more visual

### 4.

Update the skill

### 5.

Reorder the table so the order of items is Present, Partial, Missing

### 6.

commit the skill and review page

### 7.

review this brief: https://github.com/lrosesu44-sketch/claude-code-for-pms-final/blob/main/05-super-speed/brief.md

### 8.

commit brief.md and push

### 9.

review this brief: https://github.com/lrosesu44-sketch/claude-code-for-pms-final/blob/main/05-super-speed/brief.md

### 10.

review this brief: https://github.com/tracy1004/claude-code-for-pms-final/blob/main/05-super-speed/production-requirements-brief.md

### 11.

Schedule review-checklist to run every Monday morning at 8:30AM Eastern time zone, and let me know what it finds; briefs should be found in claude-code_for-pms-final. If no brief is found, still generate the checklist. If more than 1 brief is found, create 1 checklist per brief. Save and keep in the same directory as other briefs. Naming convention should indicate the date of the brief and the person who sent it. Nothing needs to be ready for it to fire today. I'm setting the habit, not waiting on the result.

### 12.

Is there a way to run this when Claude is closed?
