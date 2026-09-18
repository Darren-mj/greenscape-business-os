# AI Workflow Design Document

# Greenscape Business Operating System (GBOS)

Version: 1.0

Status: Approved

---

# 1. Purpose

This document defines all AI-powered capabilities, automations, workflows, integrations, and future AI enhancements for Greenscape Business Operating System.

The objective is to reduce manual work, improve quotation quality, increase lead conversion, and provide business insights.

---

# 2. AI Architecture

React Frontend
        ↓
FastAPI Backend
        ↓
PostgreSQL (Neon)

AI Requests
        ↓
n8n VPS
        ↓
OpenAI

Notifications
        ↓
Telegram

Documents
        ↓
Cloudinary

---

# 3. AI Modules

Phase 1

1. AI Quotation Generator
2. AI Quotation Regenerator
3. AI Daily Business Summary
4. AI Project Summary

---

Phase 2

5. AI Lead Follow-up Assistant
6. AI Business Insights Engine
7. AI WhatsApp Assistant
8. AI Revenue Forecasting

---

# 4. AI Quotation Generator

Purpose:

Generate professional quotations automatically.

---

## Inputs

Client Name

Project Name

Site Location

Service

Products

Measurements

Quantity

Unit

Rate

Transportation Charges

Food Charges

Accommodation Charges

Other Charges

---

## AI Tasks

Generate:

- Professional Introduction
- Scope of Work
- Product Description
- Installation Description
- Terms & Conditions
- Delivery Terms
- Payment Terms
- Validity Terms

---

## Output

Professional quotation content

Ready for PDF generation

---

## Trigger

Manual Button

"Generate with AI"

---

# 5. AI Quotation Regenerator

Purpose:

Generate revised quotations based on client negotiations.

---

## Inputs

Existing Quotation

Client Feedback

Target Amount

---

## Example

Client says:

Reduce quotation from ₹2,50,000 to ₹2,20,000

---

AI will:

- Adjust line items
- Suggest pricing revisions
- Regenerate quotation text
- Preserve profitability notes

---

## Output

Quotation Version 2

Quotation Version 3

etc.

---

# 6. AI Daily Business Summary

Purpose:

Generate daily business insights.

---

## Inputs

Database Data

- New Leads
- New Clients
- Quotations Sent
- Quotations Approved
- Revenue Collected
- Outstanding Payments

---

## Output

Daily Summary

Example:

Today's Summary

New Leads: 3

New Quotations: 2

Revenue Received: ₹50,000

Outstanding Amount: ₹1,25,000

Projects Won: 1

Projects Lost: 0

---

## Delivery

Telegram

---

# 7. AI Project Summary

Purpose:

Generate project status summaries.

---

## Inputs

Project Data

Site Visits

Labour Costs

Payments

Documents

---

## Output

Project Health Summary

Financial Summary

Pending Actions

---

# 8. Lead Management AI

Phase 2

Purpose:

Assist in lead tracking and conversion.

---

## Inputs

Lead Information

Lead Activities

Follow-up History

Quotation Status

---

## Outputs

Lead Summary

Follow-up Recommendations

Lead Priority Suggestions

---

# 9. Business Insights Engine

Phase 2

Purpose:

Generate business intelligence reports.

---

Examples

Which lead source generates most revenue?

Which services have highest success rate?

Which quotation range converts best?

Average project value?

Average quotation approval time?

---

# 10. Telegram Automation

Purpose:

Notify business owners automatically.

---

## Notifications

New Lead Created

Quotation Generated

Quotation Approved

Project Won

Outstanding Payment Alert

Daily Business Summary

---

## Delivery Channel

Telegram Bot

---

# 11. n8n Workflow Inventory

Workflow 1

Lead Notification Workflow

Trigger:

New Lead Created

Action:

Send Telegram Notification

---

Workflow 2

Quotation Generation Workflow

Trigger:

Generate AI Quotation

Action:

OpenAI

↓

Generate Content

↓

Save Database

↓

Generate PDF

---

Workflow 3

Quotation Revision Workflow

Trigger:

Client Requests Revision

Action:

OpenAI

↓

Generate New Version

↓

Save Version History

---

Workflow 4

Daily Business Summary Workflow

Trigger:

Every Day 7 PM

Action:

Collect Metrics

↓

Generate AI Summary

↓

Send Telegram Message

---

Workflow 5

Outstanding Payment Reminder

Trigger:

Daily Schedule

Action:

Find Overdue Payments

↓

Generate Reminder

↓

Send Telegram Alert

---

# 12. OpenAI Integration Design

Purpose:

Provide content generation.

---

Models

Development:

GPT-4o-mini

Production:

Latest OpenAI Model

---

Use Cases

Quotation Generation

Quotation Revision

Business Summary

Project Summary

Lead Summary

---

# 13. Prompt Library

Prompt 1

Quotation Generator

Prompt 2

Quotation Regenerator

Prompt 3

Daily Business Summary

Prompt 4

Project Summary

Prompt 5

Lead Summary

---

All prompts will be stored in:

prompts/

folder

for centralized maintenance.

---

# 14. AI Audit Logging

Every AI request must store:

Prompt

Response

Timestamp

User

Status

Model Used

Purpose

---

Benefits

Cost Monitoring

Quality Tracking

Debugging

Compliance

---

# 15. Future Enhancements

WhatsApp Integration

Voice-to-Quotation

Image-to-Quotation

AI Project Risk Detection

AI Revenue Forecasting

AI Proposal Generator

Mobile AI Assistant

---

# 16. Success Metrics

Quotation Creation Time

Target:

< 5 Minutes

---

Lead Follow-up Time

Target:

< 1 Day

---

Daily Reporting Time

Target:

0 Manual Effort

---

Quotation Revision Time

Target:

< 2 Minutes

---

# 17. AI Workflow Approval

Status:

Approved

Version:

1.0