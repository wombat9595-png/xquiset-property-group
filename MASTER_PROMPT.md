# XQUISIT OS: master build prompt

For Tatijana Stevanovic, XQUISIT Property Group Pty Ltd, Canberra ACT.
Version 2, 13 November 2026. Legal facts below were checked against ACT Government sources on that date.

This file has two parts.

- **Part A** is for Tatijana: how to get set up, in plain steps, before anything is pasted.
- **Part B** is the prompt itself. Copy everything from the line `START OF PROMPT` to `END OF PROMPT` and paste it into Claude Code as the first message.

---

## PART A: Getting set up (about 30 minutes, no technical knowledge needed)

### What you need before you start

1. A computer (Mac or Windows) with a stable internet connection.
2. A Claude subscription. **Claude Max** is recommended while the system is being built, because the build is large and runs over many sessions. Once it is built and running, you can drop to **Claude Pro** for ongoing changes. Check current prices at claude.ai/pricing.
3. Your business email login, and access to your domain settings (whoever set up xquisitpropertygroup.com.au can help with this later; you do not need it on day one).
4. About two hours a week of your time for the first two months, mostly approving things and answering questions. Claude does the building.

### Step-by-step

1. Go to **claude.ai/download** and install the **Claude desktop app**. Sign in.
2. In the app, open **Claude Code** (it is in the left-hand menu).
3. Create a new empty folder on your computer called `xquisit-os` (for example on your Desktop). In Claude Code, choose **Open folder** and select it.
4. Open this file, copy everything between `START OF PROMPT` and `END OF PROMPT` below, paste it into Claude Code, and press Enter.
5. When Claude Code asks permission to run a command or install something, read the one-line reason it gives, and click **Allow**. If anything asks for money, a password or a card number, stop and read it first. Claude will never ask you to type a password or card into the chat; if it does, say no.
6. Claude will start by asking you a few questions about your business, one at a time. Answer in your own words. You can type or use voice.
7. At the end of each session, Claude writes down what it did. To continue next time, open the same folder in Claude Code and type: **"Continue building XQUISIT OS. Read docs/PROGRESS.md first."**

### What to expect, honestly

- Week 1: you see a working, branded dashboard on your computer and phone filled with practice data.
- Weeks 2 to 6: your real properties go in, and the daily work (inbox, arrears, maintenance, approvals) starts running.
- Months 2 to 3: everything else, run side by side with PropertyMe for at least one full month-end.
- **Keep PropertyMe until you are satisfied.** Do not cancel anything until XQUISIT OS has run alongside it through a month-end and your trust accounting position is settled (see "Trust money" in Part B).

---

## PART B: The prompt

========== START OF PROMPT ==========

You are building **XQUISIT OS**: one private web app that runs the property management and sales business of **Tatijana Stevanovic**, director and licensed agent of **XQUISIT Property Group Pty Ltd**, Canberra, ACT. She works alone. It replaces her property management software (PropertyMe, which costs her about $400 a month) and adds a CRM, AI agents that do her marketing and management work, and emails and messages that are drafted for her and sent only once she approves them.

The goal: she opens one dashboard in the morning, sees what needs her judgement, approves or edits what the agents have prepared, and spends her day on the work only a person can do: meeting owners, showing homes, negotiating. Everything else is drafted, chased, scheduled, filed and reported for her.

This project runs over many sessions. On your first turn, save this prompt as `docs/BRIEF.md`. Keep `docs/PROGRESS.md` current (what is built, what is verified, what is waiting on her, what is next), `docs/DECISIONS.md` (every technical choice and why), and `docs/DISCOVERY.md` (what she tells you). Any later session must be able to pick up from these files alone.

---

### 1. Who you are working with

Tatijana is an expert in real estate and not a software person. She is the one at the keyboard.

- **Do the work yourself.** Install what is needed, write the code, configure it, run the tests. Never ask her to choose between technical options. Make the choice, record it in `docs/DECISIONS.md`, and tell her in one plain sentence only if it affects her.
- **Only ask for what needs her hands or judgement:** creating an account, entering a password or payment detail, approving something that goes to a client, or a real business decision. Batch these so she does them in one sitting, with numbered steps that say exactly what to click and what she will see.
- **Plain English.** No jargon, no file paths, no code unless she asks. When you finish something, tell her what she can now do that she could not before, and show her where to click.
- **Secrets never go in the chat.** Have her enter passwords and API keys directly into the provider's settings page or into a `.env` file that you open for her in a text editor. Never print a secret back to the screen. Never commit one.
- **When she is away from the keyboard,** keep working on anything that does not need her, and leave a short list of what does.

### 2. What is known, and what to find out first

Known (from her public listings and profiles; confirm with her):

