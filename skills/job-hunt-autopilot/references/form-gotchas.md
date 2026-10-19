# Form gotchas (learned the hard way)

## LinkedIn Easy Apply
- **Pre-selected CV = last used, not the right one.** Always check the Resume block on the
  Review screen and switch if needed.
- **Pre-filled answers come from earlier applications and can be wrong or impossible**
  (e.g. "authorized to work in Germany: Yes", "8 years EKS" next to "2 years AWS").
  Check every pre-filled field against the answer bank.
- Some numeric fields reject text ("4 years" -> type "4"); some text fields have character limits.
- Contact email defaults to the LinkedIn account email; make sure it's the answer-bank email.
- After submitting, LinkedIn may open "similar jobs" or another Apply dialog. Never submit a
  form you didn't vet; if forms appear that you didn't open, stop and tell the user.
- Easy Apply may hand off to ATS forms (SmartRecruiters, Workable) with extra pages:
  work history, education, salary, diversity, privacy consent.
- Closing a half-filled dialog asks "Save this application?" - choose Discard for skipped jobs.

## Typing
- Typing long text into some forms **drops characters** ("ISO 7001", "a eam").
  Set long answers with a direct value-setting tool (form_input), then zoom in to verify.
- Fields filled with a value-setting tool may not register in React forms (seen on Ashby):
  if validation says a filled field is empty, click into it and type it again.

## ATS platforms
- **Ashby**: CV upload required; answers can reset after upload - recheck.
- **Workable**: "Optional" salary fields may still be required (asterisk). Use "Negotiable".
  Privacy-consent checkbox is required.
- **SmartRecruiters**: multi-page (experience, education, diversity, consent). Some salary
  fields accept numbers only.
- **JOIN**: separate Terms & Privacy acceptance - only if pre-approved.

## Uploads
- Prefer flows that reuse a CV stored on the platform (LinkedIn saved resumes, Indeed resume,
  StepStone/Monster profile). Ask the user to upload CVs to each platform once.
- Company career sites need a fresh upload: works from Claude Desktop / Cowork with local files.
  In web chat it isn't possible; ask the user to attach the file.

## CAPTCHAs
- Never bypass or use solver services. Pause and ask the user to solve it.
- Keep a human pace and stay logged in to keep them rare.

## Cookie banners
- Choose "Necessary only" / decline non-essential.
