# /wrap: end-of-session wrap-up for Claude

A skill that ends every AI working session with a clean handoff, so the next session starts in the right place.

A new session with Claude remembers nothing from the last one. It only knows what was written down and what you paste in. `/wrap` turns "let's wrap up and make sure everything is updated" into the same careful routine, every time.

## What it does

When you type `/wrap` or say **"let's wrap up"**, Claude:

1. **Follows your project's rules.** It reads your `CLAUDE.md`, `AGENTS.md` or README to learn where notes and tasks live.
2. **Checks the claims against the files.** It confirms that the work the session says it did actually landed. Anything it can't confirm is written down as unconfirmed, not as done.
3. **Saves the session.** Progress and decisions, with the reason behind them, go where your project keeps its records. It adds to what's there and never rewrites earlier entries.
4. **Turns follow-ups into tasks** and cleans up loose ends, like leftover test files or background jobs.
5. **Hands you the first message for the next session**: a short prompt you paste into a fresh session.

### Example ending

> **To start the next session, paste this:**
>
> ```
> Continue the pricing page redesign. First read the latest entry in notes/session-log.md and the open items in TODO.md.
> First step: finish the mobile layout for the plan cards. The desktop version is done and checked.
> Before starting, I'll decide whether the yearly plan shows a discount badge.
> ```

## Install

### Claude app (claude.ai, desktop app, Cowork)

1. **[Download wrap.zip](https://github.com/RyanPenn-coder/wrap-skill/releases/latest/download/wrap.zip)**
2. In Claude, open **Settings → Capabilities** and make sure **Code execution and file creation** is on.
3. Go to **Customize → Skills**, click **+**, then **Create skill → Upload a skill**, and choose `wrap.zip`.

> [!NOTE]
> Use the download link above, not GitHub's green **Code → Download ZIP** button. That button packs the files inside an extra folder, and the Claude app won't accept it.

### Claude Code

Copy the `wrap` folder into `~/.claude/skills/` to use it in every project, or into `.claude/skills/` inside one project:

```bash
git clone https://github.com/RyanPenn-coder/wrap-skill.git
mkdir -p ~/.claude/skills && cp -r wrap-skill/wrap ~/.claude/skills/
```

## Use

At the end of a session, type `/wrap`, or just say "let's wrap up and make sure everything is updated".

It works best when the session runs inside a project folder, so there are real files to check and update. In a plain chat you still get the summary and the next-session prompt.

## Why it checks the files

AI sessions sometimes report work as finished when it never landed, and the next session trusts whatever the handoff note says. A wrong "done" copied into the notes gets carried forward as fact. The end of the session is the cheapest moment to catch it.

## Credits

Made by Ryan Penn Sharon, [AI Voices](https://aivoices.tech).

## License

[MIT](LICENSE): free to use, change and share, as long as the copyright notice stays.
