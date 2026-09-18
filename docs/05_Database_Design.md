# Database Design Document

# Greenscape Business Operating System (GBOS)

Version: 1.0

Status: Approved

---

# 1. Database Overview

Database Engine:

PostgreSQL

Hosting:

Neon PostgreSQL

ORM:

SQLAlchemy

Migration Tool:

Alembic

---

# 2. Database Design Principles

The database design follows the following principles:

- Normalized structure
- Auditability
- Scalability
- Historical tracking
- AI-ready architecture
- Minimal data duplication
- API-first architecture
- Future mobile application support

---

# 3. Core Business Entities

## Master Tables

1. Users
2. Lead Sources
3. Project Outcomes
4. Services
5. Products
6. Quotation Templates
7. Payment Methods
8. Document Types

---

## Transaction Tables

9. Leads
10. Clients
11. Projects
12. Project Sites
13. Project Services
14. Project Products
15. Quotations
16. Quotation Versions
17. Quotation Line Items
18. Labour Costs
19. Payments
20. Documents

---

## AI & Automation Tables (Future)

20. AI Logs
21. Notification Logs
22. Workflow Execution Logs

---

# 4. Entity Relationship Diagram (ERD)

```text
lead_sources
    |
    v
clients
    |
    v
projects
    |
    +--------------------+
    |                    |
    v                    v
project_sites      quotations
                         |
                         v
                quotation_versions
                         |
                         v
                quotation_line_items

projects
    |
    +--------------------+
    |                    |
    v                    v
labour_costs        payments

projects
    |
    v
documents

projects
    |
    +--------------------+
    |                    |
    v                    v
project_services   project_products
```

---

# 5. Service Master

Services offered by Greenscape:

1. Landscape Design & Execution
2. Garden Development
3. Vertical Garden Installation
4. Artificial Grass Installation
5. WPC Deck & Pergola Installation
6. Drain Cell & Geotextile Installation
7. HPL Cladding Installation
8. Fencing Solutions
9. Paving Works
10. Fabrication Works
11. Terrace Garden Development
12. Irrigation System Installation
13. Garden Lighting
14. Garden Renovation
15. Annual Landscape Maintenance

---

# 6. Product Master

Products supplied by Greenscape:

1. Lattice Panels
2. Artificial Grass
3. Vertical Garden Materials
4. Drain Cells
5. Geotextile Fabric
6. Grass Pavers
7. Garden Edging
8. WPC Decking
9. WPC Wall Panels
10. Pergolas
11. HPL Cladding Sheets
12. Louvers
13. Roofing Sheets
14. Terracotta Clay Tiles
15. Swimming Pool Tiles
16. Woven Bamboo Panels
17. Garden Ladder
18. Wire Mesh & Orion Fencing
19. EPDM Sports Flooring
20. Planters & Garden Accessories

---

# 7. Table Definitions

## Table: lead_sources

Purpose:

Stores client acquisition channels.

### Columns

| Column | Type |
|----------|----------|
| id | UUID PK |
| source_name | VARCHAR(100) |
| description | TEXT |
| is_active | BOOLEAN |
| created_at | TIMESTAMP |
| updated_at | TIMESTAMP |

---

## Table: project_outcomes

Purpose:

Stores project completion outcomes.

### Columns

| Column | Type |
|----------|----------|
| id | UUID PK |
| outcome_name | VARCHAR(50) |
| description | TEXT |
| is_active | BOOLEAN |
| created_at | TIMESTAMP |
| updated_at | TIMESTAMP |

Sample Values:

- Won
- Lost
- Cancelled

---

## Table: services

### Columns

| Column | Type |
|----------|----------|
| id | UUID PK |
| service_name | VARCHAR(200) |
| description | TEXT |
| is_active | BOOLEAN |
| created_at | TIMESTAMP |
| updated_at | TIMESTAMP |

---

## Table: products

### Columns

| Column | Type |
|----------|----------|
| id | UUID PK |
| product_name | VARCHAR(200) |
| hsn_code | VARCHAR(50) |
| gst_percentage | DECIMAL(5,2) |
| unit | VARCHAR(50) |
| default_rate | DECIMAL(12,2) |
| description | TEXT |
| is_active | BOOLEAN |
| created_at | TIMESTAMP |
| updated_at | TIMESTAMP |