- Trading name **XQUISIT Property Group** (spelled X-Q-U-I-S-I-T, no E at either end). Legal entity XQUISIT Property Group Pty Ltd. Website xquisitpropertygroup.com.au.
- Director and licensed agent Tatijana Stevanovic (spelled T-A-T-I-J-A-N-A S-T-E-V-A-N-O-V-I-C). Solo operator. Previously traded as "Edge Tatijana Stevanovic" on some portals.
- Phone +61 414 451 480. Email info@xquisitpg.com.au. PO Box 3822, Manuka ACT 2603.
- Instagram `tatijana_xquisit`, Facebook `TatijanaXquisit`. Profiles on Allhomes, Domain and RateMyAgent with strong reviews.
- Residential sales and property management in Canberra.
- Current property management software: PropertyMe, about $400 a month.

**Discovery conversation.** Before designing anything, ask her these, one at a time, and stop when you have what you need. Write answers to `docs/DISCOVERY.md`; they override this brief wherever they differ.

1. How many properties she manages, how many owners, and how many sales listings at a time.
2. What she uses today for: property management and trust accounting (PropertyMe plan), email (Gmail, Outlook or other), calendar, SMS, e-signing, listing uploads, bookkeeping (Xero or other), tenancy applications, and what each costs.
3. Which PropertyMe features she actually uses every week, and which she never touches.
4. The three tasks that eat the most of her week, and the three things that went wrong or nearly did in the last year.
5. Which bank holds her trust account, who her trust account auditor is, and when her last audit was lodged.
6. Whether she is a member of the REIACT and uses its standard forms.
7. Her regular tradespeople, and the approval limits she has agreed with each owner.
8. How she wants the system to reach her: morning email, SMS, phone notification, or only inside the app.
9. What she wants on the screen first thing in the morning.
10. Her own tone: send you five emails she has written to owners and tenants that she is proud of, so the agents can match her voice.

### 3. Rules that hold throughout, and why

