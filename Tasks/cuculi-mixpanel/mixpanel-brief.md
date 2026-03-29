<brief>

Project Brief — Mixpanel Implementation for Yuka (from "Dashboard Development Planning" meeting)

1) Project Overview
- Implement Mixpanel to centralize event-driven analytics for Yuka, focusing on notification observability and the end-to-end customer journey to drive engagement and user growth.

2) Strategic Objectives
- Increase active users and engagement.
- Improve notification effectiveness (delivery, open, click, conversion).
- Provide actionable dashboards and drill-downs to enable rapid product/marketing decisions.
- Enable segmentation/cohorts and automation (alerts/reports/Cloud Code/LLM workflows).

3) Scope
In scope:
- Instrumentation of core events across Notification Service, web and mobile apps.
- User profile (people) properties.
- Mixpanel project setup, access, dashboards, funnels, cohorts, alerts, reporting.
- Verification of Mixpanel <> MongoDB / Stripe connectors; Cloud Code integrations.
- Staging QA, governance, and documentation (events catalog).
Out of scope:
- Building external BI systems beyond defined exports/pipelines.

4) Stakeholders & Roles
- Chris Cruz — Product / project lead; meet with Yuka to define metrics and targets.
- Jose Velasquez — Engineering lead for web & Mixpanel access; verify Mixpanel <> MongoDB; grant access.
- Cristian Guerrero — Implement Mixpanel instrumentation in Notification Service.
- Paul — Instrument backend/mobile events.
- Adrian — Architecture / implementation advisor (Mixpanel UI vs code).
- Yuka — Business owner; define strategic objectives and top metrics.
- Ops/Speaker 2 — Connector validation and access provisioning.

5) Deliverables
- Events catalog (CSV/Sheet): event_name, properties, types, required/optional, owner, created_date, notes.
- Instrumentation plan & SDK usage guide.
- Staging Mixpanel project with test events.
- Dashboard spec (one-page) and mock(s).
- Live Mixpanel dashboards: KPI, Notification Performance, Funnels, Cohorts, Acquisition.
- Alerts & scheduled reports; Cloud Code query examples.
- QA checklist, runbook, governance & changelog.

6) Timeline (recommended)
- Week 0: 1-hr meeting with Yuka to define objectives, top 3–5 metrics, targets.
- Week 1: Draft events catalog; set up staging Mixpanel; grant access to Chris.
- Week 2: Cristian instruments Notification Service; Paul instruments core backend events.
- Week 3: Instrument web/mobile; Jose verifies MongoDB connector.
- Week 4: Build dashboards & funnels in staging; run QA; gather feedback.
- Week 5: Deploy production dashboards; enable alerts and reports.
- Ongoing: Monthly audits, event/property cleanup, roadmap for advanced features.

7) Core Event Model (minimum)
- notification_sent: event_id, distinct_id, channel (push/email/sms), template_id, campaign_id, timestamp, provider, platform, source
- notification_delivered: event_id, distinct_id, channel, provider_response, timestamp
- notification_opened: event_id, distinct_id, channel, timestamp, device_type
- notification_clicked: event_id, distinct_id, channel, destination, timestamp
- notification_failed: event_id, distinct_id, channel, error_code, timestamp
- booking_created / payment_completed: event_id, distinct_id, amount, currency, plan, timestamp
- Additional: page_view, signup, profile_update

8) User Profile Properties
- distinct_id, email_hash (if needed), signup_date, plan, country, last_notification_at, last_active_at, lifetime_value, acquisition_source, is_potential_host (derived)

9) Identification & Mapping Rules
- distinct_id = authenticated user_id when available; fallback to device_id for anonymous.
- Prefer server-side timestamps for backend events.

10) Integrations & Data Flow
- SDKs: JS (web), iOS, Android, server SDKs or HTTP API.
- Connectors: MongoDB, Stripe, OneSignal, Cloud Code — evaluate direct sync vs ETL.
- Data pipelines: JQL / exports for warehouse sync if required.
- Cloud Code: for ad-hoc queries, automation, or LLM integrations.

11) Dashboards & Priority Metrics
- KPI tiles: DAU/MAU, new users (7d), conversion rate (sent→booking), revenue/day.
- Funnel: sent → opened → clicked → booking → payment (7d window).
- Notification Performance: sends, delivery rate, open rate, click rate, failure rate by channel/campaign.
- Cohorts: top restaurants, top users, potential hosts, churn-risk.
- Alerts: conversion drops, failure spikes, ingestion outages.

