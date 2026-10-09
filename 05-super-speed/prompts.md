# 05 · Super Speed — prompts

**Context:** You joined Rook two weeks ago as PM on Dispatch.
Release 4.2 shipped on 12 August, just before you arrived, and
landed badly. You've spent three sessions finding out what went
wrong: the two piles of feedback that didn't agree, the numbers that
hid four people inside an average, and the code that settled it —
the shorter timeout is what did it.

At the end of the session, type wrap up, and Claude Code saves the
prompts you wrote yourself below — not the starter prompt — updates
CLAUDE.md, and saves your work to GitHub. By Module 6 this file is a
prompt library built from your own questions.

---

### 1.

Help me write a brief in response to Helen's notes in 05-super-speed/director-request.txt that addresses her questions as well as any additional gaps. Do not draft your response until you review her note, the root-wiki, and the Word doc 00-rook/company/notes/handoff-from-priya.docx. Think about your answer before you respond and ask me if you have any questions.

### 2.

Can you make it clearer to Helen what the fixes are that we are proposing?

### 3.

I think Group A and B are both necessary, not an "instead of". Can you change the brief to streamline further and ensure all the information we need to provide to Helen can be communicated succinctly to her in one page?

### 4.

Why are only handlers notified of changes? Should responders be notified to since changes directly impact them?

### 5.

Check whether the phone app can send in-app messages

### 6.

One additional tweak: Add a closing that addresses Helen's request for a prototype - that if she is in agreement with the proposed solutions, to let me know and I can turn around a prototype for her

### 7.

Rename helen-brief.md to brief.md

### 8.

Save the brief exactly as it stands now as 05-super-speed/brief.md. Show me the file when it's done.

### 9.

Take the brief you just wrote and build me a working prototype, an actual screen I can click through, not a description of one. Show me this happening to Farlight specifically, using her name, the way her handler would see it. Save it as 05-super-speed/prototype.html, a single file I can just open in my browser. Show me where this would actually happen, and make at least one thing on it respond when I click it.

### 10.

Is this prototype based on the current foundational app?

### 11.

Is it possible to create the prototype should that it uses the current console or screenshots with a banner at the top indicating it is a prototype inclusive of bug fixes and enhancements?
Also, while the ping timeout is not settled, please increase it to 75 for the prototype. 

* Can you add a timer that displays for handler and responder so they are aware how much time is left before the responder misses the ping? 
* For Farlight, add a weekly visual of meaningful metrics.
   * If the responder should have insight to any of the ping details (incident type, location, # of people involved, etc.), come up with a way to display that info so they aren't walking into an incident blindly.
* For the handler, is there a way to override the ping timeout? If not, add it and the ability to capture the reason.


Cross-check the above plus the solutions presented in the brief to Helen to confirm the prototype is inclusive of all changes being requested.

### 12.

In the responder view, they see: "Your next few pings won't count a miss against you." - what does "next few" quantify as? Do we have that number defined anywhere?

### 13.

Yes, update the prototype and add it to Wen's questions

### 14.

1. Once a responder takes a ping, they should see the details of the incident.
2. It should be easier for the handler to determine whether the responder is Active on a current incident and when the incident is Resolved or Closed after it was taken.
3. The week-by-week the handler sees for the responder is helpful but busy: do you have a recommendation how to make this info more digestible and actionable, when needed. For example, if a handler sees 100% misses, can they do a test ping?
4. Is it necessary for any handler to see more than one responder's info?

### 15.

Please update the brief to highlight the "bells and whistles" out of the original scope, and also provide a summary here of all the changes before committing.

### 16.

trim the brief to one page
