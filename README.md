# 🌐 Website Contact Form → CRM Automation

An n8n automation that receives website contact-form submissions, processes the inquiry, sends the data to a CRM system, and automatically sends a confirmation email to the customer.

## 🎯 Project Overview

Businesses receive customer inquiries through their websites every day.

Without automation, someone has to manually:

1. Check the incoming inquiry
2. Copy the customer details
3. Add the lead to a CRM
4. Send a confirmation email

This workflow automates that process.

### Automated Flow

Website Contact Form
        ↓
Webhook
        ↓
Data Processing
        ↓
CRM
        ↓
Customer Confirmation Email

## ⚙️ Workflow

The main n8n workflow consists of four stages:

### 1. Webhook

Receives the contact-form submission through an HTTP POST request.

### 2. Code

Processes and prepares the incoming customer information.

The workflow extracts:

- Name
- Email
- Phone
- Service
- Message

### 3. CRM Integration

The processed inquiry is sent to the CRM through an HTTP request.

For this project, a local mock CRM endpoint was used to simulate an external CRM API.

The CRM stores:

- CRM ID
- Name
- Email
- Phone
- Service
- Message
- Status
- Created At

### 4. Email Confirmation

After the inquiry is processed, the workflow sends automated email notifications to both the business owner and the customer.

## 🧪 Testing

The workflow was tested using a `curl` HTTP request from Windows Command Prompt to simulate a website sending a contact-form submission.

Example test data:

- Name: Rahul Sharma
- Email: rahul@gmail.com
- Phone: 9876543210
- Service: E-commerce Website
- Message: I need an online store for my clothing business

The test successfully triggered the complete automation.

### Result

The submitted inquiry was:

✅ Received by the webhook  
✅ Processed by n8n  
✅ Added to the CRM  
✅ Confirmation email sent to the customer
✅ Owner notification email sent successfully

## 🛠️ Technologies Used

- n8n
- JavaScript
- HTTP / REST
- Webhooks
- Google Sheets
- Gmail
- JSON
- Windows Command Prompt (`curl`)

## 📁 Repository Structure

```text
p3-website-to-crm-automation/
│
├── README.md
│
└── screenshots/
    ├── 01-main-workflow.png
    ├── 02-mock-crm-workflow.png
    ├── 03-test-request.png
    ├── 04-crm-result.png
    ├── 05-owner-lead-notification.png
    └── 06-customer-confirmation.png
```


💼 Business Value

This automation reduces manual data entry and ensures that customer inquiries are captured and acknowledged automatically.

It can be adapted for:

Web development agencies
Marketing agencies
Consultants
Local businesses
Service providers
E-commerce businesses

The same automation pattern can be extended to real CRM platforms and additional business systems.

🔐 Notes

This repository contains a portfolio/demo implementation.

The CRM endpoint used in this project is a local mock CRM created for testing. In a production environment, the HTTP Request step could be connected to an actual CRM or business API.

No credentials or private authentication information are included in this repository.

🚀 Future Improvements

Possible production extensions include:

Real CRM integration
Automatic lead qualification
Automatic lead assignment
Slack/Teams notifications
WhatsApp notifications
AI-powered lead classification
Follow-up automation
Error handling and alerting
Database integration
