# 📋 Project Tracker

An app-style, public project tracker that reads a Google Sheet **live**.
Edit the sheet → the page updates within a minute. No code, no redeploy.

**Live:** https://project-tracker-eight-gamma.vercel.app
**Data:** https://docs.google.com/spreadsheets/d/1gFCCXv0fcYUguKR7_atG0V7eZYt7RZvH4wiGpy64_Ak/edit

## Features

- **Three views:** Board (kanban by stage), Cards (illustrated), and List. Your choice is remembered.
- **Hero dashboard:** greeting, live summary, a pipeline bar, and stat tiles (click any of them to filter).
- **Illustrations:** a hand-drawn hero scene, plus unique generated cover art for every project.
- **Detail drawer:** click a project to see its progress stepper, next step, details, dates and an "Edit in sheet" link to that row.
- Search (⌘K or `/`), stage filters, sorting, dark/light mode, auto-refresh, and a mobile bottom nav.

## Sheet columns

The page matches columns by header name (case-insensitive). Column order doesn't matter.

| Column | Also accepted as | Used for |
|---|---|---|
| **Name** | Project, Title | Card title |
| **Status** | Stage, State | Status pill and automatic stage grouping |
| **Next Step** | Next, Action, To do | Highlighted "Next step" box |
| **More Details** | Details, Notes, Description | Description |
| **Important Dates** | Dates, Deadline, Due, Last update | Date chips with countdowns ("in 5 days") |
| **Image** *(optional)* | Cover, Photo, Picture | Paste an image URL to use a real photo as the project's cover |
| **Team** *(optional)* | Group | Which team a project belongs to (see below) |

Any other columns you add are shown in the project's detail drawer.

## Teams

Projects are grouped into **ISE Research Team** and **Personal**, with tabs to switch between them. The Hall of Fame is split the same way.

- Without a `Team` column, a project goes to the research team if its name contains "IRB" or matches one of: IGIE Case report, Gastric ESD, Bile CF DNA, ACG Pancreas Cyst, Foregut oncology. Everything else is Personal.
- Add a `Team` column to the sheet to control it yourself. Whatever you type there wins, and you can create new teams just by typing a new name.
- The team names and the matching list are in the `CONFIG` block of `index.html` (`RESEARCH_TEAM`, `PERSONAL_TEAM`, `RESEARCH_PROJECTS`).

## How statuses become stages

You can write statuses however you like. The page groups them by keywords:

| Stage | Matches words like |
|---|---|
| 🟦 In progress | in progress, edit, draft, working, shared, ready, 95% |
| 🟪 Submitted | submitted, under review, with editor, await, pending |
| 🟩 Approved (teal) | approved, cleared |
| ✅ Completed | published, presented, accepted, done, complete |
| 🟧 On hold | standby, on hold, paused, away, rotation |
| 🟥 Blocked | blocked, stuck, delayed, rejected |
| ⬜ Backlog | not started, planned, anything else |

Project types (IRB, Case report, Abstract, Paper, Review, Letter…) are detected from the name and get their own icon.

## One-time setup

The sheet must be readable by anyone with the link:
**Share → General access → Anyone with the link → Viewer.** (Only you can edit.)

## Customising

Edit the `CONFIG` block near the bottom of `index.html` to change the sheet (`SHEET_ID`, `GID`), the page title, or the refresh interval.
