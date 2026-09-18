# Deployment Architecture Document

# Greenscape Business Operating System (GBOS)

Version: 1.0

Status: Approved

---

# 1. Purpose

This document defines the deployment architecture for the Greenscape Business Operating System.

The architecture is designed to:

- Minimize operational cost
- Support AI automation
- Support future scaling
- Support cloud deployment
- Support mobile application expansion

---

# 2. Deployment Architecture Overview

Frontend

React
↓
Render

Backend

FastAPI
↓
Render

Database

PostgreSQL
↓
Neon

File Storage

Cloudinary

Automation Layer

n8n VPS

AI Services

OpenAI API

Notifications

Telegram Bot

---

# 3. Infrastructure Components

## Frontend

Technology:

React

Hosting:

Render

Purpose:

User Interface

---

## Backend

Technology:

FastAPI

Hosting:

Render

Purpose:

Business Logic and API Layer

---

## Database

Technology:

PostgreSQL

Hosting:

Neon

Purpose:

Application Data Storage

---

## File Storage

Technology:

Cloudinary

Purpose:

Store:

- Quotations
- Site Photos
- Agreements
- Drawings
- Completion Certificates

---

## Automation Platform

Technology:

n8n

Hosting:

Existing VPS

Purpose:

Workflow Automation

---

## AI Layer

Technology:

OpenAI API

Purpose:

- Quotation Generation
- Quotation Revision
- Project Summary
- Daily Business Summary

---

## Notification Layer

Technology:

Telegram Bot

Purpose:

- New Lead Alerts
- Quotation Alerts
- Payment Alerts
- Daily Summary

---

# 4. Environment Architecture

## Development

Developer Laptop

Docker

Containers:

- React
- FastAPI
- PostgreSQL

Development Tools:

- VS Code
- Git
- Docker Desktop

---

## Testing

Render Preview Environment

Neon Test Database

Cloudinary Test Folder

---

## Production

Render Production

Neon Production

Cloudinary Production

n8n VPS Production

---

# 5. CI/CD Strategy

Source Control

GitHub

Branch Strategy

main

production-ready code

develop

active development

feature/*

feature branches

---

Deployment Flow

Developer

↓

GitHub

↓

Render Auto Deploy

↓

Production

---

# 6. Security Design

Secrets Stored In:

Render Environment Variables

n8n Credentials Manager

---

Protected Secrets

OPENAI_API_KEY

DATABASE_URL

CLOUDINARY_API_KEY

TELEGRAM_BOT_TOKEN

---

# 7. Backup Strategy

Database

Neon Automated Backups

Documents

Cloudinary Backup

Source Code

GitHub Repository

---

# 8. Monitoring Strategy

Application

Render Logs

Automation

n8n Execution Logs

Database

Neon Monitoring

AI Usage

OpenAI Usage Dashboard

---

# 9. Scalability Strategy

Phase 1

Single Business

Greenscape

---

Phase 2

Multiple Users

Role Management

---

Phase 3

Multi-Tenant SaaS

Multiple Companies

---

# 10. Cost Estimate

Frontend

Render Free

Backend

Render Free

Database

Neon Free

Cloudinary

Free Tier

n8n

Existing VPS

Total Monthly Cost

₹0 (excluding OpenAI API usage)

---

# 11. Deployment Approval

Status:

Approved

Version:

1.0