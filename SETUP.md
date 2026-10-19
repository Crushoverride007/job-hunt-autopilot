# Setup (about 15 minutes)

## 1. Install the apps
1. Install **Claude Desktop** (claude.ai/download) and sign in.
2. Install **Claude in Chrome** from the Chrome Web Store and sign in with the same account.
3. In Chrome, log in to **LinkedIn**, **Indeed**, **StepStone** and **Monster** (create accounts
   yourself if needed).

## 2. Connect Notion and Gmail
In Claude: **Settings → Connectors** → connect **Notion** (required) and **Gmail** (optional).

## 3. Add the skill
1. Download this repo (Code → Download ZIP) or the `job-hunt-autopilot.skill` file from Releases.
2. In Claude: **Settings → Capabilities → Skills → Upload skill**, and choose the `.skill` file
   (or zip the `skills/job-hunt-autopilot` folder and upload that).

## 4. Start
Open a new chat in Claude Desktop (Cowork if available) and say:

> **Start my job hunt.** Here's my CV. (attach it)

Claude will interview you (goal, roles, countries, visa, salary, languages, deal-breakers),
build your answer bank and Notion workspace, and suggest 1-2 CV versions.

## 5. One-time profile cleanup (Claude will remind you)
- LinkedIn headline + location match your CV.
- **Upload your CV version(s) once to each platform's profile**: LinkedIn saved resumes,
  Indeed resume, StepStone profile, Monster profile. Easy Apply / quick-apply flows then reuse
  them, so no upload is needed per application. Only company career sites (Ashby, Workable...)
  need a fresh upload; Claude Desktop handles those from your computer.
- Delete outdated CVs (LinkedIn → Settings → Data privacy → Job application settings).
  Keep "save resumes and application data" **on**.
- Turn on daily job alerts.

## Daily use
Say **"continue the job hunt"**. Claude checks your inbox, finds new postings, fills a batch and
shows you a table. Reply **"send all"** (or "send 1-4, skip 5"). Everything is logged in Notion.

## Weekends
Few new postings and recruiters are offline. Skip or use the time for interview prep.

## CAPTCHAs
The skill never bypasses CAPTCHAs (it would break the sites' terms and risk account bans).
To keep them rare: stay logged in in the same Chrome profile, keep a human pace
(about 10-15 applications a day per site), and prefer Easy Apply / quick-apply. When one
appears, Claude pauses and you click it.

## Notes
- Notion's free plan allows 1 chart; the dashboard uses boards for the rest.
- Typing in some forms drops characters; the skill sets long answers directly and verifies.
- Your data stays in your own Claude, Notion and email accounts. Nothing in this repo contains
  anyone's personal data.
