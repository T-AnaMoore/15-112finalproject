# Daily Debrief: 15-112 Term Project Plan

A desktop app that reads my Canvas calendar feed and exported emails, pulls out what matters, and opens each day with a ranked debrief: what's due, what's coming, and which weeks will be heavy.

**Goal:** finish by **Thu Dec 3 at 3pm**, 24 hours before the repo is downloaded on Fri Dec 4 at 3pm.

To check something off, change `- [ ]` to `- [x]`, then commit and push.

## Deadlines

| Date | Deadline |
| --- | --- |
| Fri Nov 13, 8pm | Term Project Mentor Sign-Up Form ✅ |
| Fri Nov 13, 11:59pm | GitHub Username Collection Form ✅ |
| Mon Nov 23, 8pm | Mentor Meeting #1 |
| Mon Nov 30, 8pm | Mentor Meeting #2 |
| Fri Dec 4, 3pm | Repo downloaded as my submission (no changes 3–4pm) |
| Fri Dec 4, 7pm | Project Showcase (required) |
| Fri Dec 4, 11:59pm | Corrections only, if a TA emails me |
| Sat Dec 5, 8pm | Oral assessment (required) |

## Every day I work on the project

- Log the session in `time_log` (date, start, end, minutes, what I did)
- Save AI prompts and responses in `ai_prompts/`
- Update `citations`
- Commit and push to GitHub

## Week 1 · Thu Nov 12 – Sun Nov 15: setup and data in

- [x] Mentor Sign-Up Form
- [x] GitHub Username Form
- [x] Set up git, clone repo, add `.gitignore`
- [x] Start `time_log`, `ai_prompts/`, `citations`
- [ ] Download my Canvas calendar feed into `data/private/`
- [ ] Build a fake sample calendar feed and ~30 fake emails in `data/`
- [ ] `models.py`: `Item`, `Email`, `Store`
- [ ] `storage.py`: load and save `store.json`
- [ ] `sources.py`: parse the .ics feed into items; read email files
- [ ] Tests for everything so far

## Week 2 · Mon Nov 16 – Sun Nov 22: Midterm 2 week, then build day

- [ ] Mon–Tue: date extraction from email text, with tests
- [ ] Simple rule-based important/noise sorting
- [ ] Wed–Thu: study for Midterm 2 (Thu Nov 19); no project work required
- [ ] Sat Nov 21 (Hack112, if I go): debrief and to-do screens
- [ ] Sun: priority ranking
- [ ] Prep for Mentor Meeting #1: show data loading and first screens

## Week 3 · Mon Nov 23 – Sun Nov 29: MVP, then Thanksgiving

- [ ] Mon Nov 23 by 8pm: Mentor Meeting #1 (be early)
- [ ] Duplicate merging
- [ ] MVP working by Tue Nov 24: sources in, debrief and ranked to-do out
- [ ] Thanksgiving: Naive Bayes classifier and inbox triage screen

## Week 4 · Mon Nov 30 – Thu Dec 3: finish 24 hours early

- [ ] Mon Nov 30 by 8pm: Mentor Meeting #2 (demo the MVP)
- [ ] Mon: week view with crunch heatmap
- [ ] Tue: visual polish and grading shortcuts
- [ ] Wed Dec 2: code complete
- [ ] Wed Dec 2: `readme` with feature list and grading shortcuts
- [ ] Wed Dec 2: record the ≤2-minute video, upload it, put the link in `video_link`, test it in an incognito window
- [ ] Thu Dec 3 by 3pm: run `main.py` from a fresh clone, check every required file, final push

## After submission

- [ ] Fri Dec 4: don't touch the repo 3–4pm; Showcase at 7pm; check email for correction requests
- [ ] By Sat Dec 5, 8pm: oral assessment; re-read every non-exempt line beforehand

## Required files

| File | What goes in it |
| --- | --- |
| `main.py` | The file graders run to start the app |
| `readme` | Feature list, how to see each feature, grading shortcuts |
| `time_log` | Total minutes at the top, then one entry per session |
| `ai_prompts/` | Every AI prompt and response, at least 5 thoughtful ones |
| `citations` | Every resource and AI tool used, with a line on how |
| `video_link` | Public YouTube or Google Drive link to the ≤2-minute demo |

## Grading shortcut ideas

| Key | Shortcut |
| --- | --- |
| `1` | Load the sample inbox and calendar |
| `2` | Jump to a crunch week so the debrief warnings show |
| `3` | Train the classifier on 10 labeled emails and re-sort the inbox |
| `4` | Open the week view with the heatmap filled in |
| `0` | Reset to an empty app |

## Questions for my mentor

- Does a from-scratch Naive Bayes classifier, date extraction, and priority ranking meet the sophistication bar?
- Is a fake sample inbox and calendar fine for grading, with my real data kept out of the repo?
- Which grading shortcuts would be most useful?
- What does the oral assessment usually ask?

## After the course (winter break)

1. Job application tracker (applied → interview → offer or rejected)
2. Live Gmail sign-in (read-only)
3. Live Canvas connection
4. Automatic daily run
5. Debrief delivered by email, then phone notifications
6. Web app interface, then a home-screen widget
