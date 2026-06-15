# AI-Powered Invoice Data Extraction & Automation using n8n

## Overview

Organizations often receive invoices in different formats, including text-based PDFs, scanned PDFs, and image files. Manually extracting information from hundreds of invoices is time-consuming and prone to errors. This workflow automates the entire process, from document retrieval to data extraction and storage, reducing manual effort and improving efficiency. This project automates the extraction of invoice data from unstructured documents such as PDFs and image files (PNG/JPG) and converts them into structured Google Sheets using n8n.

---

## Objectives

This project focuses on three core processes:

### Data Validation

- Retrieve invoice files from Google Drive
- Identify the file type (PDF or Image)
- Route files to the appropriate extraction process

### Data Extraction

- Extract invoice information from PDFs and images
- Convert unstructured data into structured data using OCR and AI
- Capture both invoice-level and item-level information

### Data Upload

- Store extracted data in Google Sheets
- Maintain separate sheets for invoice details and item details

The workflow automatically:

- Retrieves invoices from Google Drive
- Identifies file types (PDF or PNG/Image)
- Processes each file using the appropriate extraction method
- Extracts invoice-level and item-level information
- Stores extracted data in separate Google Sheets

---

## Technologies Used

### Workflow Automation

- n8n

### File Storage

- Google Drive

### OCR Processing

- OCR API (via HTTP Request)

### AI-Powered Information Extraction

- Google Gemini
- Groq (Experimented/Tested)
- OpenRouter (Experimented/Tested)

### Data Storage

- Google Sheets

---

## Workflow Architecture

```text
Manual Trigger
      │
      ▼
Search Files and Folders (Google Drive)
      │
      ▼
Loop Over Items
      │
      ▼
Download File
      │
      ▼
Switch (File Type Validation)
      │
 ┌────┴────┐
 ▼         ▼
PNG       PDF
 │          │
 ▼          ▼
HTTP Request (OCR)    Extract From File
 │                     │
 └──────────┬──────────┘
            ▼
         IF Node
            │
            ▼
  Information Extractor
            │
            ▼
 Google AI Chat Model
            │
            ▼
    Append to Sheet 1
            │
            ▼
       Edit Fields
            │
            ▼
         Split Out
            │
            ▼
 Append or Update Row
       in Sheet 2
```

---

## Data Output

### Sheet 1 – Invoice Information

Stores invoice-level details such as:

- Invoice Number
- Invoice Date
- Vendor Information
- Customer Information
- Tax Information
- Total Amount

### Sheet 2 – Item Information

Stores item-level details such as:

- Product Name
- Quantity
- Unit Price
- Item Total

---

## Business Value

This automation helps organizations:

- Reduce manual data entry effort
- Improve processing speed
- Minimize human errors
- Standardize invoice data collection
- Create structured datasets from unstructured documents
- Improve operational efficiency

---

## Learning Outcomes

Through this project, I gained hands-on experience in:

- Workflow automation using n8n
- Handling unstructured business documents
- OCR-based document processing
- AI-powered information extraction
- Data extraction and transformation
- End-to-end automation design
- Workflow testing and debugging
- Integrating Google Drive, AI models, OCR services, and Google Sheets into a single automated workflow

---

## Author

**Saranya K P**

This project was developed as part of my learning journey in workflow automation, AI-powered data extraction, and business process automation using n8n.
