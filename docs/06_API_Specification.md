# API Specification Document

# Greenscape Business Operating System (GBOS)

Version: 1.0

Status: Approved

---

# 1. API Overview

Backend Framework:

FastAPI

API Style:

REST API

Data Format:

JSON

Authentication:

Phase 1 - No Authentication

Phase 2 - JWT Authentication

Base URL:

/api/v1

---

# 2. API Design Principles

- RESTful Design
- Consistent Response Structure
- Version Controlled APIs
- Pagination Support
- AI Integration Ready
- Mobile Application Ready

---

# 3. Standard Response Format

## Success Response

```json
{
  "success": true,
  "message": "Operation successful",
  "data": {}
}
```

## Error Response

```json
{
  "success": false,
  "message": "Error occurred",
  "errors": []
}
```

---

# 4. Lead APIs

## GET /leads

Get all leads.

Filters:

- Status
- Lead Source
- Date Range

---

## GET /leads/{id}

Get lead details.

---

## POST /leads

Create lead.

---

## PUT /leads/{id}

Update lead.

---

## POST /leads/{id}/convert

Convert lead into client.

---

## PATCH /leads/{id}/status

Update lead status.

---

# 5. Client APIs

## GET /clients

Purpose:

Get all clients.

Filters:

- Name
- Mobile Number
- City
- Lead Source

---

## GET /clients/{id}

Purpose:

Get client details.

---

## POST /clients

Purpose:

Create client.

Request Fields:

- Client Name
- Company Name
- Contact Person
- Mobile Number
- Email
- GST Number
- Address
- City
- State
- Pincode
- Lead Source

---

## PUT /clients/{id}

Purpose:

Update client.

---

## DELETE /clients/{id}

Purpose:

Soft delete client.

---

# 6. Project APIs

## GET /projects

Purpose:

Get all projects.

Filters:

- Status
- Client
- Outcome
- Date Range

---

## GET /projects/{id}

Purpose:

Get project details.

---

## POST /projects

Purpose:

Create project.

Request Fields:

- Client
- Project Name
- Project Type
- Project Value
- Status

---

## PUT /projects/{id}

Purpose:

Update project.

---

## PATCH /projects/{id}/status

Purpose:

Update project status.

---

## DELETE /projects/{id}

Purpose:

Soft delete project.

---

# 7. Project Site APIs

## GET /project-sites

Get all project sites.

---

## GET /project-sites/{id}

Get site details.

---

## POST /project-sites

Create site.

Fields:

- Site Name
- Site Address
- City
- State
- Pincode
- Site Visit Date
- Visit Notes
- Measurement Notes

---

## PUT /project-sites/{id}

Update site.

---

# 8. Services APIs

## GET /services

Get all services.

---

## POST /services

Create service.

---

## PUT /services/{id}

Update service.

---

## DELETE /services/{id}

Deactivate service.

---

# 9. Products APIs

## GET /products

Get all products.

---

## GET /products/{id}

Get product details.

---

## POST /products

Create product.

Fields:

- Product Name
- HSN Code
- GST %
- Unit
- Default Rate

---

## PUT /products/{id}

Update product.

---

## DELETE /products/{id}

Deactivate product.

---

# 10. Quotation APIs

## GET /quotations

Get all quotations.

Filters:

- Client
- Project
- Status
- Date Range

---

## GET /quotations/{id}

Get quotation details.

---

## POST /quotations

Create quotation.

---

## PUT /quotations/{id}

Update quotation.

---

## POST /quotations/{id}/send

Mark quotation as sent.

---

## POST /quotations/{id}/approve

Approve quotation.

---

## POST /quotations/{id}/reject

Reject quotation.

---

# 11. Quotation Version APIs

## GET /quotation-versions

Get all versions.

---

## POST /quotation-versions

Create new version.

Purpose:

Revision history management.

---

## GET /quotation-versions/{id}

Get version details.

---

# 12. Quotation Line Item APIs

## GET /quotation-line-items

Get all line items.

---

## POST /quotation-line-items

Create line item.

Fields:

- Product
- Service
- Description
- Measurement
- Quantity
- Unit
- Rate

---

## PUT /quotation-line-items/{id}

Update line item.

---

## DELETE /quotation-line-items/{id}

Remove line item.

---

# 13. Labour APIs

## GET /labour-costs

Get labour entries.

---

## POST /labour-costs

Create labour entry.

Fields:

- Labour Name
- Mobile Number
- Work Type
- Days Worked
- Rate Per Day

---

## PUT /labour-costs/{id}

Update labour entry.

---

## DELETE /labour-costs/{id}

Delete labour entry.

---

# 14. Payment APIs

## GET /payments

Get payments.

---

## POST /payments

Create payment.

Fields:

- Payment Date
- Amount
- Payment Method
- Reference Number

---

## PUT /payments/{id}

Update payment.

---

# 15. Document APIs

## GET /documents

Get documents.

---

## POST /documents/upload

Upload document.

Supported Types:

- Quotation
- Invoice
- Site Photo
- Agreement
- Drawing
- Completion Certificate

---

## DELETE /documents/{id}

Delete document.

---

# 16. Dashboard APIs

## GET /dashboard/summary

Returns:

- Total Clients
- Total Projects
- Active Projects
- Revenue
- Outstanding Payments

---

## GET /dashboard/project-status

Returns project status counts.

---

## GET /dashboard/lead-sources

Returns lead source analytics.

---

## GET /dashboard/project-outcomes

Returns win/loss analytics.

---

# 17. AI APIs

## POST /ai/generate-quotation

Purpose:

Generate quotation draft using AI.

Input:

- Project Details
- Products
- Measurements
- Rates

Output:

- Professional Description
- Scope of Work
- Terms & Conditions

---

## POST /ai/regenerate-quotation

Purpose:

Generate revised quotation.

Input:

- Existing Quotation
- Target Amount
- Client Feedback

Output:

- Revised Quotation

---

## POST /ai/project-summary

Purpose:

Generate project summary.

---

## POST /ai/daily-business-summary

Purpose:

Generate daily business report.

---

# 18. Future APIs

## Authentication APIs

- Login
- Logout
- Refresh Token

---

## Notification APIs

- Telegram Notifications
- WhatsApp Notifications

---

## Mobile APIs

Reserved for future mobile application.

---

# 19. API Version Control

Current Version:

v1

Base URL:

/api/v1

Future:

/api/v2

---

# 20. API Specification Approval

Status:

Approved

Version:

1.0