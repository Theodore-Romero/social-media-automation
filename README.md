# Medical Spa Social Media Automation

An automated social posting system that pulls approved content from Google Sheets, retrieves media from Google Drive, and publishes across multiple platforms on a schedule.

![n8n](https://img.shields.io/badge/n8n-EA4B71?style=flat&logo=n8n&logoColor=white)
![Google Sheets](https://img.shields.io/badge/Google%20Sheets-34A853?style=flat&logo=googlesheets&logoColor=white)
![Google Drive](https://img.shields.io/badge/Google%20Drive-4285F4?style=flat&logo=googledrive&logoColor=white)
![Instagram](https://img.shields.io/badge/Instagram-E4405F?style=flat&logo=instagram&logoColor=white)
![TikTok](https://img.shields.io/badge/TikTok-000000?style=flat&logo=tiktok&logoColor=white)
![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white)
![Facebook](https://img.shields.io/badge/Facebook-1877F2?style=flat&logo=facebook&logoColor=white)
![X](https://img.shields.io/badge/X-000000?style=flat&logo=x&logoColor=white)

---

## 📊 Overview

This project answers the operational question: **How do we consistently publish social content without manual posting every week?**

The system automatically:
- Runs on a schedule (every 3 days by default)
- Pulls the next approved post from a Google Sheets “Posting Queue”
- Downloads media from a Google Drive share link
- Uploads the media and posts to configured platforms
- Writes back to the sheet with a Posted timestamp or Error status

---

## 🛠️ Tech Stack

| Component | Technology |
|----------|------------|
| Workflow Automation | n8n |
| Content Queue | Google Sheets |
| Media Storage | Google Drive |
| Social Publishing | Blotato (multi-platform posting) |

---

## 📐 Architecture

Schedule Trigger (every 3 days)

│

▼

Google Sheets: Posting Queue (next row)

│

▼

Extract Google Drive media ID

│

▼

Download Media (public Drive link)

│

├── on error ──► Mark row as Errored

│

▼

Upload Media

│

▼

Post to Platforms (IG / TikTok / Threads / LinkedIn / Facebook / X)

│

▼

Mark row as Posted + Posted At timestamp

---


## 📁 Repository Structure

medical-spa-social-automation/
├── README.md

├── n8n-workflows/

│ └── medical-spa-social-media-automation.json

├── docs/

│ ├── setup-guide.md

│ ├── posting-queue-schema.md

│ 

└── screenshots/

├── workflow-overview.png

---

## ⚙️ Setup Instructions

See: `docs/setup-guide.md`

---

## 📄 License

This project is open source and available under the MIT License.
