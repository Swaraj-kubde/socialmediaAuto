# socialmediaAuto
Social Media Posting Automation (Google Sheets → X/Twitter)

This workflow automates posting content to X (Twitter) whenever a new row is added or updated in a Google Sheet. It removes all manual steps and makes your content pipeline fast and consistent.

#Overview

This n8n automation listens for any row update in a specific Google Sheet.
When a new entry is added (or an existing row is modified), the workflow automatically pushes that content to X (Twitter) using the X API.

Key Features

Google Sheets Trigger – Fires instantly when a row is added/updated.
Dynamic Content Parsing – Reads caption/content fields directly from the sheet.
Auto Publishing to X – Publishes the text to your X account using authenticated API credentials.
Fully No-Code – Managed entirely inside n8n.

Workflow Structure
1. Google Sheets Trigger (Watch for Changes)
Mode: Watch Rows / On Updated or Added Row
When a new row comes in, n8n pulls:
post_text (caption)
image_url (optional, if you added)
scheduled_time (if applicable)
Any other custom fields you’ve created.


2. X (Twitter) Node – Create a Tweet

Uses your OAuth credentials.

Publishes:

Text-only tweet, or

Tweet with media if configured

4. Logging / Response Node

Updates a “Status” column in your Google Sheet:

SUCCESS

FAILED

ERROR: <details>

Prerequisites

Before using this workflow, ensure you have:

1. Google Cloud Project

Enable Google Sheets API

Connect your Google account inside n8n

2. X (Twitter) Developer Account

App created in developer portal

API Keys + OAuth tokens added as X credentials inside n8n

3. Required Columns in Google Sheet

Your sheet should include (at minimum):

Column Name	Purpose
post_text	Text of the tweet
image_url (optional)	Media to attach
status	Filled automatically by n8n
How to Use

Add or update a row in the Google Sheet.

Automation triggers instantly.

Content is posted to your X account.

Sheet updates with posting status.

Use Cases

Daily content calendar

Auto-posting marketing campaigns

Managing client accounts

Scheduled content pipelines

Bulk posting workflows

Deployment & Scaling

You can duplicate this workflow for:

LinkedIn

Instagram (via Buffer or API)

Facebook / Pages

Threads (through API wrappers)

Works with Airtable or Notion if you want to migrate later.
