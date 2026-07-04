# AI Lead Qualification & CRM Follow-Up System (n8n)

An automated lead qualification and follow-up workflow built with **n8n**, **Google Sheets**, and **Gmail**. Captures form leads, logs them to a CRM sheet in real time, filters by budget to flag high-value prospects, alerts the sales team, and sends personalized, service-specific auto-replies — all without manual intervention.

Built by [Sohag Gain](https://bd.linkedin.com/in/sohaggain) — Founder, [AI Smart Galaxy](https://aismartgalaxy.com).

---

## Problem

Service businesses lose deals when leads sit unanswered for hours, and sales teams waste time manually qualifying and replying to every inquiry — regardless of budget fit.

## What This Workflow Does

1. **Capture** — A custom intake form collects Full Name, Email, Service Type (SEO/Ads), and Budget.
2. **Log** — Every submission is appended to a Google Sheet instantly, functioning as a lightweight CRM.
3. **Qualify** — A Filter node checks budget against a $1,000 threshold to separate high-value leads from low-fit inquiries.
4. **Alert** — Qualified leads trigger an instant internal email notification to the sales owner.
5. **Route & Personalize** — An If node branches by service type (SEO vs. Ads), triggering a tailored auto-reply email with a direct booking link for each.
6. **Update CRM** — After the auto-reply sends, the sheet is automatically updated with `Contacted: TRUE` and a `Rejected` flag based on budget — no manual status tracking required.

## Result

Every lead is captured, scored, routed, and responded to within seconds. The system scales from 10 leads/month to 1,000+ without adding headcount or hiring a VA.

## Tech Stack

| Component | Tool |
|---|---|
| Automation Engine | n8n |
| Lead Storage / CRM | Google Sheets API |
| Email Notifications & Replies | Gmail API |
| Trigger | n8n Form Trigger |

## Workflow Architecture

```
Form Submission → Append to Sheet → Filter (Budget ≥ $1,000)
       → Internal Alert Email → If (Service Type)
              ├── Ads → Personalized Ads Reply ─┐
              └── SEO → Personalized SEO Reply ─┴→ Merge → Update CRM Status
```

## Use Cases

This pattern generalizes to any business that needs automated lead capture + qualification + follow-up:
- Marketing/ad agencies
- Coaches & consultants
- Real estate lead intake
- E-commerce inquiry handling

## Setup Notes

- Requires an n8n instance (self-hosted or cloud), a connected Google account (Sheets + Gmail OAuth2), and a Google Sheet with columns: `Full Name`, `Email`, `Service`, `Budget`, `Date`, `Contacted`, `Rejected`.
- Budget threshold and service branching logic are configurable in the Filter and If nodes.

## About Me

I build AI automation systems — lead-gen, CRM automation, AI agents, and workflow automation — using n8n, Make.com, Zapier, GoHighLevel, and Claude/OpenAI APIs.

- Website: [aismartgalaxy.com](https://aismartgalaxy.com)
- LinkedIn: [bd.linkedin.com/in/sohaggain](https://bd.linkedin.com/in/sohaggain)
- Upwork: Available for AI automation & workflow automation projects

---

*This repository showcases workflow architecture and logic. Credentials, API keys, and live sheet/email endpoints have been removed or replaced with placeholders.*
