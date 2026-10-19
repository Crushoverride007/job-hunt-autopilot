# Notion workspace

## Page "Job Hunt - <Name>" sections (in this order)
1. Goal (callout): "<N> applications by <date> - progress <x>/<N>"
2. All applications (child database below) + "How to log a reply" toggle
3. Plan (daily loop, weekly tasks, auto-skip rules, rules that never change)
4. Answer bank (answer-bank-template.md)
5. Backlog (leads not applied yet)
6. To do (one-time checklist)
7. Dashboard (views appended last, see below)

Add views LAST and append them at the end of the page. Rewriting a page that already contains
inline views can scramble their positions.

## Database "Applications" (Notion SQL DDL for notion-create-database)
```
CREATE TABLE ("Role" TITLE, "Company" RICH_TEXT,
 "Country" SELECT('Ireland':green,'Portugal':red,'Germany':yellow,'Netherlands':orange,'Belgium':brown,'Spain':pink),
 "City" RICH_TEXT,
 "Status" STATUS('Applied':gray:to_do,'Followed up':blue:in_progress,'Recruiter reply':purple:in_progress,'Interview':orange:in_progress,'Offer':green:complete,'Rejected':red:complete,'Ghosted':gray:complete,'Skipped':brown:complete),
 "Response" SELECT('No reply yet':gray,'Positive':green,'Screening call':blue,'Rejection':red,'Auto-rejection':pink),
 "Rejection reason" SELECT('Visa / sponsorship':red,'Experience / seniority':orange,'Language':yellow,'Skills gap':purple,'Location / residency':brown,'Role filled':gray,'No reason given':default),
 "CV version" SELECT('Version A':blue,'Version B':orange),
 "Channel" SELECT('LinkedIn Easy Apply':blue,'Indeed':purple,'StepStone':green,'Monster':pink,'Company site':gray,'Recruiter agency':yellow),
 "Applied on" DATE, "Salary" RICH_TEXT, "Contact" RICH_TEXT, "Contacted" CHECKBOX,
 "Follow-up date" DATE, "Link" URL, "Notes" RICH_TEXT)
```
Adjust Country options and CV version names to the user.

## Views (Notion free plan = 1 chart; use boards for the rest)
- Chart (column): FILTER Status != Skipped; GROUP BY Status - "Funnel"
- Board: GROUP BY Response - response rate (counts in column headers)
- Board: GROUP BY Country
- Board: GROUP BY CV version - A/B test
- Board: FILTER Rejection reason not empty; GROUP BY Rejection reason
- Board: GROUP BY Channel - which platform works
- Table: Status in (Applied, Followed up) AND Follow-up date <= today - "Follow-ups due"

## Logging rules
- One row per application, including skipped postings (Status = Skipped, reason in Notes).
- Applied on = today; Follow-up date = +7 days.
- When a reply arrives: update Status, Response and (if rejected) Rejection reason.
- Keep the row's page ID from the create response; you need it for later updates.
