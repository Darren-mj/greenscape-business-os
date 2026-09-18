 # Solution Architecture Document (SAD)

# Greenscape Business Operating System (GBOS)

Version: 1.0

Status: In Progress

Prepared By: Darren John

Role: AI Business Solutions Consultant

Date: 16 September 2026

---

# 1. Introduction

## 1.1 Purpose

The purpose of this document is to define the functional architecture, technical architecture, business processes, system components, integrations, and implementation approach for the Greenscape Business Operating System (GBOS).

The system will digitize client management, project management, quotation management, labour cost tracking, payment tracking, document management, business analytics, AI-powered quotation generation, and business automation.

---

## 1.2 Business Objectives

The primary objectives of the solution are:

- Centralize business operations.
- Improve project visibility.
- Improve payment tracking.
- Improve labour cost tracking.
- Automate repetitive business activities.
- Introduce AI-assisted business processes.
- Build a scalable foundation for future growth.

---

## 1.3 Scope

### Included

- Client Management
- Project Management
- Product & Pricing Master
- Quotation Management
- Labour Cost Tracking
- Payment Management
- Document Management
- Dashboard & Analytics
- AI Quotation Generation
- Daily Business Summary
- Overdue Payment Alerts
- n8n Workflow AI Automation

### Excluded

- Inventory Management
- Payroll Management
- Mobile Application - The architecture must be API-first so that a mobile application can be developed later without requiring backend redesign.
- Client Portal
- Vendor Portal
- WhatsApp Integration
- AI Chat Assistant
- Revenue Forecasting

---

# 2. User Model

## 2.1 System Users

The application will be used exclusively by:

- Business Owner (Father)
- Business Owner (Son)

Both users will have full system access.

No role hierarchy will be implemented in Phase 1.

---

## 2.2 Non-System Users

The following entities are not system users:

- Clients
- Labourers
- Vendors

Their information will be stored and managed within the application.

---

# 3. High Level Solution Architecture

```

React Frontend
       |
       |
       v

FastAPI Backend
       |
       |
       v

PostgreSQL Database (Neon)

       |
       |
       +-------------------+
       |                   |
       v                   v

Cloudinary           n8n AI Automation

                           |
                           v

                       OpenAI

                           |
                           v

                       Telegram

```

## Components

### Frontend

- React
- Vite
- Bootstrap
- Axios

### Backend

- FastAPI
- SQLAlchemy
- Alembic

### Database

- PostgreSQL (Neon)

### Storage

- Cloudinary

### AI Automation

- n8n

### AI

- OpenAI

### Notifications

- Telegram

---

# 4. Core Business Modules

## Module 1 – Client Management

Purpose:

Maintain all client information.

Features:

- Add Client
- Edit Client
- Search Client
- View Client History
- Track Lead Source

Lead Sources:

- Referral
- Website
- Instagram
- Facebook
- Google
- WhatsApp
- Existing Client
- Walk-in
- Other

---

## Module 2 – Project Management

Purpose:

Manage projects from enquiry to completion.

Features:

- Create Project
- Update Project Status
- Assign Client
- Track Revenue
- Track Progress

---

## Module 3 – Product & Pricing Master

Purpose:

Maintain product catalogue and pricing.

Features:

- Product Management
- Rate Management
- HSN Code Management
- GST Management

---

## Module 4 – Quotation Management

Purpose:

Create, manage, revise and store quotations.

Features:

- AI Quotation Generation
- Quotation PDF Generation
- Quotation Revision Management
- Quotation Version History
- Approved Quotation Tracking
- Store PDF Versions

Quotation Status:

- Draft
- Sent
- Under Review
- Revised
- Approved
- Rejected
- Expired

Versioning Example:

| Quotation No | Version | Status |
|-------------|----------|---------|
| Q-001 | V1 | Rejected |
| Q-001 | V2 | Revised |
| Q-001 | V3 | Approved |

Business Requirement:

