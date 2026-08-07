# 📚 Learning Dictionary

A living reference of concepts, tools, and technologies encountered during the internship.
Topics are organized by tool or technology. Add new entries as you learn.

---

## How to Use
- Each technology gets its own section.
- Add a new `###` entry with the term or concept.
- Include a short definition, a note on where/when you encountered it, and any useful links.

---

## .NET MAUI

### What is MAUI?
**.NET Multi-platform App UI** — a framework for building cross-platform apps (Windows, macOS, Android, iOS) from a single C# codebase.
- **Encountered:** Initial setup week
- **Repo:** [LexiQuest](https://github.com/degasolutions/LexiQuest)

### LexiQuest
Internship project repo — a MAUI app built by Dega Solutions. Used as the main codebase for hands-on learning.
- **Encountered:** 2026-05-28 — cloned/accessed on GitHub and ran locally
- **Repo:** [degasolutions/LexiQuest](https://github.com/degasolutions/LexiQuest)

### MAUI workload & project tools
Visual Studio (or the .NET SDK) needs the **.NET MAUI** workload and related tooling installed before you can build and run a MAUI solution. “Project tools” here means the SDK, workloads, and dependencies the solution expects—not the app UI itself.
- **Encountered:** 2026-05-28 — installed/downloaded what LexiQuest needed, then got the app running
- **Notes:** First successful local run; spent time exploring the running app

### MAUI on Mac vs Windows (LexiQuest)
On Mac, LexiQuest may run the **UI only** while full app/package setup can fail on other machines (e.g. HP with package install issues). Platform and workload differences matter for what actually builds and runs locally.
- **Encountered:** 2026-05-31 — HP packages did not work; UI ran on Mac; may need supervisor guidance for full Mac support
- **Encountered:** 2026-06-02 — discussed Mac situation with Devon after pushing UI changes; exploring whether **storing data** (e.g. local/persisted data path) helps get the full app running on Mac
- **Encountered:** 2026-06-03 — phonics/sounds and media pages (video, sound, story) failed on Mac but differ from Devin’s Windows setup; platform-specific behavior matters for what “working” means

### Voice recognition (LexiQuest)
Speech/voice input used in the LexiQuest app—needed local setup and testing to confirm it works on Mac before debugging library/reading issues.
- **Encountered:** 2026-06-05 — got voice recognition working again after set up and test pass; ran additional speech recognition tests

### Reproducible-errors document
A written log of bugs or failures you can trigger reliably (steps, environment, expected vs actual)—helps Devin and future you fix library/reading issues without guessing.
- **Encountered:** 2026-06-05 — started while working on the library/reading task

### Library & reading (LexiQuest)
Features related to the **library** and **reading** flows in LexiQuest—current internship task from Devin after the Mac media-page fixes.
- **Encountered:** 2026-06-04 — new assignment from Devin; using a Cursor agent in the repo to explore and learn the code before editing
- **Encountered:** 2026-06-05 — spent time understanding the problem (including Cursor-assisted exploration); app tested locally with voice recognition confirmed

### Cursor agent in codebase
A Cursor agent session scoped to the LexiQuest project to explain code, suggest fixes, and help track what you learn while working on a task (e.g. library and reading).
- **Encountered:** 2026-06-04 — set up to support the library/reading fix and document progress

### Cross-platform testing (Mac vs Windows)
When one developer uses Windows and another uses Mac, features like **phonics, sounds, and media pages** may work on one OS and not the other. Testing only on your machine does not prove changes work for everyone—plan how to verify on both (second machine, CI, or supervisor review).
- **Encountered:** 2026-06-03 — after Devin conversation; fixed Mac pages with Cursor assistance but unsure how to validate changes across platforms

---

## Git & GitHub

### Pull Request (PR)
A request to merge your branch into another (usually `main`). Reviewers can comment, request changes, or approve.
- **Notes:** Add detailed steps here if the process gave you trouble — see journal for context.

### Clone vs Fork
- **Clone:** Copy a repo to your local machine.
- **Fork:** Copy a repo to your own GitHub account (used for open source contribution).

### GitHub Pages
Hosts static files (like `index.html`) from a repo as a public website. For a project repo, the URL is usually `https://<username>.github.io/<repo-name>/`.
- **Encountered:** 2026-05-28 — deploying the internship tracker (`Internship` repo)
- **Notes:** Use **GitHub Actions** as the Pages source when a workflow deploys the site; branch must match your default branch (`master` here). Add `.nojekyll` at the repo root so GitHub does not run Jekyll on plain HTML.

### GitHub Actions (Pages deploy)
Automated jobs defined in `.github/workflows/` (e.g. `static.yml`) that build and publish the site on push.
- **Encountered:** 2026-05-28 — fixed workflow branch, cleaned deploy artifact, excluded build output from the repo
- **Live site:** [aheiner2001.github.io/Internship](https://aheiner2001.github.io/Internship/)

### .gitignore
A file listing paths Git should not track or push—used here to keep **LexiQuest** (private) and `bin/`/`obj/` build folders out of the public tracker repo.
- **Encountered:** 2026-05-28 — before pushing tracker changes without publishing LexiQuest source

---

## Google Antigravity CLI

### Setup
- Sign up: [Google Developer Program](https://developers.google.com/program)
- Install: [Antigravity CLI](https://antigravity.google/product/antigravity-cli)
- Free plan: limited requests, resets every 4 hours. Type `/usage` to check.

---

## Slack

### Workspace Tips
- Use direct messages for quick questions to your supervisor.
- Keep a record of important instructions shared over Slack — paste them in your journal.

---

<!-- ADD NEW TECHNOLOGIES BELOW THIS LINE -->
