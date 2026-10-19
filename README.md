# Job Hunt Autopilot

A Claude skill that runs your job search like a good assistant: it learns your CV once, sets a
goal (e.g. **30 applications**), searches **LinkedIn, Indeed, StepStone and Monster**, filters out
jobs you can't or don't want to do, adjusts your CV per job without inventing anything, fills the
forms, and logs everything with analytics in **Notion**.

Your part: answer a 10-minute onboarding once, then reply **"send all"** to each batch of ~10.

> Every rule in `references/` comes from something that went wrong at least once in a real
> job search.

## What it does

| Step | Who |
|---|---|
| Onboarding interview + answer bank from your CV | Claude (asks you once) |
| Notion workspace: applications DB, dashboard, follow-ups | Claude |
| Daily search on 4 job sites, newest first | Claude |
| Vetting: language, sponsorship, seniority, deal-breakers | Claude |
| CV version per job (tailored only for top matches) | Claude |
| Filling forms from the answer bank | Claude |
| **Approve a batch of ~10 with one reply** | **You** |
| Submit, confirm, log, set follow-up dates | Claude |
| Inbox check: replies, rejections (with reasons), drafts | Claude (you approve sends) |
| Log in to job sites, solve CAPTCHAs | You |

## Why there's still an approval step
Applications are sent in your name and include salary, visa status and consents. Job sites also
pre-fill wrong answers (we saw "authorized to work: Yes" and "8 years EKS" next to "2 years AWS")
and some forms silently drop typed characters. One reply per batch catches these. Job sites
also restrict accounts that apply like bots, so the skill keeps a human pace.

## Requirements
- Claude (Pro or higher) with **Claude Desktop / Cowork** for CV uploads from your computer
  (web chat works for LinkedIn Easy Apply only)
- **Claude in Chrome** extension, signed in with the same account
- **Notion** connector (free plan works) and **Gmail** connector (optional, for inbox checks)
- Accounts on the job sites you want to use

## Install
See **[SETUP.md](SETUP.md)** (about 15 minutes).

## Repo layout
```
skills/job-hunt-autopilot/
  SKILL.md                      main workflow + non-negotiables
  references/
    onboarding.md               first-run interview + Notion setup
    answer-bank-template.md     everything forms ask, answered once
    filters.md                  auto-skip rules + grey zone
    form-gotchas.md             LinkedIn / Ashby / Workable / SmartRecruiters quirks
    cv-tailoring.md             adjust CVs without fabricating
    messages.md                 batch table, recruiter replies, follow-ups
    notion-schema.md            database DDL + free-plan dashboard
SETUP.md                        install guide for a new user
```

## Credits
CV-tailoring rules borrow ideas (anti-fabrication, AI-word avoidance, multi-reader critique) from
[claude-resume-kit](https://github.com/ARPeeketi/claude-resume-kit) (MIT).

## License
MIT
