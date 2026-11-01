# Household Logbook

An offline web app (PWA) for the iPhone that keeps track of the house, the car, family dates, monthly commitments and long-term plans, with a monthly calendar of what's coming up.

**Open it:** https://danipuskas.github.io/Household/ in Safari → Share → **Add to Home Screen** (keep "Open as Web App" on). Open it once from the Home Screen while online; from then on it works offline.

## What's in it

- **Today** – a **This week** strip (duty days shaded), everything due in the next 45 days, the mandatory monthly base and the next balance check.
- **Search** (magnifier, top right) – finds anything: jobs and their steps, companies and phone numbers, plate and VIN, document numbers, payments and plans.
- **Photos and files** – attach photos, scans or PDFs to documents, jobs, service log entries (invoices), the car, companies and plans. Tap one to view it; Share saves or sends it.
- **Add to Calendar** – on any dated item, or "Add to Calendar" on Today for everything in the next 12 months. Each event has an alert at 9:00 the day before (documents also at their reminder date).
- **Roster** – CrewPulse writes the roster into the iPhone Calendar, which web apps can't read. A Shortcut (*Copy roster for Household*, steps in Calendar → Roster) copies the next 60 days as lines `HHR|start|end|all day|title|location`; then **Paste roster** in the app. A calendar file (.ics) works too. Duty days are shaded on the calendar and This week, and jobs on them are marked On duty. Entries containing words like OFF or LVE are ignored (editable).
- **Calendar** – month view with home and car jobs (future repeats outlined), car renewals, family dates, payments, plan targets and the balance-check day. Each type can be switched off.
- **Home** – the maintenance schedule (preloaded from the DLP homeowner's manual for a villa: AC every 4 months, water heater and water tank every 6 months and yearly, plus the "as needed" jobs), companies you trust with their numbers, and the service history. **Done** shows the job's checklist; pick the date it was really done and the next due date moves forward from there.
- **Car** – one or more cars with plate, VIN, odometer, insurance and registration renewal, warranty and service contract. Services can be due by date, by km, or both.
- **Family** – two parts:
  - **Dates:** birthdays and anniversaries (yearly), school dates and appointments.
  - **Documents:** passports, Emirates IDs, visas, licences, car and property papers, with number, expiry and a reminder window (30 days to 6 months). Add a scan with the camera (**Scan / photo**, with "Sharpen as document" to whiten the page) or a photo or PDF from Files. For a cropped multi-page scan, use Scan Documents in the Notes or Files app and attach the PDF.
- **Money** – recurring commitments (mortgage, loans, utilities, insurance, subscriptions) with the monthly base, and a monthly balance check: spent = previous balance + income − new balance, split into mandatory payments and everything beyond them.
- **Plans** – long-term goals with a target date and amount, and how much to set aside each month.

## Where the data is

Everything is stored on the iPhone, not on GitHub; the files here are only the empty app. Deleting the Home Screen icon deletes its data, so use one of the backups (⚙︎ button, top right):

- **Sync & backup** – while the app is open and online, it keeps the logbook in a **private** GitHub repository (e.g. `household-backup`): a few seconds after a change it goes up, and every minute it checks for changes from another iPhone. Each entry keeps its newest edit, deletions carry over, and photos and PDFs are uploaded once and downloaded on the other phone. Every save is kept as a version and can be restored. It needs a fine-grained access token limited to that repository with **Contents: Read and write**; the steps are shown in the app.
  - **Second iPhone:** on the first phone, Sync & backup → **Set up another iPhone** gives a setup code (it contains the token, so send it privately). On the other phone, install the app, paste the code in Sync & backup, Connect, and choose **Use the shared logbook**.
  - iOS doesn't let web apps run in the background, so syncing only happens while the app is open.
- **Back up to a file / Restore from a file** – share a JSON copy to Files or Notes, and restore it on this or another iPhone.

## Updating

A new version downloads in the background while the app is open and online. An **Update** button appears at the top; otherwise it's used the next time the app starts. Bump `CACHE` in `sw.js` and `APP_VERSION` in `index.html` together with every release.

Fonts: Barlow Condensed and IBM Plex (SIL Open Font License, see `fonts/`).
