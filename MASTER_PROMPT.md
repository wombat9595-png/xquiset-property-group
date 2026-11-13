# XQUISIT OS — master build brief

Paste everything below the line into Claude Code on Tatijana's computer, in a new empty folder called `xquisit-os`.

---

You are building XQUISIT OS: a single private web app that runs Tatijana Stevanovic's real estate business for her. She is the director and licensed agent of XQUISIT Property Group Pty Ltd in Canberra, ACT, and she works alone. She does residential sales and property management. Her current property management software (understood to be PropertyMe; confirm with her) is not working for her, and she spends her days doing administration that software and AI agents should be doing.

The goal is that she opens one dashboard in the morning, sees what needs her judgement, approves or edits what the agents have prepared, and gets on with the parts of the job only a person can do: meeting owners, showing homes, negotiating. Everything else is drafted, chased, scheduled, filed and reported for her.

This is a large project that will run over many sessions. Save this brief as `docs/BRIEF.md` in the project on your first turn, and keep `docs/PROGRESS.md` current as you work (what is built, what is verified, what is waiting on her, what is next), so that any later session can pick up from the files alone.

## 1. Who you are working with

Tatijana is an expert in real estate and not a software person. She will be the one sitting at this computer.

- Do the work yourself. Install what is needed, write the code, create the configuration, run the tests. Never ask her to choose between technical options; make the choice and tell her in one plain sentence what you chose if it affects her.
- Only ask for things that need her hands or her judgement: signing up for an account, entering a password or payment detail, approving something that goes to a client, or a real business decision. Batch these so she does them in one sitting, with numbered steps that say exactly what to click.
- Write to her in plain English. No jargon, no file paths, no code unless she asks. When you finish a piece of work, tell her what she can now do that she could not do before, and show her where to click.
- Never ask her to paste a password or API key into the chat. Have her put secrets into the hosting provider's settings page or a local `.env` file that you open for her.

## 2. What we know, and what to find out first

Known facts (from her public site and listings):

- Trading name: XQUISIT Property Group (note the spelling: no E at either end). Legal entity: XQUISIT Property Group Pty Ltd.
- Director and licensed agent: Tatijana Stevanovic. Solo operator.
- Phone +61 414 451 480, email info@xquisitpg.com.au, PO Box 3822, Manuka ACT 2603.
- Instagram `tatijana_xquisit`, Facebook `TatijanaXquisit`. Profiles on Allhomes, Domain and RateMyAgent with strong reviews.
- Her public website (xquisitpropertygroup.com.au) is currently a "coming soon" page.

Known complaints about her current software, as relayed by the person who commissioned this build:

> [Benji: paste here everything Tatijana has told you about what is wrong with her current software and what she wishes it did. The more specific, the better.]

Before designing anything, hold a short discovery conversation with her. Ask one question at a time, in plain language, and stop when you have what you need. You need to learn:

1. What software she uses today for property management, trust accounting, sales CRM, email, calendar, bookkeeping, e-signing and listing uploads, and what she pays for each.
2. Roughly how many properties she manages, how many owners, and how many sales listings she carries at a time.
3. The three tasks that eat the most of her week, and the three things that have gone wrong or nearly gone wrong in the last year (a missed renewal, an arrears case that dragged, an owner who complained).
4. Which bank holds her trust account and who her trust account auditor is.
5. Which tradespeople she uses regularly.
6. How she likes to be contacted by the system: email digest, SMS, phone notification.
7. What she would want to see on the screen first thing in the morning.

Write what you learn to `docs/DISCOVERY.md` and let it override the assumptions in this brief wherever they differ. She knows her business; this brief is a starting position.

## 3. Rules that hold throughout, and why

**Trust money stays in her existing audited system for now.** Rent, bonds and deposits held on behalf of clients are trust money under the ACT Agents Act. A trust account is audited every year and a ledger error can cost her licence. So in the first version, XQUISIT OS does not hold, move or act as the ledger of record for trust money. Her current trust accounting system and bank remain the source of truth. The OS imports their data (exports, statements, bank files), mirrors it, flags anomalies and prepares work for her; it never initiates a payment. Replacing the trust ledger is a separate later project that requires her auditor's sign-off before it starts. Tell her this plainly in the first session so she is not expecting otherwise.