---

## Table: quotation_templates

### Columns

| Column | Type |
|----------|----------|
| id | UUID PK |
| template_name | VARCHAR(100) |
| payment_terms | TEXT |
| validity_terms | TEXT |
| delivery_terms | TEXT |
| notes | TEXT |
| is_default | BOOLEAN |
| created_at | TIMESTAMP |
| updated_at | TIMESTAMP |

---

## Table: leads

Purpose:

Store all incoming business enquiries before conversion into clients.

### Columns

| Column | Type |
|----------|----------|
| id | UUID PK |
| lead_source_id | UUID FK |
| lead_name | VARCHAR(200) |
| company_name | VARCHAR(200) |
| mobile_number | VARCHAR(20) |
| email | VARCHAR(200) |
| city | VARCHAR(100) |
| status | VARCHAR(50) |
| next_followup_date | DATE |
| notes | TEXT |
| converted_to_client | BOOLEAN |
| converted_date | DATE |
| created_at | TIMESTAMP |
| updated_at | TIMESTAMP |

### Lead Status Values

- New
- Contacted
- Site Visit Scheduled
- Measurement Completed
- Quotation Sent
- Won
- Lost

---

## Table: clients

### Columns

| Column | Type |
|----------|----------|
| id | UUID PK |
| lead_source_id | UUID FK |
| client_name | VARCHAR(200) |
| company_name | VARCHAR(200) |
| contact_person | VARCHAR(200) |
| mobile_number | VARCHAR(20) |
| email | VARCHAR(200) |
| gst_number | VARCHAR(50) |
| address | TEXT |
| city | VARCHAR(100) |
| state | VARCHAR(100) |
| pincode | VARCHAR(20) |
| created_at | TIMESTAMP |
| updated_at | TIMESTAMP |

---

## Table: projects

### Columns

| Column | Type |
|----------|----------|
| id | UUID PK |
| client_id | UUID FK |
| project_outcome_id | UUID FK |
| project_name | VARCHAR(255) |
| project_type | VARCHAR(100) |
| project_value | DECIMAL(15,2) |
| status | VARCHAR(50) |
| outcome_reason | TEXT |
| start_date | DATE |
| end_date | DATE |
| created_at | TIMESTAMP |
| updated_at | TIMESTAMP |

---

## Table: project_sites

### Columns

| Column | Type |
|----------|----------|
| id | UUID PK |
| project_id | UUID FK |
| site_name | VARCHAR(200) |
| site_address | TEXT |
| city | VARCHAR(100) |
| state | VARCHAR(100) |
| pincode | VARCHAR(20) |
| latitude | DECIMAL(10,7) |
| longitude | DECIMAL(10,7) |
| site_visit_date | DATE |
| visited_by | VARCHAR(200) |
| visit_notes | TEXT |
| measurement_notes | TEXT |
| created_at | TIMESTAMP |
| updated_at | TIMESTAMP |

---

## Table: project_services

### Columns

| Column | Type |
|----------|----------|
| id | UUID PK |
| project_id | UUID FK |
| service_id | UUID FK |
| created_at | TIMESTAMP |

---

## Table: project_products

### Columns

| Column | Type |
|----------|----------|
| id | UUID PK |
| project_id | UUID FK |
| product_id | UUID FK |
| estimated_quantity | DECIMAL(12,2) |
| unit | VARCHAR(50) |
| created_at | TIMESTAMP |

---

## Table: quotations

### Columns

| Column | Type |
|----------|----------|
| id | UUID PK |
| client_id | UUID FK |
| project_id | UUID FK |
| quotation_number | VARCHAR(50) |
| current_version | INTEGER |
| status | VARCHAR(50) |
| sent_date | DATE |
| client_response_date | DATE |
| approval_date | DATE |
| total_amount | DECIMAL(15,2) |
| created_at | TIMESTAMP |
| updated_at | TIMESTAMP |

---

## Table: quotation_versions

### Columns

