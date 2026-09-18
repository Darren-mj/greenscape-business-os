# Screen Inventory Document

# Greenscape Business Operating System (GBOS)

Version: 1.0

Status: Approved

---

# 1. Purpose

This document defines all screens required for the Greenscape Business Operating System (GBOS).

The screen inventory acts as the blueprint for React frontend development.

---

# 2. Screen Categories

## Master Management

1. Lead Sources
2. Services
3. Products
4. Quotation Templates

---

## Client Management

5. Client List
6. Client Details
7. Add Client
8. Edit Client

---

## Project Management

9. Project List
10. Project Details
11. Add Project
12. Edit Project
13. Project Site Management

---

## Quotation Management

14. Quotation List
15. Quotation Details
16. Create Quotation
17. Quotation Revision
18. Quotation Version History

---

## Labour Management

19. Labour Cost List
20. Add Labour Cost
21. Labour Cost Details

---

## Payment Management

22. Payment List
23. Add Payment
24. Payment Details

---

## Document Management

25. Document List
26. Upload Document
27. Document Viewer

---

## Dashboard & Analytics

28. Executive Dashboard
29. Lead Source Analytics
30. Project Outcome Analytics
31. Revenue Dashboard

---

## AI Features

32. AI Quotation Generator
33. AI Quotation Regenerator
34. AI Project Summary
35. AI Daily Business Summary

---

# 3. Executive Dashboard

Purpose:

Provide business overview.

Widgets:

- Total Clients
- Total Projects
- Active Projects
- Revenue
- Outstanding Payments
- Quotations Pending Approval
- Projects Won
- Projects Lost

Charts:

- Revenue Trend
- Lead Source Distribution
- Project Outcome Distribution

---

# 4. Client Screens

## Client List

Columns:

- Client Name
- Company Name
- Contact Person
- Mobile Number
- City
- Lead Source

Actions:

- View
- Edit
- Delete

---

## Client Details

Sections:

### Basic Information

- Client Name
- Company Name
- Contact Person

### Contact Information

- Mobile Number
- Email

### Address

- Address
- City
- State
- Pincode

### Related Records

- Projects
- Quotations
- Documents

---

## Add/Edit Client

Fields:

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

# 5. Project Screens

## Project List

Columns:

- Project Name
- Client
- Status
- Project Value
- Start Date
- End Date

Filters:

- Status
- Client
- Date Range

---

## Project Details

Sections:

### Project Information

- Project Name
- Project Type
- Status
- Outcome

### Site Information

- Site Address
- Site Visit Date
- Measurements

### Financial Information

- Project Value
- Payments Received
- Outstanding Amount

### Related Records

- Quotations
- Labour Costs
- Documents

---

## Add/Edit Project

Fields:

- Client
- Project Name
- Project Type
- Status
- Estimated Value

---

## Project Site Management

Fields:

- Site Name
- Site Address
- City
- State
- Pincode
- Latitude
- Longitude
- Site Visit Date
- Visit Notes
- Measurement Notes

---

# 6. Product Management Screens

## Product List

Columns:

- Product Name
- HSN Code
- GST %
- Unit
- Default Rate

Actions:

- Edit
- Deactivate

---

## Add/Edit Product

Fields:

- Product Name
- HSN Code
- GST Percentage
- Unit
- Default Rate
- Description

---

# 7. Service Management Screens

## Service List

Columns:

- Service Name
- Status

---

## Add/Edit Service

Fields:

- Service Name
- Description

---

# 8. Quotation Screens

## Quotation List

Columns:

- Quotation Number
- Client
- Project
- Amount
- Status
- Created Date

Filters:

- Status
- Client
- Date Range

---

## Quotation Details

Sections:

### Header

- Quotation Number
- Client
- Project

### Line Items

- Product
- Service
- Measurement
- Quantity
- Rate
- Amount

### Additional Charges

- Transportation
- Accommodation
- Food
- Other

### Totals

- Subtotal
- GST
- Grand Total

### Version History

- All revisions

---

## Create Quotation

Fields:

- Client
- Project
- Products
- Services
- Measurements
- Rates

Actions:

- Save Draft
- Generate PDF
- Generate With AI

---

## Quotation Revision

Fields:

- Existing Amount
- Target Amount
- Client Feedback

Actions:

- AI Regenerate
- Save New Version

---

## Version History

Columns:

- Version Number
- Created Date
- Amount
- Status
- Revision Notes

---

# 9. Labour Management Screens

## Labour Cost List

Columns:

- Labour Name
- Mobile Number
- Work Type
- Days Worked
- Amount

---

## Add Labour Cost

Fields:

- Labour Name
- Mobile Number
- Work Type
- Days Worked
- Rate Per Day

---

# 10. Payment Screens

## Payment List

Columns:

- Payment Date
- Amount
- Payment Method
- Reference Number

---

## Add Payment

Fields:

- Project
- Amount
- Payment Method
- Reference Number
- Remarks

---

# 11. Document Screens

## Document List

Columns:

- File Name
- Document Type
- Project
- Upload Date

Filters:

- Document Type
- Project

---

## Upload Document

Fields:

- Client
- Project
- Quotation
- Document Type
- File Upload

---

## Document Viewer

Supports:

- PDF
- Images

Categories:

- Quotation
- Invoice
- Site Photo
- Agreement
- Drawing
- Completion Certificate

---

# 12. Analytics Screens

## Lead Source Analytics

Metrics:

- Leads by Source
- Projects by Source
- Revenue by Source

---

## Project Outcome Analytics

Metrics:

- Won Projects
- Lost Projects
- Win Percentage

---

## Revenue Dashboard

Metrics:

- Monthly Revenue
- Outstanding Amount
- Payment Trends

---

# 13. AI Screens

## AI Quotation Generator

Inputs:

- Project Details
- Products
- Measurements
- Rates

Outputs:

- Professional Description
- Scope of Work
- Terms & Conditions

---

## AI Quotation Regenerator

Inputs:

- Existing Quotation
- Client Feedback
- Target Amount

Outputs:

- Revised Quotation

---

## AI Project Summary

Outputs:

- Project Overview
- Financial Summary
- Progress Summary

---

## AI Daily Business Summary

Outputs:

- Daily Revenue
- New Leads
- Pending Quotations
- Outstanding Payments

---

# 14. Navigation Structure

Dashboard

├── Clients

├── Projects

├── Quotations

├── Products

├── Services

├── Labour

├── Payments

├── Documents

├── Analytics

└── AI Tools

## 16. Lead Management

1. Lead List
2. Lead Details
3. Add Lead
4. Edit Lead
5. Lead Pipeline

Actions:

View
Edit
Convert to Client
---

# 15. Mobile Readiness

The screen design must support:

- Desktop
- Tablet
- Mobile (Future Phase)

Responsive design is mandatory.

---

# 16. Screen Inventory Approval

Status:

Approved

Version:

1.0