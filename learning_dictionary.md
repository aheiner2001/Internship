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

## Discord (Realm website project)

### Discord server setup & permissions
Devin's website (**Realm**) uses a Discord server as its community/forum backend. Getting admin/**Manage Server** permissions from Devin was the first step before any bot or channel config could happen.
- **Encountered:** 2026-08-11 — contacted Devin a couple of times to get permissions and admin access on the Discord server
- **What worked:** Ask the server owner directly for **Manage Server** permission — it's required later to configure channels in the AnswerOverflow dashboard.

### Discord bot (Realm Bot)
A bot that must be invited to the server and stay online/connected in order for indexing and real-time sync (Discord → website) to work at all.
- **Encountered:** 2026-08-11 — confirmed working when local terminal logs showed `Logged in as Realm Bot`
- **What worked:** Keep the dev process (`bun dev`) running continuously; indexing only happens while the bot is connected. If you restart, wait for the "Logged in" message again before testing.

### Discord invite links (branded)
The invite section on the website can be configured to point to a specific server/owner identity rather than a generic one.
- **Encountered:** 2026-08-11 — changed the invite section so it shows **Devin's name** instead of the intern's, so visitors join the right community under the right identity.

---

## AnswerOverflow (self-hosted forum sync)

### What is AnswerOverflow?
A tool that indexes Discord forum-channel threads into a database and republishes them as a searchable, public web archive — used here to power the `/forum` page on Devin's website.
- **Encountered:** 2026-08-11 — connected AnswerOverflow to sync Discord threads to the site

