# Week 1 Setup Steps · Thu Nov 12 – Sun Nov 15

Goal for the week: the project folder is fully set up, the required log files are current, and the app can load a Canvas calendar feed and sample emails into Python objects (no graphics yet).

Done so far: ✅ Mentor Sign-Up Form · ✅ GitHub Username Form · ✅ git set up, repo cloned, `.gitignore` pushed

---

## Step 1 · Install the time keeper (10 min, once)

`timelog.py` logs your work sessions straight into `time_log` and keeps the total at the top. It lives **outside** your project repo, so it isn't part of the graded code.

1. In Finder, make a folder named `tools` in your home folder, and move `timelog.py` into it.
2. In Terminal, add a shortcut so you can type `timelog` from anywhere:

   ```bash
   echo 'alias timelog="python3 ~/tools/timelog.py"' >> ~/.zshrc
   source ~/.zshrc
   ```

3. Try it:

   ```bash
   timelog status
   ```

   It should say `No session running.`

**Every work session from now on:**

```bash
timelog start
```
...work...
```bash
timelog stop "Wrote parseIcs and its tests"
```

Other commands: `timelog status` (is a session running, and for how long) and `timelog cancel` (forget a session you started by accident).

Notes:
- Each entry looks like `2026-11-12 | 11:05 | 12:00 | 55 min | what you did`. If you add one by hand, use exactly that format so it counts toward the total.
- Add a line to `citations`: `timelog.py helper script written by Claude (Anthropic); used only to record my time, not part of the project code.`
- Remember the caps: ideating 2 hours, art/UI design 1 hour, understanding AI code 2 hours, other non-coding (like git setup) 1 hour. Describe each session clearly so it's easy to tell which bucket it's in.

---

## Step 2 · Catch up the log files (20 min)

Today's setup already counts, so log it now.

1. **`time_log`**: add today's sessions by hand in the format above. For example:
   ```
   2026-11-12 | 11:05 | 12:00 | 55 min | Set up git, cloned repo, added gitignore and plan
   ```
   Also add earlier ideation sessions (Oct 31, Nov 5) if you remember the times. Then run `timelog start` and `timelog stop "Logged earlier sessions"` once; that rewrites the total at the top.
2. **`ai_prompts/`**: copy your key prompts and my responses from this chat into `ai_prompts/planning.txt`. Include at least: choosing the project idea, the project plan, the course spec update, and the git setup. That's already 4 of the 5 required.
3. **`citations`**: list Claude (planning, git help, timelog script), the 15-112 course site, and any other resources so far.
4. Commit and push:
   ```bash
   cd ~/Documents/15-112finalproject
   git add .
   git commit -m "Catch up time log, prompts, and citations"
   git push
   ```

---

## Step 3 · Set up the project folders (10 min)

In VS Code, create:

```
15-112finalproject/
├── main.py          (empty for now)
├── models.py
├── storage.py
├── sources.py
├── tests.py
├── data/
│   ├── sample_calendar.ics
│   ├── emails/      (fake sample emails go here)
│   └── private/     (your real data; git ignores it)
└── screens/         (later)
```

Commit and push. Git skips empty folders, so `data/emails` won't show on GitHub until it has a file in it.

---

## Step 4 · Get your real Canvas feed (5 min)

1. Open Canvas → **Calendar**.
2. Bottom right, click **Calendar Feed** and copy the link.
3. Paste the link in your browser; it downloads an `.ics` file.
4. Move that file into `data/private/` and rename it `canvas.ics`.
5. Open it in VS Code to see the format (`BEGIN:VEVENT`, `SUMMARY:`, `DTSTART:`).

Treat that link like a password: anyone with it can see your Canvas calendar. Don't paste it into the repo or into chats.

---

## Step 5 · Make the fake sample data (45–60 min)

Graders and your demo use this, not your real data.

1. **`data/sample_calendar.ics`**: copy the structure of your real feed, then make up ~15 events across 3–4 fake courses (assignments, an exam, a project deadline). Put several in the same week so there's a "crunch week" to show later.
2. **`data/emails/`**: write ~30 short `.txt` emails, one per file, each starting with:
   ```
   From: Prof. Rivera <rivera@example.edu>
   Subject: Lab 6 moved to Friday
   Date: 2026-11-10 09:15

   Hi all, Lab 6 is now due Friday at 8pm...
   ```
   Mix them roughly: 12 important (deadline changes, exam info, TA messages), 12 noise (club newsletters, promos, campus events you'd skip), and 6 tricky ones that could go either way. Include dates written different ways ("Friday," "11/13," "tomorrow by 8pm") for the date-extraction step next week.

Data creation counts as non-coding time; keep the session descriptions specific.

---

## Step 6 · Write the code (2–3 hours across Sat–Sun)

Write these yourself, using the plan doc as a guide. Cite anything you base on the plan's sketches, and only keep code you can explain line by line.

1. **`models.py`**: `Item`, `Email`, and `Store` classes.
2. **`sources.py`**:
   - `parseIcs(text)`: turn the .ics text into a list of event dictionaries (remember to unfold wrapped lines).
   - A function that turns those events into `Item` objects, converting UTC times to Pittsburgh time.
   - A function that reads every file in `data/emails/` into `Email` objects.
3. **`storage.py`**: save the `Store` to `store.json` and load it back (sets become lists when saving).
4. **`tests.py`**: test functions for each of the above, using small hand-written inputs. Run them often.

Good checkpoint: running `tests.py` prints that all tests passed, and a quick script prints your sample items sorted by due date.

---

## Step 7 · Daily routine (every day you work)

1. `timelog start` before, `timelog stop "..."` after
2. Save any new AI prompts to `ai_prompts/`
3. Update `citations` if you used something new
4. Check off finished items in `PLAN.md`
5. `git add .` → `git commit -m "what you did"` → `git push` (from inside the project folder)

---

## End-of-week checklist

- [ ] `timelog` installed and working
- [ ] `time_log`, `ai_prompts/`, `citations` caught up and pushed
- [ ] Folder structure created
- [ ] Real Canvas feed in `data/private/` (not on GitHub)
- [ ] Sample calendar and ~30 sample emails in `data/`
- [ ] `models.py`, `sources.py`, `storage.py` working
- [ ] `tests.py` passing
- [ ] Pushed every day you worked
