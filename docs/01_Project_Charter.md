 # Greenscape Business Operating System (GBOS)

## Project Charter

### Project Name

Greenscape Business Operating System (GBOS)

---

### Client

Greenscape Solutions

---

### Prepared By

Darren John

Role: AI Business Solutions Consultant

---

### Project Start Date

16 September 2026

---

### Project Status

In Progress

---

### Version

1.0

---

### Business Overview

Greenscape Solutions is a fencing and gardening company specializing in landscaping, fencing, artificial grass, vertical gardens, and related outdoor infrastructure projects.

The business is currently managed by the founder and his son.

Most business operations are managed manually through phone calls, WhatsApp conversations, paper records, and spreadsheets.

---

### Problem Statement

The business currently lacks a centralized system to manage:

- Customers
- Projects
- Quotations
- Labour Costs
- Payments
- Documents
- Business Reporting

This results in limited visibility into operations, project profitability, outstanding collections, and overall business performance.

---

### Project Objective

Design and develop a centralized Business Operating System that digitizes business operations and introduces AI-powered automation to improve efficiency, visibility, and decision-making.

## Success Criteria

The project will be considered successful if the following objectives are achieved:

### Operational Objectives

- All customer information is managed digitally.
- All projects are tracked within the system.
- Quotations are generated and stored digitally.
- Labour costs are tracked per project.
- Payments and outstanding balances are visible.
- Business documents are centrally stored.

### Reporting Objectives

- Business dashboard provides real-time visibility.
- Revenue and collections can be monitored.
- Project status can be tracked.

### AI Objectives

- AI-assisted quotation generation is operational.
- Daily business summaries are automated.
- Overdue payment alerts are automated.

### Technical Objectives

- System is accessible through a web browser.
- Data is stored securely in PostgreSQL.
- Architecture supports future enhancements without major redesign.

## Project Scope

### In Scope

#### Core Modules

- Customer Management
- Project Management
- Product & Pricing Master
- Quotation Management
- Labour Cost Tracking
- Payment Management
- Document Management
- Dashboard & Analytics

#### AI Features

- AI-Assisted Quotation Generation
- Daily Business Summary
- Overdue Payment Alerts

#### Automation Features

- n8n Workflow Automation
- Telegram Notifications
- Scheduled Business Reports

---

### Out of Scope (Phase 1)

- Inventory Management
- Payroll Management
- Labour Attendance System
- Mobile Application
- Customer Portal
- Vendor Portal
- Revenue Forecasting
- AI Chat Assistant
- WhatsApp Integration
- GST Filing Automation

---

## Stakeholders

### Business Stakeholders

#### Project Sponsor

Greenscape Solutions

#### Business Owners

- Father
- Son

#### End Users

- Father
- Son

---

## Constraints

### Budget Constraints

- Project must be developed using free or low-cost tools.
- No paid SaaS platforms unless approved later.

### Technical Constraints

- Must use React for frontend development.
- Must use FastAPI for backend development.
- Must use PostgreSQL as primary database.
- Must support future AI enhancements.

### Resource Constraints

- Single developer project.
- Development performed alongside learning activities.

---

## Assumptions

- Internet connectivity is available.
- Business owners will provide product pricing data.
- Business owners will provide quotation templates.
- Product HSN codes will be maintained through the Product Master.
- Project data volume will remain within free-tier cloud limits during Phase 1.

---

## Expected Benefits

### Business Benefits

- Centralized business operations.
- Reduced manual effort.
- Improved project visibility.
- Better payment tracking.
- Improved quotation management.
- Better labour cost visibility.

### Operational Benefits

- Faster quotation creation.
- Centralized document storage.
- Real-time business reporting.
- Improved project tracking.

### AI Benefits

- Reduced quotation preparation time.
- Automated business summaries.
- Automated overdue payment alerts.
- Foundation for future AI enhancements.

---

## Risks

| Risk | Mitigation |
|--------|--------|
| Incomplete business requirements | Conduct regular review sessions |
| Changes in business process | Maintain backlog and change log |
| Learning curve for React | Follow structured implementation approach |
| AI output inconsistencies | Human review before sharing quotations |
| Free-tier limitations | Monitor usage and optimize resources |

---

## Project Deliverables

### Deliverable 1

Business Operating System

Includes:

- Customers
- Projects
- Quotations
- Payments
- Labour Tracking
- Documents

### Deliverable 2

Business Analytics Dashboard

Includes:

- Revenue Tracking
- Collections Tracking
- Project Status Monitoring
- Labour Cost Visibility

### Deliverable 3

AI & Automation Layer

Includes:

- AI Quotation Generation
- Daily Business Summary
- Overdue Payment Alerts
- n8n Workflow Automation

---

## Approval

This Project Charter establishes the business objectives, scope, assumptions, constraints, risks, and success criteria for the Greenscape Business Operating System (GBOS) project.

Approved By:

Greenscape Solutions

Status:

Approved for Solution Architecture Phase