**Nothing leaves the building without her approval until she says so.** Every email, SMS, notice, social post, listing, owner statement or payment instruction is prepared as a draft in an approvals queue. Each type of automation has its own switch with three positions: off, draft for approval, send automatically. Everything starts at "draft for approval". She promotes an automation to automatic only after she has seen it get things right. Formal legal notices (rent increases, notices to remedy, termination notices, entry notices) and anything involving money never go fully automatic. The reason is simple: an agent that sends a wrong legal notice to a tenant under her name creates a real liability, and she needs to trust the system before she will let it act.

**Tenancy law is looked up, cited and stored as data.** Do not rely on your memory for notice periods, inspection limits, rent increase rules or bond requirements. Read the current ACT legislation and official guidance (legislation.act.gov.au, the ACT Government renting pages, ACAT, the ACT Revenue Office for bonds) and build a `rules` table where every rule has a value, a plain-English summary, a source link and the date you checked it. Automations read from that table. Add a monthly job that re-checks the sources and flags changes to her. Topics to cover at minimum: rent increase frequency, notice and the cap on increase amount; routine inspection frequency and entry notice; arrears steps and timing from first missed payment to ACAT; bond lodgement and refund; break-lease and end-of-tenancy notice periods by reason; smoke alarm requirements; the minimum ceiling insulation standard for rentals (check its current phase-in status and deadline, which is close); energy efficiency disclosure in rental ads; and the requirements for sales (energy efficiency rating in ads, required contract documents, cooling-off). Where the law is unclear or a case is unusual, the system should say so and suggest she check with ACAT or her solicitor instead of guessing.

**Client data is private and stays in Australia.** She holds tenants' identity documents, payslips, bank details and home addresses. Host the database and file storage in an Australian region. Enforce access rules at the database level so an owner can only ever see their own properties and a tenant only their own tenancy. Keep an audit log of who viewed or changed what. Never put real client data in test fixtures, logs, screenshots or prompts to third-party services beyond what a task needs. Never commit secrets. Marketing messages need recorded consent and a working unsubscribe, as the Spam Act requires.

**Run in parallel before replacing anything.** She keeps her existing software until XQUISIT OS has run alongside it for at least one full month-end and she is satisfied. Never tell her to cancel a subscription; give her the evidence and let her decide.

**Tell her the truth about the state of things.** If something is not built, not tested, or not possible (see the constraints in section 7), say so. A dashboard that looks finished but quietly does nothing is the worst outcome here.

## 4. How it should be built

Recommended approach, which you may change if you find a good reason and record it in `docs/DECISIONS.md`:

- One web application, TypeScript, Next.js, with a Postgres database, authentication and file storage from a managed provider with a Sydney region (Supabase is the default choice), deployed to a managed host. Installable on her computer and her phone as an app icon, so "her dashboard" is one click and also works when she is at an inspection.
- Three kinds of sign-in: Tatijana (everything), owners (their portal), tenants (their portal). Row-level security from the first migration.
- Background jobs on a schedule and on events (a new email, a missed payment, a date approaching), so the system works while her laptop is closed.
- AI agents built on the Claude API with the Agent SDK. Use the strongest current model for reasoning-heavy work such as arrears strategy, legal-notice preparation, owner advice and appraisal narratives; a mid-tier model for everyday drafting; and the smallest model for high-volume classification like sorting the inbox. Check the current model list and pricing instead of assuming. Every agent action is logged with its inputs, output and cost, and visible to her.
- Before she signs up for anything, show her a one-page table of every account needed, what it is for and what it costs per month, and get her yes.
- Start with realistic invented demo data so she can see and react to the dashboard on day one, clearly labelled as demo, with one button to wipe it before real data goes in.
- Tests for anything involving dates, money or legal rules. An arrears calculation or a notice date that is off by one day is a real problem, so these get proper test coverage with edge cases (public holidays, weekends, leap years, mid-period rent changes).

## 5. What the dashboard contains

Think of what a well-run agency's whole back office does, then give a solo operator all of it. Each area below should be a section of the one app, sharing the same contacts, properties and history.

**Today.** The home screen. Money in and overdue, what needs her approval, today's appointments, anything with a deadline in the next 14 days, and a short morning brief written for her: what happened overnight, what the agents did, the three things that most need her today. One search box that finds any person, property or document. One "ask" box where she can type or dictate a question ("who is behind on rent?", "draft a renewal for 12 Smith St at $680") and get it done.

**Portfolio.** Every property, owner, tenant and tenancy, with a single timeline per property showing every message, job, inspection, payment and document. Keys register. Management agreements and their fee terms.

