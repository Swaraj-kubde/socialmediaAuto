# socialmediaAuto
Social Media Auto-Posting Automation (n8n Workflow)
Overview

This workflow demonstrates an end-to-end automation that posts content to X (Twitter) whenever a new entry is added in a connected Google Sheet.
The setup shows how to build a fully automated posting pipeline using n8n without manual intervention.

Although the recruiter’s task allowed connecting two social media platforms, I intentionally avoided Facebook and LinkedIn for this demo:

Facebook: My personal account currently has a technical login issue, so I couldn’t authenticate n8n with the Facebook Graph API.

LinkedIn: I did not want to perform automation tests on my official LinkedIn account (to avoid unintended or untrustworthy activity).

The automation still demonstrates the same required skills:
Trigger → Extract Data → Format → Auto-Post to social media.

Tech Stack

n8n

Google Sheets

X (Twitter) API (OAuth2)

Workflow Summary
Trigger

Google Sheets Trigger node

Polls the sheet every minute for any new row

When a new row is detected, it passes the row contents to the next node

Data Fetching

Google Sheets (Get Row) node

Pulls the updated row values

Extracts the content that will be posted to X

Posting to X

Create Tweet node

Takes the filtered row value (1st column) and automatically publishes it as a tweet

Tweet format used:

this is n8n automation testing {{ $json["1st column"] }}

Workflow Structure
Google Sheets Trigger
        ↓
Get Row(s) from Sheet
        ↓
Create Tweet (Post to X)

Files Included

n8n workflow JSON (view-only)

Short screen recording showing:

Adding a new row in Google Sheets

Automation detecting the change

Tweet posted automatically

README (this file)

How to Use

Import the provided .json workflow into your n8n instance

Add your own:

Google Sheets credentials

X (Twitter) OAuth2 credentials

Activate the workflow

Add a new row in your Google Sheet → watch the tweet get created automatically
Important Note

Facebook and LinkedIn nodes were not used intentionally:

Facebook: account login issue

LinkedIn: avoided posting from my official LinkedIn profile

The purpose of the demo is to show automation capability, not to post on multiple personal accounts.
