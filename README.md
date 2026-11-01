# Household Logbook

An offline web app (PWA) for the iPhone that keeps track of the house, the car, family dates, monthly commitments and long-term plans, with a monthly calendar of what's coming up.

**Open it:** https://danipuskas.github.io/Household/ in Safari → Share → **Add to Home Screen** (keep "Open as Web App" on). Open it once from the Home Screen while online; from then on it works offline.

## What's in it

- **Today** – everything due in the next 45 days, the mandatory monthly base and the next balance check.
- **Calendar** – month view with home and car jobs (future repeats outlined), car renewals, family dates, payments, plan targets and the balance-check day. Each type can be switched off.
- **Home** – the maintenance schedule (preloaded from the DLP homeowner's manual for a villa: AC every 4 months, water heater and water tank every 6 months and yearly, plus the "as needed" jobs), companies you trust with their numbers, and the service history. **Done** shows the job's checklist; pick the date it was really done and the next due date moves forward from there.
- **Car** – one or more cars with plate, VIN, odometer, insurance and registration renewal, warranty and service contract. Services can be due by date, by km, or both.
- **Family** – birthdays and anniversaries (yearly), document renewals, appointments.
- **Money** – recurring commitments (mortgage, loans, utilities, insurance, subscriptions) with the monthly base, and a monthly balance check: spent = previous balance + income − new balance, split into mandatory payments and everything beyond them.
- **Plans** – long-term goals with a target date and amount, and how much to set aside each month.

## Where the data is

Everything is stored on the iPhone, not on GitHub; the files here are only the empty app. Deleting the Home Screen icon deletes its data, so use one of the backups (⚙︎ button, top right):

- **Online backup** – while the app is open and online, it saves a copy to a **private** GitHub repository (e.g. `household-backup`) about a minute after a change. Every backup is kept as a version and can be restored. It needs a fine-grained access token limited to that repository with **Contents: Read and write**; the steps are shown in the app. iOS doesn't let web apps run in the background, so backups only happen while the app is open.
- **Back up to a file / Restore from a file** – share a JSON copy to Files or Notes, and restore it on this or another iPhone.

## Updating

A new version downloads in the background while the app is open and online. An **Update** button appears at the top; otherwise it's used the next time the app starts. Bump `CACHE` in `sw.js` and `APP_VERSION` in `index.html` together with every release.

Fonts: Barlow Condensed and IBM Plex (SIL Open Font License, see `fonts/`).