**Rent and arrears.** Rent roll mirrored from her trust system. Arrears detected daily, with a staged follow-up prepared for each case according to the ACT rules table: friendly reminder, firmer reminder, formal notice, ACAT preparation pack with the evidence assembled. Payment plans tracked. She sees each case's history and the next step with its earliest legal date.

**Maintenance.** Tenants report issues through their portal or by email or SMS, with photos. The system triages urgency (and treats anything that sounds like an urgent repair under the Act as urgent), checks the owner's approval limit, requests quotes from her preferred trades, schedules access with the tenant, follows up until the job is done, collects the invoice and photos, and closes the loop with tenant and owner. She approves spend above the owner's limit and anything unusual.

**Inspections.** Routine, entry and exit inspections scheduled within the legal limits, entry notices prepared with the right notice period, routes planned for the day. On her phone at the property: room-by-room checklist, photos, dictated notes. The system turns that into a finished report for the owner, a list of maintenance items and a follow-up for the tenant. Exit reports compared against the entry report for bond claims.

**Compliance.** Smoke alarms, insulation standard, pool safety where relevant, landlord insurance expiry, gas and electrical checks, her own licence, professional indemnity insurance, CPD and trust audit dates. Colour-coded, with jobs raised automatically before anything expires.

**Leasing.** Vacancy pipeline from notice to vacate through to keys handed over. Rental listing copy and a rent recommendation prepared from the property record. Enquiries answered and viewing times booked. Applications collected through a branded form, summarised and ranked against her criteria with the reasoning shown (and with her making the decision, so screening stays fair and lawful). Lease documents and bond paperwork prepared. Move-in checklist.

**Renewals and rent reviews.** Every lease end date and rent review date tracked. Well ahead of each date, a recommendation for the owner with comparable evidence, the lawful increase limit and notice date from the rules table, and the draft letters ready to go.

**Sales.** Her sales CRM: prospects, appraisals, listings, buyers, offers and contracts through to settlement. Appraisal packs and listing proposals drafted in her brand. Open-home attendee capture on her phone with same-day follow-up. Buyer matching against new listings. Weekly vendor reports written automatically from enquiry and inspection activity. Settlement milestones and key dates tracked. Past clients kept warm with anniversaries and local market updates.

**Inbox.** Her email, SMS and portal messages in one place, each linked to the right person and property, sorted by what needs action, with a reply already drafted in her voice. Learn her voice from sent messages she approves.

**Money.** Read-only mirror of the trust ledger and month-end. Supplier bills read and matched to jobs and properties, prepared for payment in her trust system. Owner statements explained in plain English alongside the official one. Month-end checklist that walks her through reconciliation and flags anything that does not tie out. Her own business bookkeeping feed (Xero or whatever she uses): fees earned, expenses, BAS reminders. Financial-year summaries for owners at tax time.

**Owner portal and tenant portal.** Owners: statements, the property timeline, inspection reports, approvals for maintenance quotes and renewals, documents. Tenants: rent position, report and track a repair, inspection times, documents, messages. Branded, simple, phone-first.

**Marketing studio.** A marketing agent that plans a content calendar, turns each new listing, sale, lease and review into Instagram and Facebook posts, reels scripts, a monthly email to her database and a suburb market update. Listing copy and brochure drafts. Just-listed and just-sold campaigns. Review requests after every settlement and lease signing, feeding RateMyAgent and Google. Tracks what gets enquiries. Posts only after approval.

**Growth.** New-business pipeline for winning managements and listings: landlord leads, referral partners, expired or stale listings to follow up, owners in her portfolio who may be ready to sell, and a simple rent-roll growth target with progress.

**Business health.** Properties under management, fee income, vacancy rate and days vacant, arrears percentage, maintenance turnaround, renewals retained, sales pipeline value, hours the agents saved her. One page she could hand to an accountant or a buyer of the rent roll.

**Automations.** The list of everything the system does on its own, each with its off / draft / automatic switch, its recent activity and its error count. A log of every agent action. She should always be able to answer "why did the system do that?"

**Documents and templates.** Every file stored against the right record. Her letter, email and SMS templates with merge fields, pre-filled with good defaults for ACT.

## 6. The agents

Build these as distinct workers with clear jobs, each writing into the approvals queue and the property timeline: a chief of staff (morning brief, weekly review, answers her questions, coordinates the others), inbox triage, arrears, maintenance coordinator, inspections, compliance, leasing, renewals, sales assistant, bookkeeper and month-end, owner reporting, marketing, and growth. For each one, define what triggers it, what it is allowed to do alone, what needs her approval, and how its work is checked. Start each narrow and reliable; widen its authority only as she switches things to automatic.

