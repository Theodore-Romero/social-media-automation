# Medical Spa Social Media Automation — Setup Guide

This guide walks you through deploying the workflow in n8n.

---

## Prerequisites

- An n8n instance (cloud or self-hosted)
- Google account access to the posting spreadsheet
- Google Drive share links for media assets
- Blotato account connected to your social profiles

---

## Step 1: Google Sheets Setup

Create a Google Sheet with a tab named:

- **Posting Queue**

Follow the exact column expectations in `docs/posting-queue-schema.md`.

---

## Step 2: Media Storage (Google Drive)

Each row should contain a **Google Drive share link** in the Media URL column.
The workflow extracts the Drive file ID and downloads using a public URL.

---

## Step 3: Import the Workflow into n8n

1. Open n8n
2. Import `n8n-workflows/medical-spa-social-media-automation.json`
3. Configure credentials:
   - Google Sheets OAuth
   - Blotato credentials / accounts per platform

---

## Step 4: Configure Schedule

The default cadence is **every 3 days**.
Adjust the Schedule Trigger node if you want daily or weekly posting.

---

## Step 5: Test Run

1. Add a test row with a valid Media URL + Caption
2. Run the workflow manually
3. Confirm:
   - media downloads successfully
   - posts publish to connected platforms
   - the row updates to **Posted** with a timestamp
   - errors mark the row as **Errored**

---

## Go-Live Checklist

- Posting Queue tab exists
- Drive links are accessible
- Blotato accounts connected
- Workflow is activated