12) QA & Testing
- Use staging Mixpanel project and test cohorts.
- Verify events in Live View; validate property types and volumes.
- Synthetic tests: simulate key journeys and assert sequence.
- Validate idempotency/deduplication and user mapping.

13) Privacy & Compliance
- Avoid raw PII; hash/omit sensitive fields.
- Use server-side tokens for sensitive events; secure API keys.
- Support GDPR/CCPA deletion/export; enforce role-based access.

14) Governance & Maintenance
- Maintain events catalog & changelog; assign owners.
- Quarterly audits to remove unused events and optimize properties.
- Versioning policy for breaking changes (e.g., event_v2) and deprecation timelines.

15) Risks & Mitigations
- High event volume/cost: monitor volumes, apply sampling when needed.
- User mapping issues: enforce login identification and reconciliation scripts.
- Schema drift: enforce schema validation and staging checks.
- Missing connectors: confirm connector capabilities early; fallback to ETL.

16) Success Criteria
- Notification events visible in Mixpanel staging.
- Customer journey funnel populated with reliable conversion metrics.
- Yuka-approved top metrics and targets defined.
- Chris and stakeholders have Mixpanel access and can run Live View checks.

17) Immediate Next Actions (owners & targets)
- Chris: schedule 1-hr meeting with Yuka to define objectives and top metrics (target: within 3 days).
- Cristian: finish Mixpanel instrumentation in Notification Service for staging (target: Week 2).
- Jose: set up staging Mixpanel project, verify MongoDB connector, grant Chris access (target: Week 1).
- Paul: instrument core backend/web events per events catalog draft (target: Week 2).
- Team: draft events catalog and share for review (target: 3 business days).

18) Offerings I will produce on request
- Prefilled events catalog (CSV/Sheet) for notifications & customer journey.
- One-page dashboard spec (mock + widget definitions + targets).
- QA checklist and staging test plan.

Confirm which deliverable to start with (events catalog, dashboard spec, or QA checklist) and confirm available windows for the Yuka meeting.</brief>

<features>

Quoted Mixpanel features and their meeting use cases

- "integrate all our provider, Stripe, magic, one signal" — use case: centralize events from payment, auth, and notification providers for unified analytics and attribution.
- "Mixpanel API" — use case: server-side instrumentation from Notification Service to send events (event_id, user_id, channel) for centralized tracking.
- "smart events" — use case: capture meaningful event properties for segmentation and funnel analysis.
- "connector with Cloud Code" — use case: run ad-hoc queries, automate responses, or enable programmatic access (e.g., LLM/cloud workflows) against Mixpanel data.
- "notify if, you know, certain triggers, certain things happen" — use case: alerting/automation when thresholds or conditions occur (e.g., spike in failures, drop in conversion).
- "generate, like, I know it's a dashboarding tool, but I wonder if, like, if it can generate reports" — use case: scheduled or historical reports for stakeholders and trend analysis beyond live dashboards.
- "connected to MongoDB" / "direct connection" — use case: sync raw data or source-of-truth user/event data between MongoDB and Mixpanel for consistency and richer joins.
- "could you ask it questions through cloud code" / "looks like the answer is yes" — use case: ad-hoc querying or natural-language/LLM-driven queries to get quick metrics or insights from Mixpanel.</features>

<next>

Next steps
- Chris: Schedule 1‑hr meeting with Yuka to define strategic objectives, top 3–5 metrics, targets, and drill paths.
- Jose: Set up staging Mixpanel project, verify Mixpanel <> MongoDB connector, and grant Chris access.
- Cristian: Finish Mixpanel instrumentation in Notification Service (notification_sent/delivered/opened/clicked/failed) for staging.
- Paul: Instrument web/mobile events (opens, clicks, conversions) per events catalog draft.
- Team: Draft and share events catalog (CSV/Sheet) listing event_name, properties, types, required/optional, owner.
- Adrian: Advise on build approach (Mixpanel UI vs code) and assist dashboard design.
- Build: Create dashboard mock (one‑page) for customer journey and notification performance; define widgets, targets, and drill paths.
- QA: Run staging tests (Live View, synthetic journeys, dedup/idempotency checks) and validate user mapping (distinct_id).
- Governance: Assign owners for events/properties, set changelog and audit cadence.
- Ops/Speaker 2: Confirm access provisioning and connector/ETL plan for Stripe/MongoDB/OneSignal.
- Deliverables to produce next (pick one): prefilled events catalog, one‑page dashboard spec, or QA checklist.</next>