**3.1 Trust money stays in licensed, audited trust software until her auditor signs off.**
Rent, bonds and sale deposits held for clients are trust money under the **Agents Act 2003 (ACT)** and the **Agents Regulation 2003 (ACT)**. The trust account is audited every year (the audit is due to Access Canberra by **30 September** each year; confirm the current date and her auditor's process), and a ledger error can cost her licence. So:

- In version 1, XQUISIT OS **does not hold, move or act as the ledger of record for trust money**. Her trust ledger stays in PropertyMe (or another trust accounting product she and her auditor choose). XQUISIT OS imports their reports and bank files, mirrors them read-only, reconciles, flags anomalies and prepares work. It never initiates a payment or a disbursement.
- Moving the trust ledger into XQUISIT OS is a separate, later project. It may only start after her auditor has reviewed the design in writing and agreed it meets the record-keeping, receipting, reconciliation and reporting requirements of the Agents Act and Regulation. Read both (legislation.act.gov.au, Agents Act A2003-20 and Agents Regulation SL2003-38) and list the specific requirements in `docs/TRUST.md` before proposing anything.
- Tell her this plainly in the first session, including what it means for cost (see section 10).

**3.2 Nothing goes to a client until she approves it.**
Every email, SMS, letter, notice, social post, listing, owner statement and payment instruction is created as a draft in the **Approvals** queue. Each automation has a three-position switch: **Off / Draft for approval / Send automatically**. Everything starts at "Draft for approval". She can move routine items (for example a rent receipt or a viewing confirmation) to "Send automatically" after she has watched them get it right for a few weeks.

These never go fully automatic, whatever the switch says: rent increase notices, notices to remedy, notices to vacate or terminate, entry notices for anything other than a routine inspection, bond claims, anything to ACAT, anything involving money leaving an account, and anything to a person who has complained or is in dispute. A wrong legal notice under her name is a real liability; the system has to earn trust before it acts alone.

**3.3 Tenancy and agency law is data, with sources.**
Never rely on memory for a notice period, limit or deadline. Build a `rules` table where each rule has: a key, the value, a plain-English summary, the source URL, the section reference if known, the date checked, and a confidence note. Every automation reads its numbers from this table and shows the source next to any date it calculates. A monthly job re-checks each source and puts any change in front of her. Where a case is unusual or the law is unclear, the system says so and suggests she check with ACAT, Legal Aid ACT, the REIACT or her solicitor.

Seed the table with the rules in section 4, then verify each one yourself against the current legislation before relying on it. Where section 4 says "look up", do so before the feature that depends on it is switched on.

**3.4 Client data is private and stays in Australia.**
She holds identity documents, payslips, bank details and addresses. Host the database and files in an Australian region (Sydney). Enforce access with row-level security from the first migration so an owner sees only their properties and a tenant only their tenancy. Keep an audit log of who viewed or changed what. Treat all personal information as if the Australian Privacy Principles apply. Never put real client data in test fixtures, logs, screenshots or anything sent to a third party beyond what a task needs. Marketing messages need recorded consent and a working unsubscribe (Spam Act 2003). Do not build any tenancy blacklist or database listing; those are regulated under the Residential Tenancies Act.

**3.5 Run in parallel before replacing anything.**
She keeps PropertyMe until XQUISIT OS has run alongside it through at least one full month-end and the numbers match. Never tell her to cancel a subscription. Give her the evidence and let her decide.

**3.6 Tell the truth about the state of things.**
If something is not built, not tested, or not possible (see section 9), say so. A dashboard that looks finished but quietly does nothing is the worst outcome. Every screen that shows demo data says DEMO in the header.

### 4. ACT rules to seed (checked 13 November 2026; re-verify before use)

Primary sources: Residential Tenancies Act 1997 (ACT) A1997-84 and its Schedule 1 standard residential tenancy terms; Residential Tenancies Regulation 1998; Agents Act 2003 (ACT) A2003-20; Agents Regulation 2003 (ACT); Civil Law (Sale of Residential Property) Act 2003 (ACT) A2003-40; all at legislation.act.gov.au. Plain-English guidance at act.gov.au/housing-planning-and-property/renting and acat.act.gov.au.

| Rule | Value | Source |
|---|---|---|
| Rent increase frequency | No more than once every 12 months, counted from the original agreement start across consecutive agreements | act.gov.au/housing-planning-and-property/renting/rent-increases |
| Rent increase notice | At least 8 weeks' written notice | same |
| Rent increase cap ("prescribed amount") | No more than 110% of the growth in the rents component of Canberra CPI, measured from the last increase notice or the tenancy start. Above that only with the tenant's written agreement after being told it exceeds the cap, or an ACAT order. CPI updates quarterly, so recalculate each quarter. Fixed terms that began before 10 Dec 2024 may have their own terms | same; ACT rent increase calculator |
| Routine inspections | First month, final month, and twice in each 12 months from the start | act.gov.au/.../renting/during-a-tenancy |
| Inspection notice | At least 1 week's written notice | same |
| Entry hours | Not Sundays, public holidays, before 8am or after 6pm, unless tenant agrees or urgent | same |
| Non-urgent repairs | 1 week's written notice to enter; complete within 4 weeks | same |
| Urgent repairs | As soon as practicable, reasonable notice to enter. Urgent includes burst water service, blocked or broken toilet, serious roof leak, gas leak, dangerous electrical fault, flooding, serious storm or fire damage, failure of gas, electricity or water supply, failure of a supplied fridge or laundry appliance, failure of hot water, cooking, heating or cooling, anything that makes the home unsafe or insecure | same |
| Smoke alarms | Working alarms at the start of the tenancy, in each storey and every corridor or hallway associated with a bedroom; tenant replaces batteries | same |
| Rent in advance | No more than 2 weeks | same |
| Rent records | Keep at least 12 months after the tenancy ends | same |
| Bond | Maximum 4 weeks' rent; must be lodged with the ACT Revenue Office; not lodging is an offence. **Look up** the lodgement deadline before building the bond workflow | act.gov.au/.../renting/starting-a-tenancy |
| Condition report | 2 copies to tenant within 1 day of move-in; tenant has 2 weeks to return comments | same |
| Pre-signing documents | Tenancy agreement with standard terms; the Renting Book (or where to find it); EER statement if one exists; asbestos assessment report or advice; ceiling insulation compliance statement; pool safety information if applicable; unit title rental certificate for units | same |
| No-cause termination | Not allowed | act.gov.au/.../renting/ending-a-tenancy-for-landlords |
| Termination grounds (periodic) | Sale: 8 weeks + proof. Owner or close family moving in: 8 weeks + statutory declaration. Major renovation: 12 weeks + proof. Change of use: 26 weeks + proof | same |
| Termination grounds (any) | Breach (incl. rent arrears): notice to remedy, then notice to vacate if not remedied, then ACAT if tenant stays. Damage: 2 weeks to repair, then 2 weeks to leave. Successor in title: 8 weeks + ACAT. Unsafe property: at least 1 week. Posting for work (if in agreement): 8 weeks | same |
| Rent arrears timing | **Look up** in the Act and standard terms: the number of days overdue before a notice to remedy can issue, and the remedy and vacate periods. Do not switch on the formal-notice stage of the arrears agent until this is verified and cited | RTA 1997 and Schedule 1 |
| Tenancy only ends | When the tenant leaves or ACAT orders; a notice date alone does not end it | same |
| Ceiling insulation standard | Ceilings with less than R2 must be brought to at least R5. **Existing tenancies must comply by 30 November 2026.** New tenancies within 9 months of signing. Exemptions (heritage, lower-floor apartments, physical constraints, cost over $10,000 with up to $10,000 spent prioritising living areas and bedrooms; temporary ones for owners corporations, tenant objection, demolition within 2 years). Keep evidence (receipt with R-value, installer report, EER report, statutory declaration). Licensed electrician inspection and Certificate of Electrical Safety before install. Certified installer. 1 week's notice to tenant for access. Disclose compliance status in every rental ad and at signing; failing to disclose or misstating it is an offence. Tenants can ask for evidence and go to ACAT | act.gov.au/.../renting/minimum-housing-standard-for-ceiling-insulation-in-rental-properties |
| Energy efficiency rating, rentals | Give the EER statement before signing if one exists; **look up** the current rule on showing an EER in rental advertising | starting-a-tenancy page; RTA |
| Energy efficiency rating, sales | An EER must be disclosed in advertising for sale and an EER statement provided with the contract; **look up** exact section and penalty | Civil Law (Sale of Residential Property) Act 2003; planning.act.gov.au energy efficiency page |
| Sales contract documents | **Look up** the required documents for an ACT residential sale contract (building and pest reports, EER, title and plan documents, and so on) and the cooling-off period and exclusions | Civil Law (Sale of Residential Property) Act 2003 |
| Trust account audit | Annual audit lodged with Access Canberra; industry sources say by 30 September. **Look up** to confirm | Agents Act 2003; Access Canberra |

**First thing to tell her:** the ceiling insulation deadline for existing tenancies is **30 November 2026**. In your first session, before anything else is built, make a one-page checklist of every property she manages with its insulation status (complies, exempt, unknown, not compliant) and the evidence on file, so she can chase the gaps immediately. If you do not have her data yet, give her the checklist as a blank she can fill in from PropertyMe.

### 5. PropertyMe parity: what must exist before she can switch

Build `docs/PARITY.md` from this list, mark each item Built / Verified / Not yet / Stays in other software, and keep it current. She switches only when every row she uses (from discovery question 3) is Verified.

| PropertyMe does | XQUISIT OS equivalent |
|---|---|
| Trust accounting: receipting, disbursements, owner payments, supplier payments, bank reconciliation, end-of-month, audit reports | Version 1: read-only mirror and reconciliation checks; ledger stays in licensed software (rule 3.1) |
| Rent roll, tenant ledgers, arrears report | Rent roll mirrored from trust software; arrears detected daily; arrears agent |
| Owner statements and EOFY summaries | Plain-English statement and tax-time summary alongside the official one |
| Bills processing (Bills AI) | Bookkeeper agent reads supplier invoices, matches to job and property, prepares for payment in trust software |
| Unified inbox (email, SMS, chat) | Inbox with per-person, per-property threads, drafted replies |
| AI reply assistant | Inbox agent, in her voice |
| Tasks and jobs (maintenance) | Maintenance module and agent, with tradie portal links |
| Inspections and inspection app | Inspections module, phone-first checklist with photos and dictation, branded reports |
| Owner and tenant app with web portal | Owner portal and tenant portal (installable on phones) |
| Property manager mobile app | The whole app is phone-first and installable |
| Key register, documents, templates | Keys register; documents on every record; ACT-specific templates |
| Compliance tracking (smoke alarms, etc.) | Compliance module and agent, including insulation and EER |
| Lease renewals and rent reviews | Renewals agent with the CPI cap from the rules table |
| Leasing: applications, bookings, references (Grow CRM) | Leasing module: listings, enquiries, viewing bookings, branded application form, reference checks |
| Online rent payments (MePay) | Not in version 1 (trust money rule); tenants keep paying the trust account directly |
| Listing portal uploads | See section 9: prepared in XQUISIT OS, published through an approved uploader |
| Reports | Business health page and exportable reports |
| API and integrations | Her own system; she owns all the data and can export any of it as CSV at any time |

Also build what PropertyMe does not do for her: a sales CRM, a marketing studio, a growth pipeline, and the agents in section 7.

### 6. What the dashboard contains

All sections share one set of contacts, properties and history.

**Today (home screen).** Money received and overdue, items waiting for approval with a count on the menu, today's appointments, deadlines in the next 14 days, and a morning brief: what happened overnight, what the agents did, and the three things that most need her today. One search box finds any person, property or document. One "Ask" box takes typed or spoken requests ("who is behind on rent?", "draft a renewal for 12 Smith St at $680 a week") and does them, putting anything outbound into Approvals.

**Approvals.** One queue for everything waiting on her. Each item shows the draft, who it goes to, why the agent prepared it, the rule and source it relied on, and buttons: Approve and send, Edit, Reject (with a reason the agent learns from), Snooze. Swipeable on the phone. Bulk approve for routine items.

**CRM / Contacts.** Every owner, tenant, applicant, buyer, vendor, tradesperson and referral partner, with tags, consent status, relationship history and next action. Buyer and landlord lead capture from her website, portals and open homes.

**Portfolio.** Every property, owner, tenant and tenancy, with one timeline per property (every message, job, inspection, payment and document). Keys register. Management agreements with fee terms and owner approval limits.

**Rent and arrears.** Rent roll mirrored from trust software. Arrears detected daily. Each case shows days overdue, amount, history, payment plan, and the next step with the earliest lawful date from the rules table.

**Maintenance.** Tenants report through the portal, email or SMS with photos. Urgency triaged against the urgent repairs list. Owner limit checked. Quotes requested from her preferred trades. Access scheduled with the tenant inside the entry rules. Followed up until done. Invoice and photos collected. Tenant and owner told.

**Inspections.** Scheduled within the legal limits, entry notices with the right notice, a route for the day. On the phone: room-by-room checklist, photos, dictated notes, offline-capable. Turned into a branded owner report, a maintenance list and a tenant follow-up. Exit compared with entry for bond claims.

**Compliance.** Smoke alarms, ceiling insulation and evidence, EER statements, asbestos advice, pool safety, gas and electrical checks, landlord insurance expiry, her licence, professional indemnity insurance, CPD and the trust audit date. Colour-coded, with jobs raised before anything lapses.

**Leasing.** Vacancy pipeline from notice to vacate to keys handed over. Listing copy (with insulation and EER disclosures inserted automatically) and a rent recommendation. Enquiries answered and viewings booked. Branded application form; applications summarised against her criteria with the reasoning shown, and she decides (screening must stay fair and lawful). Lease documents, pre-signing document pack, bond lodgement steps. Move-in checklist and condition report.

**Renewals and rent reviews.** Every lease end and rent review date. At least 12 weeks ahead: a recommendation to the owner with comparable evidence, the CPI cap and the earliest notice date, and the draft letters.

**Sales.** Prospects, appraisals, listings, buyers, offers and contracts through to settlement. Branded appraisal packs and listing proposals. Open-home attendee capture on the phone with same-day follow-up. Buyer matching to new listings. Weekly vendor reports written from enquiry and inspection data. Settlement milestones. Past clients kept warm.

**Inbox.** Her email and SMS in one place, each message linked to the right person and property, sorted by what needs action, with a reply drafted in her voice.

**Money.** Read-only mirror of the trust ledger. Supplier bills matched to jobs. Month-end checklist that walks her through reconciliation and flags anything that does not tie out. Her business bookkeeping feed (Xero or whatever she uses). Owner tax-time summaries.

**Owner portal and tenant portal.** Owners: statements, property timeline, inspection reports, approve quotes and renewals, documents. Tenants: rent position, report and track a repair, inspection times, documents, messages. Branded, simple, phone-first, light theme.

**Marketing studio.** Content calendar; posts and reel scripts from every new listing, lease, sale and review; monthly email to her database; suburb market updates; just-listed and just-sold campaigns; review requests feeding RateMyAgent and Google. Tracks what produces enquiries. Posts only after approval.

**Growth.** New-business pipeline for managements and listings: landlord leads, referral partners, stale listings, owners in her portfolio likely to sell, a rent-roll growth target with progress.

**Business health.** Properties under management, fee income, vacancy rate and days vacant, arrears percentage, maintenance turnaround, renewals retained, sales pipeline value, hours saved by the agents, and running cost of the system this month.

**Automations.** Every automation with its switch, schedule, recent activity and error count. A log of every agent action with inputs, output, cost and the rule it used. She can always answer "why did it do that?"

**Settings.** Her details, branding, templates with merge fields, approval limits, notification preferences, connected accounts, and a one-click full data export.

### 7. The AI agents

Build each as a separate worker with a narrow job, using the Claude API (check the current model list and prices at docs.anthropic.com before choosing; use the most capable model for legal and money reasoning, a mid-tier model for everyday drafting, and the smallest model for high-volume sorting). Every agent writes to the Approvals queue and the property timeline, never sends directly unless its switch allows it, logs inputs, output and cost, and cites the rule it relied on. Start each one narrow; widen only when she switches it up.

| Agent | Runs when | Does on its own | Needs her approval | Model tier | How its work is checked |
|---|---|---|---|---|---|
| Chief of staff | 6:30am daily; Sunday 5pm weekly; whenever she uses Ask | Writes the morning brief and weekly review, answers questions, hands tasks to other agents | Anything outbound | Top | Brief must link every claim to a record; numbers come from the database, not the model |
| Inbox | Every new email or SMS | Sorts, links to person and property, tags urgency, drafts a reply | Every reply until switched | Small to sort, mid to draft | She rates drafts; edits are saved as voice examples |
| Arrears | Daily 7am after the rent roll syncs | Detects arrears, updates cases, schedules reminders | Reminder SMS/email (can be switched to auto); every formal notice (never auto) | Mid for reminders, top for notices | Day counts calculated in code from the rules table and unit tested, never by the model |
| Maintenance coordinator | New request; daily follow-up at 9am | Triages, asks tenant for photos, requests quotes, chases trades, books access within entry rules | Work orders above owner limit; any urgent repair spend; any owner message | Mid | Urgency checked against the urgent repairs list; notice dates computed in code |
| Inspections | Weekly planning Monday 7am; after each inspection | Proposes schedule within limits, drafts entry notices, turns notes and photos into a report | Entry notices; reports before they go to owners | Mid (vision for photos) | Inspection count and notice checked in code against rules |
| Compliance | Daily 6am | Tracks every expiry, raises jobs 60, 30 and 7 days ahead, chases evidence | Messages to owners about cost; any exemption claim | Mid | Each item links to its evidence file; nothing marked compliant without one |
| Leasing | New vacancy, enquiry or application | Drafts listing with mandatory disclosures, answers enquiries, offers viewing times, summarises applications | Listing before publishing; choice of tenant (always hers); lease documents | Mid | Disclosure checklist must pass before the listing can be approved |
| Renewals | 16 weeks before each lease end or review date | Pulls comparables, calculates the CPI cap and earliest notice date, drafts owner recommendation and tenant letters | Everything | Top | Cap and date calculated in code; source and CPI quarter shown on the draft |
| Sales assistant | New lead, open home, offer, weekly Friday 4pm | Logs leads, follows up open-home attendees, matches buyers, writes vendor reports, tracks settlement dates | Every client message until switched | Mid | Vendor report numbers pulled from the database |
| Bookkeeper | New bill; daily bank file import; month-end | Reads invoices, matches to jobs, prepares payment batch for trust software, reconciles the mirror | Every payment instruction (never auto) | Mid | Totals must tie to source to the cent or the item is flagged |
| Owner reporting | Monthly after statements; EOFY | Writes plain-English summary for each owner | Each summary until switched | Mid | Figures copied from the official statement, not generated |
| Marketing | Weekly Monday 8am plan; on every new listing, lease, sale or review | Drafts the week's posts, emails and reel scripts in her brand voice | Every post and campaign | Mid | Checks consent and unsubscribe before any send; no client data in public posts without consent |
| Growth | Weekly Wednesday | Scores leads, suggests 5 people to call this week with a reason, drafts outreach | All outreach | Mid | Shows the data behind each suggestion |

General rules for all agents: a model never calculates a date, an amount or a legal limit; code does that from the rules table and the model only writes the words around it. If an agent is unsure, it says so in the draft and flags it. Every agent has a daily spending cap; if it is reached, the agent stops and tells her.

### 8. Automations and email that she approves

- **Sending email** from her own domain through a transactional email service (Resend or Postmark, Sydney-friendly, with SPF, DKIM and DMARC set up on her domain). Replies come back into her normal mailbox and are pulled into the Inbox.
- **Reading email** from her mailbox through the Gmail API or Microsoft Graph, depending on what she uses. Read-only plus "save draft" unless she approves sending from the mailbox itself.
- **SMS** through an Australian SMS provider with an approved alphanumeric sender ID (for example "XQUISIT"). Two-way, so tenant replies land in the Inbox. Sender ID registration takes days; start it in week one.
- **Approvals flow:** every message is created as a draft with status Waiting, appears in Approvals and in her morning brief, and is only sent when she approves it (or its switch is on Automatic and it is not in the never-automatic list). A sent message is stored against the person and property with the exact text and time.
- **Templates** for every common ACT communication, with merge fields: rent receipt, arrears reminder 1 and 2, routine inspection entry notice, repair entry notice, inspection report cover, maintenance update, rent increase notice, renewal offer, owner renewal recommendation, insulation compliance request to owner, compliance reminder, viewing confirmation, application outcome, welcome pack, vacate checklist, bond refund steps, vendor weekly report, appraisal follow-up, review request, market update.
- **Schedule** (all times Canberra time, adjusting for daylight saving): 6:00 compliance scan, 6:30 morning brief, 7:00 rent roll sync and arrears, 9:00 maintenance follow-ups, Monday 7:00 inspections plan, Monday 8:00 marketing plan, Wednesday growth list, Friday 16:00 vendor reports, Sunday 17:00 weekly review, 1st of each month rules re-check and backup restore test.
- **Failure handling:** if a job fails twice, she gets one plain-English alert and the item goes to a "Needs attention" list. Nothing fails silently.

### 9. Constraints to check and be honest about

Check each yourself, because access programmes change, and tell her where it stands:

- **Trust accounting** stays in licensed software in version 1 (rule 3.1). The trust audit itself must be done by a qualified auditor; the system can only prepare the reports.
- **Listing portals.** realestate.com.au, Domain and Allhomes take listings through approved software feeds. A custom system may not get access. Fallback: prepare the complete listing in XQUISIT OS and publish through an approved uploader or the portals' agent tools.
- **PropertyMe data.** API access is on their Advanced plan or for partners. Plan the migration from their report exports (properties, contacts, tenancies, ledgers, documents) and check whether her plan includes API access.
- **Online rent payments.** Out of scope while trust money stays in licensed software.
- **Comparable sales data.** CoreLogic and PropTrack are paid licences. Use what she already pays for; otherwise use public sales results and her own history, and say which was used.
- **Standard forms.** REIACT forms are for members. The ACT standard residential tenancy terms are in the Act and free to use. Do not reproduce licensed forms she is not entitled to.
- **E-signing.** Use an e-signature service that meets the Electronic Transactions Act 1999 (ACT) requirements; check what she already has.
- **Meta posting.** Needs her Facebook business account connected and app approval. Until then, the marketing studio produces ready-to-post content she can publish in two taps.
- **Legal judgement.** The system prepares; she decides. Anything going to ACAT, any dispute, and anything unusual is flagged for her or her solicitor.
- **Things that stay with a person:** the trust audit (auditor), signing as licensee (her), choosing a tenant (her), legal advice (solicitor or Legal Aid ACT), and any physical inspection (her).

### 10. Running costs: be honest

Before she signs up for anything, show her a one-page table of every account, what it is for, and its current monthly price (check each live; prices below are estimates as of November 2026 and must be re-checked). Get her yes.

| Item | What for | Estimated monthly cost |
|---|---|---|
| Hosting (Vercel Pro or similar; the free tier does not allow commercial use) | Runs the app | about A$30 |
| Database, login and file storage (Supabase Pro, Sydney region) | Her data, daily backups | about A$40 |
| Transactional email (Resend or Postmark) | Sending approved emails | A$0 to A$30 |
| SMS (Australian provider) | Reminders, tenant messages | about 5 to 10 cents per SMS; typically A$20 to A$60 |
| Claude API | The agents | estimate A$40 to A$150, depending on volume; show actual spend on the Business health page and set a hard monthly cap |
| Domain | Already owned | A$0 extra |
| Claude subscription for Claude Code | Building now, changes later | Max during the build, Pro after (check current prices) |
| **Total, excluding trust accounting** | | **about A$130 to A$310 a month** |

**The honest part about savings.** XQUISIT OS replaces everything PropertyMe does except the trust ledger in version 1. She still needs licensed trust accounting software. PropertyMe's own start-up package (Basic, up to 100 properties) was listed at about $193 a month including GST in its published pricing; find what trust-only options exist and their prices, and tell her the real comparison. Version 1 total may land close to what she pays now, but she gets a CRM, AI agents, her own brand and her own data. The big saving comes in a later phase if her auditor approves moving the trust ledger into XQUISIT OS. Say this to her plainly; do not promise savings that depend on that approval.

### 11. How it should be built

Recommended stack (change it only with a reason recorded in `docs/DECISIONS.md`):

- One web app: TypeScript, Next.js, Postgres. Supabase (Sydney region) for database, authentication and file storage. Deployed to a managed host. Installable on her computer and phone as an app (PWA) so it is one tap, with offline support for inspections.
- Three kinds of sign-in: Tatijana (everything), owners (their portal), tenants (their portal). Optional later: tradesperson links that need no account. Two-factor login for her account.
- Row-level security from the first migration. An automated test proves an owner cannot read another owner's data and a tenant cannot read another tenancy.
- Background jobs on schedules and events so the system works while her laptop is closed.
- Agents built with the Claude API and Agent SDK, each with a tool list limited to what it needs.
- Realistic invented demo data from day one, labelled DEMO, with one button to wipe it before real data goes in.
- Tests for anything involving dates, money or legal rules, with edge cases: ACT public holidays (including Canberra Day and Reconciliation Day), weekends, Sundays for entry, leap years, daylight saving, rent changes mid-period, consecutive agreements for the 12-month rent increase rule.
- Daily automatic backups, a monthly tested restore, and a one-click export of all her data.
- Error monitoring that alerts her (and whoever supports her) in plain English.

### 12. Brand and look

Her brand is **matte black and gold**, and the app should feel like a private members' club, not accounting software.

**Logo.** A bold geometric **X** built from layered gold chevrons, followed by "QUISIT PROPERTY GROUP" in a clean uppercase geometric sans. Ask her for the original logo files (SVG or high-resolution PNG). Until then, take the image from xquisitpropertygroup.com.au and trace a clean SVG of the X mark. Use the X alone, large, as the sign-in screen centrepiece, the app icon, the loading mark and the favicon. Use the full lockup in the header and on every document.

**Palette** (taken from her site; extend carefully):

- Blacks: `#070707` page, `#0F0F0F` and `#151515` surfaces, a soft warm-charcoal gradient on raised cards.
- Gold: `#AF9B60` primary accent; `#C4BC96` pale gold for secondary accents and hover.
- Text: `#FFFFFF` and warm off-white `#F6F3EC`; `#BEB9AD` for secondary text.

**Rules.** Matte means no gloss, no neon, no heavy shadows. Gold is used sparingly: a hairline at the top of a card, an icon, a key number, the primary button outline. If everything is gold, nothing is. Status colours (overdue, due soon, done) must pass WCAG AA contrast on black without fighting the gold. Headings in a geometric sans matching the wordmark, small uppercase labels with generous letter-spacing, body text in a highly readable sans. Rounded cards with a fine border, pill-shaped outlined buttons, plenty of space.

**Phone first.** Inspections and open homes happen on the phone, so every screen must work one-handed at phone width. Light theme for owner and tenant portals and for printing. Owner-facing documents (appraisals, vendor reports, inspection reports, statements) carry the brand and look good enough to win business.

Before you show her any screen, open it yourself in a browser at phone and desktop widths, take screenshots, and fix anything that looks off.

### 13. Order of work

Each stage ends with something she can use and a short demonstration. Do not start a stage until the previous one is verified.

1. **Setup and first look (week 1).** Discovery conversation. Insulation checklist (section 4). Cost table and her yes. Accounts created with her (numbered steps). Install, deploy. Branded shell with sign-in, Today, Approvals and Portfolio on demo data. She reacts; you adjust.
2. **Her real data.** Import properties, owners, tenants, tenancies, rent roll, compliance dates and documents from PropertyMe exports. Reconcile counts and totals against the source and show her the comparison side by side.
3. **Daily operations.** Inbox, Approvals, email and SMS sending, arrears (reminders only until the formal-notice rule is verified), maintenance, morning brief. From here it saves her time every day.
4. **Calendar work.** Inspections, compliance, renewals and rent reviews, with the rules table verified and cited.
5. **Leasing and sales.** Vacancy pipeline, applications, sales CRM, vendor reports, open-home capture.
6. **Portals.** Owner and tenant portals, invited a few friendly clients at a time.
7. **Marketing and growth.** Marketing studio, review requests, new-business pipeline.
8. **Money and month-end.** Ledger mirror, bills, month-end checklist, business health. Run one full month-end in parallel with PropertyMe and show her the numbers match.
9. **Handover.** A plain-English guide written for her (`docs/GUIDE.md`, also as a page inside the app), backups with a tested restore, monitoring, and a walk-through of every section. A one-page list of what still lives in other software and why.

At the end of every session, update `docs/PROGRESS.md` and tell her in a few sentences: what now works, what you need from her, and what comes next.

### 14. What done looks like

She opens one app, on her computer or phone, in her brand. Her whole portfolio and pipeline are in it and match her system of record. Every recurring task in her week is either done by an agent or waiting in one Approvals queue with the work already prepared. No deadline is missed, because every date is tracked, calculated from cited rules, and raised early. She can see and switch off anything the system does. Her data is private, backed up, in Australia, and hers to export at any time. She knows exactly what it costs each month. And she has stopped doing the administration that was the reason for building this.

========== END OF PROMPT ==========

---

### Sources checked for this version (13 November 2026)

- ACT Government, rent increases: https://act.gov.au/housing-planning-and-property/renting/rent-increases
- ACT Government, during a tenancy: https://www.act.gov.au/housing-planning-and-property/renting/during-a-tenancy
- ACT Government, starting a tenancy: https://www.act.gov.au/housing-planning-and-property/renting/starting-a-tenancy
- ACT Government, ending a tenancy for landlords: https://www.act.gov.au/housing-planning-and-property/renting/ending-a-tenancy-for-landlords
- ACT Government, minimum ceiling insulation standard: https://www.act.gov.au/housing-planning-and-property/renting/minimum-housing-standard-for-ceiling-insulation-in-rental-properties
- ACT legislation register (Residential Tenancies Act 1997, Agents Act 2003, Agents Regulation 2003, Civil Law (Sale of Residential Property) Act 2003): https://www.legislation.act.gov.au
- Access Canberra, agent licensing: https://www.accesscanberra.act.gov.au/business-and-work/real-estate-and-property/licensing-for-business-real-estate-and-stock-and-station-agents
- ACT planning, energy efficiency ratings: https://www.planning.act.gov.au/professionals/regulation-and-responsibilities/responsibilities/energy-efficiency
- PropertyMe pricing and plan features: https://www.propertyme.com.au/pricing-2025
- Business name and agent spelling: https://www.allhomes.com.au/agency/xquisit-property-group-984405/ and https://www.ratemyagent.com.au/real-estate-agency/xquisit-property-group-pty-ltd-be843/sales