### Local vs. hosted AnswerOverflow (important distinction)
Running AnswerOverflow locally (`localhost:3000`) spins up **your own empty Convex database** — it does **not** pull in threads from the public [answeroverflow.com](https://www.answeroverflow.com) site. Seeing "0 messages / 0 threads" on localhost is expected until your **local bot indexes Discord into your local DB**.
- **Encountered:** 2026-08-11/12 — confused at first by an empty local forum vs. the populated public site; these are two separate deployments/databases.

### Localhost developer mode (why threads weren't showing)
Threads didn't appear on localhost until a specific developer mode was enabled — this was the key blocker before things started working.
- **Encountered:** 2026-08-11 — AI helped identify that a developer-mode setting on localhost was required to see synced threads
- **What worked:** Enable the relevant local/developer mode, then confirm indexing against the correct URLs (not the Convex admin page).

### Correct local URLs to use
- **Public archive** (what `/forum` embeds): `http://localhost:3000/c/<channel-id>`
- **Operator dashboard**: `http://localhost:3000/dashboard/<channel-id>`
- **Do NOT use** `http://127.0.0.1:3210` — that's Convex's raw DB admin page, not the forum.
- **Encountered:** 2026-08-12 — clarified after initial confusion about which local port/page was the real forum output.

### Enabling indexing per channel
Indexing must be turned on **per forum channel** in the AnswerOverflow dashboard (Dashboard → Channels → toggle **Indexing Enabled**). Regular text channels should stay off.
- **What worked:** Only enable indexing on the specific forum channels Devin wants public (e.g. tutorials, help, bug reports).
- **Gotcha:** The bot also needs **View Channel** and **Read Message History** permissions on that channel, or indexing silently skips it.

### Indexing timing (bulk vs. real-time)
- **Bulk/historical** indexing runs on a scheduled job roughly every 6 hours (not instant).
- AnswerOverflow's own UI estimate ("backfill in 1–2 days") is conservative/optimistic messaging, not a hard rule.
- **New** forum posts should sync closer to real-time, but only if indexing is ON for that channel and the bot is online.
- **What worked:** Test with a **new** forum post in an indexed channel rather than waiting on old/historical threads.

### PostHog analytics errors (safe to ignore locally)
The dashboard's page-view/invite-click charts call PostHog for analytics. Locally this throws `PostHog ApiKey is required`, showing as "Sorry, we encountered an error loading the data."
- **Encountered:** 2026-08-11/12 — this error is cosmetic for local dev and does **not** block thread indexing or the public forum page. No action needed unless analytics themselves are required.

### Disk space as a hidden blocker
Convex and Turbopack can fail to write (and fail **silently**) if local disk space is low, which can look like an indexing bug.
- **What worked:** Keep several GB free locally before debugging further indexing issues.

### End-to-end "what working looks like" checklist
1. `bun dev` running, bot logged in (see "Logged in as Realm Bot" in terminal)
2. Target forum channels have **Indexing Enabled** ON in the dashboard
3. New forum post created in one of those channels
4. `localhost:3000/c/<channel-id>` shows the thread (minutes for real-time, hours for bulk history)
5. `localhost:5173/forum/` shows the same content in the embedded iframe
- **Encountered:** 2026-08-12 — used this checklist to confirm the integration was fully working before reporting it done.

---

## AWS

### Planned integration (not started yet)
Discussed with Devin as the next step to make the form/site publicly accessible online (rather than only running on localhost).
- **Encountered:** 2026-08-11 — asked Devin whether to start AWS integration; not yet begun.

---

<!-- ADD NEW TECHNOLOGIES BELOW THIS LINE -->

AnswerOverflow (self-hosted forum sync)
Gotchas & Root Causes: Port Collisions & Disk Space
Multiple instances of `bun dev` can collide on ports 3000 and 3210[cite: 1]. If Next.js jumps to port 3001 while the iframe expects 3000, or if Convex fails to bind to port 3210, the app returns errors[cite: 1]. Additionally, low disk space (`No space left on device`) can cause silent writes or Next.js compile failures (e.g., returning 500 or hard 404 errors)[cite: 1].

What worked: Kill all conflicting `bun` processes (`lsof -nP -iTCP:3000` / `3210`), free up a few GB of disk space, clear `.next` cache (`rm -rf apps/main-site/.next`), and restart a single clean `bun dev` stack[cite: 1].

Server Permission Hierarchy for Dashboard Access
Answer Overflow only displays a server in the user dashboard if the user is the Owner, an Administrator, or has the **Manage Server** permission (labeled "Manage Guild" in AO's UI)[cite: 1]. A standard "Moderator" role without Manage Server will cause the server to stay hidden[cite: 1].

What worked: Ensure the server owner grants "Manage Server" or adds the Moderator role as a "Dashboard Role" under AO settings[cite: 1]. Then sign out and sign back in with Discord to refresh permissions[cite: 1].

Forum Channels vs. Text Channels Indexing
AO is optimized for **forum channels** (used for tutorials, help requests, bug reports)[cite: 1]. While text channels can be indexed with threads enabled, text chat streams tend to cause noise and low-quality website feeds[cite: 1].

What worked: Explicitly turn **Indexing Enabled ON** only for specific forum channels in the dashboard, and leave text channels turned OFF[cite: 1].

Local DB vs. Hosted Database Isolation
Running AO locally (`localhost:3000`) communicates with a **local Convex database** (`127.0.0.1:3210`), which is completely isolated from the production `answeroverflow.com` database[cite: 1]. Content existing on `answeroverflow.com` does not automatically backfill into local dev[cite: 1].

What worked: Confirm indexing against the correct local community URL (`http://localhost:3000/c/<channel-id>`) rather than expecting hosted data to appear locally[cite: 1].

Disabling Next.js Local Dev Indicators for Clean Embeds
When embedding local Next.js applications into static pages via iframes, the Next.js dev tools badge ("N" / Issues indicator in the bottom-left) can overlay the UI[cite: 1].

What worked: Set `devIndicators: false` in `next.config.js` to hide local dev indicators and keep iframe embeds clean[cite: 1].

GitHub Pages vs. Localhost Iframe Limitations
Static sites deployed via GitHub Pages cannot display embedded content referencing `http://localhost:3000` because end-users cannot reach the local machine, and HTTPS pages block insecure HTTP embeds[cite: 1].

What worked: Use `localhost` exclusively for local development[cite: 1]. For production/GitHub Pages, update the iframe `src` to point to a publicly accessible, hosted domain or reverse proxy[cite: 1].
