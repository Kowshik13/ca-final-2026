# CA Final 2026 Study Hub

A single-file CA Final tracker for Koushika with the original dark-gold UI, chapter progress, rewards, notes, mock tests, a Pomodoro timer, reminders, and optional live Firebase sync.

## Features

- **Dashboard** with overall progress, today's focus, streaks, study velocity, and a daily motivation quote.
- **Subject trackers** for FR, AFM, Auditing, DT, IDT, and IBS.
- **Chapter milestones** for each chapter:
  - Lecture
  - Notes
  - Practice
  - Revision 1
  - Mock/Test
  - Revision 2
- **Reward system** that adds points as milestones are completed and gives a bonus when a chapter is fully done.
- **Quick notes** per chapter.
- **Mock test tracker** with paper-wise scores and pass/fail summary.
- **Pomodoro timer** with focus/break durations and session count.
- **Daily reminders** with browser notifications.
- **Backup / restore** via JSON export and import.
- **Live sync** with Firestore when configured, otherwise local storage mode.

## How To Use

### 1) Open the app

- Open [index.html](index.html) directly, or serve the folder with a local web server.
- If Firebase is not configured, the app still works in local-only mode.

### 2) Track a chapter

- Open any subject from the sidebar.
- Click a chapter card to open the chapter modal.
- Mark milestones as you complete them.
- Set clarity after you study the chapter.
- Add a chat link if you want to keep the Claude conversation URL.

### 3) Use rewards

- Each milestone completion adds reward points.
- Chapter completion gives an extra bonus.
- Reward points are recalculated from saved milestone state, so they stay consistent after refresh.

### 4) Plan your day

- The dashboard shows today's focus based on the current phase.
- The daily quote changes once per day.
- Study streaks and hours are updated from your logged activity.

### 5) Log mock tests

- Go to **Mock Tests**.
- Add scores for each paper in a test round.
- The app shows aggregate score and pass/fail status.

### 6) Use notes

- Go to **Notes**.
- Add mnemonics, traps, short rules, or revision points for any chapter.
- Notes save automatically after a short debounce.

### 7) Use the timer

- Go to **Timer**.
- Start, pause, reset, or skip focus/break sessions.
- Set focus and break durations if you want a different Pomodoro pattern.

### 8) Set reminders

- Go to **Settings**.
- Enable browser notifications.
- Choose a daily reminder time and save it.

### 9) Back up data

- Export your tracker state as JSON from **Settings**.
- Import the JSON later to restore the tracker.

## Live Sync

The app uses Firebase Firestore if the Firebase config in [index.html](index.html) is set up.

- When sync is available, updates are written to a shared Firestore document.
- If sync is offline or blocked, the app keeps working locally and queues writes.
- Local state is stored in the browser as a fallback.

## Reward Rules

- Lecture: 2 points
- Notes: 2 points
- Practice: 3 points
- Revision 1: 4 points
- Mock/Test: 5 points
- Revision 2: 6 points
- Full chapter completion bonus: 5 points

## Notes

- The app is designed to preserve the original gold aesthetic.
- No login flow is used for the Firestore sync path.
- If you want live sync, make sure the Firestore config and rules are set correctly.

## Suggested Workflow

1. Pick the current subject from the sidebar.
2. Complete the chapter lecture.
3. Mark notes, practice, and revision milestones as you finish them.
4. Update clarity after each serious revision pass.
5. Log mock scores when you take tests.
6. Check the dashboard daily for focus and motivation.

## Files

- [index.html](index.html) - main app and logic
- [README.md](README.md) - this guide