If a client requests a revised amount, the system must:

- Retain the original quotation
- Generate a revised quotation
- Maintain revision history
- Store the final approved version

---

## Module 5 – Labour Cost Tracking

Purpose:

Track labour expenses against projects.

Features:

- Add Labour Entry
- Assign Project
- Record Cost
- Cost Analysis

---

## Module 6 – Payment Management

Purpose:

Track client payments and balances.

Features:

- Record Payments
- Track Outstanding
- Track Due Dates

---

## Module 7 – Document Management

Purpose:

Store and retrieve project documents.

Document Types:

- Quotations
- Invoices
- Site Photos
- Purchase Bills
- Other Project Documents

---

## Module 8 – Dashboard & Analytics

Purpose:

Provide business visibility.

KPIs:

- Total Clients
- Active Projects
- Revenue
- Collections
- Outstanding Amount
- Labour Cost
- Project Status

---

# 5. Business Process Overview

## Process 1

## Process 1

Lead
→ Client Creation
→ Site Visit
→ Measurement Collection
→ Project Creation
→ AI Quotation Generation
→ Client Review
→ Quotation Revision (if required)
→ Approval
→ Advance Payment
→ Project Execution
→ Labour Cost Tracking
→ Final Payment
→ Project Closure

## Process 2

Project → Labour Cost Tracking

## Process 3

AI Quotation Generation

## Process 4

Overdue Payment Alert AI Automation

## Process 5

Daily Business Summary AI Automation

---

# 6. AI Solution Architecture

## AI Feature 1

Smart Quotation Generator

Inputs:

- Product
- Measurement
- Labour Cost
- Transportation Cost
- Additional Charges
- Client Requirements

Outputs:

- AI Generated Description
- HSN Mapping
- GST Calculation
- Professional Quotation PDF

Capabilities:

- Generate Initial Quotation
- Regenerate Revised Quotations
- Maintain Version History
- Produce Final Approved Quotation

---

## AI Feature 2

Daily Business Summary

Generated automatically by n8n + openai.

Delivery Channel:

- Telegram

---

## AI Feature 3

Overdue Payment Alerts

Generated automatically by n8n + openai.

Delivery Channel:

- Telegram

---

# 7. AI Automation Architecture

Platform:

n8n + openai

Workflows:

### WF-001

Daily Business Summary

### WF-002

Overdue Payment Monitoring

### WF-003

AI Quotation Processing

---

# 8. Non Functional Requirements

## Performance

- Page load less than 3 seconds
- API response less than 2 seconds

## Availability

- Accessible through web browser

## Scalability

- Support future modules without redesign

## Security

- Secure login
- Protected APIs
- Secure database access

---

# 9. Assumptions

- Stable internet connectivity
- Product pricing maintained by business owners
- HSN codes maintained through Product Master
- Free-tier cloud resources sufficient for Phase 1

---
# 10. Project Outcome Tracking

Purpose:

Track project conversion and business performance.

Project Outcomes:

- Won
- Lost
- Cancelled

Mandatory Reasons for Lost or Cancelled Projects:

Examples:

- Price Too High
- Competitor Selected
- Project Postponed
- Client Budget Constraints
- No Response
- Scope Change
- Other

Business Benefits:

- Conversion Analysis
- Lead Source Analysis
- Pricing Analysis
- Future AI Insights

Example Insight:

"38% of lost projects were lost due to pricing concerns."


# 11. Future Enhancements

Mobile Application

The solution will follow an API-first architecture, allowing future mobile application development without requiring backend redesign.

Potential Mobile Technologies:

- React Native
- Flutter

Phase 2 possibilities:

- Inventory Management
- Vendor Management
- Mobile Application
- WhatsApp Integration
- AI Business Advisor
- Revenue Forecasting
- Advanced Analytics

---

# 12. Approval

Status: Approved  & Locked

Architecture Approved for Detailed Design Phase

Document Version:

1.1