## 7. Constraints to be honest about

Check each of these yourself, since access programmes change, and tell her where things stand:

- **Listing portals.** Publishing to realestate.com.au, Domain and Allhomes normally goes through an approved software provider's feed. A custom system may not get that access. The fallback is to prepare the complete listing in XQUISIT OS and have her existing uploader or the portals' own agent sites do the publish step.
- **Her current software's data.** PropertyMe and similar systems restrict API access to approved partners. Plan to migrate and sync using their report exports and scheduled files, and ask whether partner access is obtainable.
- **Bank feeds and payments.** Not in scope while trust money stays in her existing system.
- **Property data.** Sales comparables and valuations from CoreLogic or PropTrack are paid licences. Use what she already subscribes to; otherwise work from public sales records and her own history, and say which was used.
- **SMS and email sending.** Need an Australian sender ID and a verified sending domain, which take a few days to approve. Start these early.
- **Meta posting.** Needs her Facebook business account connected and app approval; until then the marketing studio produces ready-to-post content she can publish in two taps.

## 8. How it should look

Her brand is matte black and gold, and she cares about how things look. The app should feel like a private members' club, not accounting software.

Take the palette from her site and extend it carefully:

- Blacks: `#070707` page, `#0F0F0F` and `#151515` surfaces, soft warm-charcoal gradient on raised cards.
- Gold: `#AF9B60` primary accent, `#C4BC96` pale gold for secondary accents and hover.
- Text: `#FFFFFF` and warm off-white `#F6F3EC`, with `#BEB9AD` for secondary text.

Matte means no gloss, no neon, no heavy drop shadows. Gold is used sparingly: a hairline at the top of a card, an icon, a key number, the primary button outline. If everything is gold, nothing is. Status colours (overdue, due soon, done) need to be clearly readable on black without fighting the gold; test them for contrast.

The logo is a bold geometric X made of layered gold chevrons followed by "QUISIT PROPERTY GROUP" in a clean uppercase geometric sans. Ask her for the original logo files; until she provides them, use the image from her site. Use the X mark alone as the app icon, the loading mark and the sign-in screen centrepiece. Headings in a geometric sans that matches the wordmark, with generous letter-spacing on small uppercase labels; body text in something highly readable. Rounded cards with a fine border, pill-shaped outlined buttons, plenty of breathing room.

It must work as well on her phone as on her computer, since inspections and open homes happen on the phone. Provide a light theme for the owner and tenant portals and for printing. Before you show her any screen, look at it yourself in a browser at phone and desktop widths and fix what looks off. Owner-facing documents (appraisals, vendor reports, inspection reports, statements) should carry the same brand and look good enough to win her business.

## 9. Order of work

Each stage ends with something she can use and a short demonstration. Do not start a stage until the previous one is verified working.

1. **Setup and first look.** Discovery conversation, cost table, accounts, install, deploy. The branded shell with sign-in, the Today screen and the Portfolio on demo data. She reacts; you adjust.
2. **Her real data.** Import properties, owners, tenants, tenancies, rent roll and documents from her current system's exports. Reconcile counts and totals against the source and show her the comparison.
3. **Daily operations.** Inbox, approvals queue, arrears, maintenance, and the morning brief. This is the point where it starts saving her time every day.
4. **Calendar-driven work.** Inspections, compliance, renewals and rent reviews, with the ACT rules table verified and cited.
5. **Leasing and sales.** Vacancy pipeline, applications, sales CRM, vendor reports, open-home capture.
6. **Portals.** Owner and tenant portals, invited a few friendly clients at a time.
7. **Marketing and growth.** Marketing studio, review requests, new-business pipeline.
8. **Money and month-end.** Ledger mirror, bills, month-end checklist, business health. Run one full month-end in parallel with her existing system.
9. **Handover.** A plain-English guide written for her, automatic daily backups with a tested restore, monitoring that alerts her and the person supporting her if a job fails, and a walk-through of every section.

At the end of each working session, update `docs/PROGRESS.md` and tell her in a few sentences: what now works, what you need from her, and what comes next.

## 10. What done looks like

She opens one app, on her computer or phone, in her brand. Her whole portfolio and pipeline are in it and match her system of record. Every recurring task in her week is either done by an agent or waiting in one approvals queue with the work already prepared. No date is ever missed, because every deadline is tracked and raised early. Every rule the system applies cites its source. She can see and switch off anything the system does. Her data is backed up, private and hers to export at any time. And she has stopped doing the administration that was the reason for building this.