| Column | Type |
|----------|----------|
| id | UUID PK |
| quotation_id | UUID FK |
| version_number | INTEGER |
| revision_notes | TEXT |
| generated_by_ai | BOOLEAN |
| total_amount | DECIMAL(15,2) |
| status | VARCHAR(50) |
| generated_at | TIMESTAMP |

---

## Table: quotation_line_items

### Columns

| Column | Type |
|----------|----------|
| id | UUID PK |
| quotation_version_id | UUID FK |
| product_id | UUID FK NULL |
| service_id | UUID FK NULL |
| description | TEXT |
| measurement | DECIMAL(12,2) |
| quantity | DECIMAL(12,2) |
| unit | VARCHAR(50) |
| rate | DECIMAL(12,2) |
| amount | DECIMAL(15,2) |

---

## Table: labour_costs

### Columns

| Column | Type |
|----------|----------|
| id | UUID PK |
| project_id | UUID FK |
| labour_name | VARCHAR(200) |
| mobile_number | VARCHAR(20) |
| work_type | VARCHAR(200) |
| days_worked | DECIMAL(5,2) |
| rate_per_day | DECIMAL(10,2) |
| total_amount | DECIMAL(15,2) |
| work_date | DATE |
| created_at | TIMESTAMP |

---

## Table: payments

### Columns

| Column | Type |
|----------|----------|
| id | UUID PK |
| project_id | UUID FK |
| quotation_id | UUID FK |
| payment_date | DATE |
| amount | DECIMAL(15,2) |
| payment_method | VARCHAR(50) |
| reference_number | VARCHAR(100) |
| remarks | TEXT |
| created_at | TIMESTAMP |

---

## Table: documents

### Columns

| Column | Type |
|----------|----------|
| id | UUID PK |
| client_id | UUID FK |
| project_id | UUID FK |
| quotation_id | UUID FK NULL |
| document_type | VARCHAR(100) |
| file_name | VARCHAR(255) |
| cloudinary_url | TEXT |
| upload_date | TIMESTAMP |

---

# 8. Relationships

| Parent | Child | Relationship |
|----------|----------|----------|
| lead_sources | clients | One-to-Many |
| clients | projects | One-to-Many |
| projects | project_sites | One-to-Many |
| projects | quotations | One-to-Many |
| quotations | quotation_versions | One-to-Many |
| quotation_versions | quotation_line_items | One-to-Many |
| projects | labour_costs | One-to-Many |
| projects | payments | One-to-Many |
| projects | documents | One-to-Many |
| projects | project_services | One-to-Many |
| projects | project_products | One-to-Many |
| lead_sources | leads | One-to-Many |
| leads | clients | One-to-One (Optional) |
---

# 9. Business Rules

## BR-001

One Project can contain one or more Services.

## BR-002

One Project can contain one or more Products.

## BR-003

Quotation Total = Line Items + Additional Charges.

## BR-004

One Quotation can contain multiple Versions.

## BR-005

One Project can contain one or more Sites.

## BR-006

Every Client must have a Lead Source.

## BR-007

Every Completed Project must have an Outcome.

## BR-008

Lost or Cancelled projects require a reason.

## BR-009

Multiple payments are allowed against a Project.

## BR-010

Measurements must be stored permanently.

## BR-011

Project photos must be stored against Projects.

## BR-012

Quotation Sent Date, Response Date and Approval Date must be tracked.

## BR-013

Every enquiry must begin as a Lead.

---

## BR-014

A Lead can be converted into a Client.

---

## BR-015

Won Leads must be converted into Clients.

---

## BR-016

Lost Leads require a Loss Reason.

---

# 10. Audit Fields

All transactional tables shall include:

| Field |
|----------|
| created_at |
| updated_at |

Future Enhancement:

| Field |
|----------|
| created_by |
| updated_by |

---

# 11. Future Tables

## ai_logs

Store AI prompts and responses.

## notification_logs

Store Telegram and future notification history.

## workflow_execution_logs

Store n8n workflow execution history.

---

# 12. Database Design Approval

Status:

Approved

Version:

1.0

Approved By:

Greenscape Business Operating System Project Team