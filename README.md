# CostManager

**Make every meeting count.** CostManager is a meeting-cost dashboard and lightweight company workspace prototype.

## Included in this prototype

- Live, running meeting-cost meter based on attendees' configured monthly pay and work hours
- Create, start, schedule and end demo meeting sessions
- People directory with search, branch/type filters, individual compensation edits and group pay bands
- CSV/JSON employee-directory import and CSV export
- Team chat groups and local demo messages
- Event creation with audience targeting
- Company statistics and Chart.js visualisations
- Investor register and illustrative financial overview
- Workspace roles, planned Google/Microsoft/Apple sign-in options, and onboarding/business settings
- Responsive dark UI, custom CostManager mark, modals and toast feedback
- Browser-local persistence using localStorage

## Run it

Open [index.html](./index.html) in a browser, or enable GitHub Pages in **Settings → Pages** and deploy from the `main` branch, root folder.

## Important prototype limitations

This repository currently contains a **front-end prototype**, not a production multi-user SaaS.

- Data is stored in the current browser only. It is not shared between team members or devices.
- Meeting sessions calculate a local estimate; they do not ring people or provide real voice/video calls.
- Chat messages are local demo messages, not real-time group chat.
- Google, Microsoft and Apple options are interface placeholders. OAuth, secure sessions, invitations and server-enforced roles are not configured.
- Salary visibility in the UI is a convenience, **not a security boundary**. Do not store real compensation data until permissions are enforced by a backend.
- CSV and JSON imports are parsed in the browser. Other document types and very large files require a server-side extraction/import pipeline with upload limits, validation and access controls.
- Turnover, expenditure, returns, focus score and some charts use illustrative sample values. They are not live accounting or investment data.
- Google Fonts and Chart.js are loaded from CDNs, so those visual enhancements require internet access.

## Suggested production architecture

- Frontend: React/Next.js + TypeScript
- Authentication: Google, Microsoft and Apple OAuth
- Database: PostgreSQL with tenant/company isolation
- Realtime: WebSockets or a managed realtime service for meeting state and chat
- Calling: WebRTC or a dedicated calling provider with notification delivery
- File imports: queued, size-limited upload pipeline with CSV/XLSX/PDF/DOCX parsers, validation and import previews
- Security: server-side role and branch permissions, audit logs, encryption, and least-privilege access
- Finance: configurable regional salary periods, currencies, overtime and bonus rules

Never commit real employee personal information, credentials, access tokens or salary data to this public repository.
