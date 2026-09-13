---
name: wrap
description: End-of-session wrap-up. Use when the user says /wrap, "wrap up" or "make sure everything is updated": check the work landed, save it, log follow-ups, give a next-session prompt.
---

# Wrap up the session

Many people end an AI working session the same way: "let's wrap up and make sure everything is updated, so I can pick this up tomorrow." This skill is that request, done the same way every time. A new session starts with no memory of this one. It knows only what is written down and what the user pastes in. So the goal is a clean handoff: the work checked and saved where it belongs, nothing left half-done, and a clear first message for next time.

## 1. Find the house rules

Look for instruction files from the working folder upward: `CLAUDE.md` (any capitalization), `AGENTS.md`, or a README that says how the project keeps notes and tasks. They decide where things get saved; the steps below only fill the gaps they leave.

If there is no project folder (a plain chat with no file access), skip the saving steps. Give the handoff in your final message, then the next-session prompt.

## 2. Take stock

List what this session actually did: files created or changed, decisions and the reasons for them, corrections the user made, follow-ups or ideas they named, and anything still running or half-finished. If it was a quick question or casual chat, there is nothing to save. Say so and go straight to the report.

## 3. Check the claims against the files

Before writing anything down, compare what this session says it did with what is actually there. For each change it claims (a file written or edited, a task closed, a setting changed, a fix applied), open the file or run the quick check and confirm it landed. Do the same for anything the session repeated from an earlier note as fact. If something can't be confirmed, don't record it as done: write it down as unconfirmed and name it in the report.

The reason: AI sessions sometimes report work as finished that never landed, and the next session trusts the handoff note. A wrong "done", or an old mistake copied into the note, gets carried forward as fact, and it is much harder to spot later than now.

## 4. Save the work where the project keeps its records

- Use the places the project already has: a session or build log, a changelog, `notes/` or `docs/`, a status section in the README, a decisions folder. Add to them instead of rewriting what's there, because earlier entries are history.
- Read a file again right before writing to it. Another session, agent or teammate may have written to it minutes ago, and a write based on an old read erases their work.
- Check the date with `date` before logging. A session that ran past midnight belongs under the new day.
- Record decisions with their reason, not only the outcome. The reason is what stops the next session from reopening them.
- If the project has no place for notes, don't invent a folder structure. Put the handoff in the final message and ask once whether the user wants a notes file for this project.

## 5. Follow-ups and loose ends

- Every follow-up, parked idea or next step goes into the project's task list if it has one. A follow-up that lives only in chat gets forgotten.
- Finish or clean up what the session started: temporary test files, background processes, drafts. If something has to stay unfinished, name it in the report.
- In a git repository, say what is uncommitted. Commit only if the project's rules or the user ask for it.

## 6. Report, then the prompt for the next session

Keep the report short and in plain words:
- what was checked and saved, and where
- anything that couldn't be confirmed
- what is still open, and where it is tracked
- anything that needs the user: a decision, a test, a file to bring

Report only what was actually saved. Skip promises like "I'll remember everything", since the next session knows only what is written down.

Then end with the next-session prompt, under the line **To start the next session, paste this:** and inside a code block so it copies cleanly. Write it for a session that has never seen this chat:
- what we are continuing and where the state lives: the exact note, log section or file to read first
- the first concrete step
- anything the user needs to bring or decide before starting

Keep it to about 3-6 lines, in the language the user used this session. If there is no natural next step, say so instead of inventing one.

**Example ending:**

To start the next session, paste this:

```
Continue the pricing page redesign. First read the latest entry in notes/session-log.md and the open items in TODO.md.
First step: finish the mobile layout for the plan cards. The desktop version is done and checked.
Before starting, I'll decide whether the yearly plan shows a discount badge.
```
