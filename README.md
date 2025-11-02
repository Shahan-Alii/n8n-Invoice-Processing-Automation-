

# Invoice Processing Automation with n8n

An automated invoice management system built using **n8n**, **LangChain**, and **Google Gemini**.
It extracts invoice details, updates a spreadsheet, and sends confirmation emails — all automatically.

---

<img width="1156" height="482" alt="Image" src="https://github.com/user-attachments/assets/884ad1ee-0f75-496c-a49b-8800b97396f8" />


## Overview

The client’s accounting team was manually handling invoices — downloading PDFs, extracting details, updating spreadsheets, and emailing confirmations.
Each invoice took 4–5 minutes to process, leading to errors and delays.

To solve this, I built an **end-to-end automation** in n8n that detects new invoices, extracts information using AI, and updates records instantly.

---

## How It Works

1. **Google Drive Trigger:**
   Detects new invoice PDFs added to a specific folder.

2. **File Download & Text Extraction:**
   Downloads the file and extracts text from the PDF using n8n’s built-in file parser.

3. **AI Data Extraction:**
   Uses **LangChain** with **Google Gemini** to identify key invoice fields such as:

   * Invoice Number
   * Bill To
   * Balance
   * Ship To
   * Date

4. **Database Update:**
   Automatically appends extracted data to a **Google Sheets** database in real time.

5. **Email Confirmation:**
   Generates and sends an automated confirmation email via the **Gmail API**.

---

## Results

* Reduced invoice processing time from **5 minutes to under 30 seconds**
* Improved data accuracy by **over 95%**
* Saved around **20 hours of manual work per week**
* Achieved a fully automated, error-free process

---

## Tech Stack

* **Automation Platform:** n8n
* **AI Models:** Google Gemini (PaLM), OpenRouter (DeepSeek)
* **Language Framework:** LangChain
* **Integrations:** Google Drive, Google Sheets, Gmail
* **File Handling:** PDF Text Extraction

---

## Workflow Components

| Component             | Description                                      |
| --------------------- | ------------------------------------------------ |
| Google Drive Trigger  | Detects new invoices uploaded to a folder        |
| File Downloader       | Downloads the invoice PDF                        |
| Extract from File     | Extracts text from the invoice                   |
| Information Extractor | Identifies key invoice fields using LangChain    |
| Google Sheets Node    | Updates the spreadsheet in real time             |
| AI Agent              | Generates structured email notifications         |
| Gmail Node            | Sends confirmation emails to the accounting team |

---

## Setup Instructions

1. **Clone or Download the Repository**

   ```bash
   git clone https://github.com/yourusername/invoice-processing-automation.git
   cd invoice-processing-automation
   ```

2. **Import the Workflow**

   * Open your **n8n dashboard**
   * Click **“Import from File”**
   * Upload `Invoice Processing.json`

3. **Set Up Credentials**

   * Google Drive OAuth2 (for file trigger & download)
   * Google Sheets OAuth2 (for data updates)
   * Google Gemini API (for AI extraction)
   * Gmail OAuth2 (for sending confirmation emails)
   * OpenRouter API (optional AI enhancement)

4. **Configure Variables**

   * Replace Google Drive folder ID with your own
   * Update Google Sheets document ID
   * Modify email recipient and template as needed

5. **Activate Workflow**

   * Set the workflow to “Active” in n8n
   * Upload a new invoice file to Google Drive to test the automation

---



## Business Impact

This automation streamlined the client’s entire billing process — eliminating manual entry, improving data accuracy, and freeing the team to focus on financial analysis instead of repetitive work.

---

## Files Included

* `Invoice Processing.json` — Full n8n workflow export
* Optional setup documentation (on request)

---

## Future Enhancements

* Integration with accounting tools like QuickBooks or Xero
* Slack/Email notifications for failed invoice extractions
* Dashboard for tracking processed invoice metrics


