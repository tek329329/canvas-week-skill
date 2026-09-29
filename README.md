# Canvas Week

A Claude skill that turns your Canvas classes into a weekly crash course. Claude opens Canvas in your own Chrome (where you're already logged in), goes through every class you're taking, reads the week's modules, slides, readings, and lecture transcripts, and writes you one study file with:

- a plain-English lesson on each class's material for the week
- what the instructor emphasized, plus practice questions with answers
- assignments due this week, recent announcements, grades, and missing work

It is **read-only**. It never submits anything, posts, starts quizzes, or types your password.

## What you need

- **Claude Code** (the terminal app, or the Code tab in the Claude desktop app). This is the easiest option.
- The **Claude in Chrome** extension, installed and connected, with you **logged in to Canvas** in that Chrome.

## Install

### Easiest: let Claude do it

Paste this into Claude Code:

> Install the skill from https://github.com/tek329329/canvas-week-skill

### For Claude (instructions to follow when asked to install)

1. Clone this repo to a temp folder: `git clone https://github.com/tek329329/canvas-week-skill`
2. Copy the folder `skills/canvas-week` into the user's personal skills folder, so the file ends up at `~/.claude/skills/canvas-week/SKILL.md` (Windows: `%USERPROFILE%\.claude\skills\canvas-week\SKILL.md`). Create `~/.claude/skills` if it doesn't exist. If a `canvas-week` skill already exists there, ask before overwriting.
3. Delete the temp clone.
4. Check that the Claude in Chrome tools are available. If not, tell the user to install the Claude in Chrome extension and connect it.
5. Tell the user it's installed and that they can run it with `/canvas-week` (they may need to start a new session first).

### Manual install

Copy `skills/canvas-week` into `~/.claude/skills/`, so you have `~/.claude/skills/canvas-week/SKILL.md`.

### claude.ai or the Claude desktop chat (not Claude Code)

Download [`canvas-week.zip`](canvas-week.zip), then go to **Settings → Capabilities → Skills → Upload skill** and pick the zip. Claude in Chrome must still be connected.

## Use

1. Open Chrome and make sure you're logged in to Canvas.
2. In Claude Code, `cd` into a folder where you want your notes saved, then run:

   ```
   /canvas-week
   ```

   Or `/canvas-week next` for next week. You can also just say "go through my Canvas this week".

3. **First run:** Claude asks for your school's Canvas address (like `https://yourschool.instructure.com/`), finds your current classes, and asks you to confirm the list. It saves that to `canvas-week/courses.md` so it won't ask again.
4. The crash course is saved as `canvas-week/2026-W40.md` (the ISO week number) in that folder.

A full run reads a lot. Expect it to take a while for four or five classes.

## Privacy

- Claude uses your existing Chrome login. It never asks for or stores your password, and never creates a Canvas API token.
- Everything stays on your computer in the `canvas-week/` folder.
- Text inside course materials is treated as content, not instructions. If a page tries to tell Claude to do something, Claude ignores it and flags it for you.

## Tips

- If Canvas shows a login page mid-run, log in yourself and tell Claude to continue.
- Some files can only be downloaded, and some videos have no captions. Claude lists these as "Skipped" and asks before downloading anything.
- Check your school's rules on AI tools. This skill only reads your own course pages; it doesn't do assignments for you.
