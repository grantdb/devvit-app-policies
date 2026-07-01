# Playscraper Bot

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Moderation-blue?style=for-the-badge)

Playscraper Bot is a professional moderator utility that uses AI to extract and summarize metadata from app and repository links. It automatically posts standardized, informative comment headers for mobile apps and open-source projects — helping moderators verify shared content at a glance.

## Features

- **Multi-Source Detection**: Identifies links from Google Play Store, F-Droid, GitHub, GitLab, and Codeberg.
- **AI-Powered Summaries**: Uses Gemini 2.5 Flash to extract developer, downloads, category, rating, content rating, and more.
- **Delayed Eligibility-First Processing**: Waits a configurable delay before processing new posts, then confirms the post is still live (not removed, filtered, or spam) before making any external API calls. Prevents wasted quota on removed posts.
- **Automated Processing**: Detects and summarizes links in new posts automatically, or waits for moderator approval first.
- **Manual Trigger**: Supports on-demand scans via the native Reddit Post Menu (moderators only).
- **Configurable Detail Levels**: Choose between Confirmed Only, General Details, or Full Details comment modes.

## Install / Use

1. Install **Playscraper Bot** via the Reddit App Directory.
2. Configure your **Google Gemini API Key** in the app settings (required).
3. Choose which sources to detect and your preferred comment detail level.
4. The bot will automatically process new posts after a brief eligibility delay.
5. Moderators can trigger manual scans on any post using the **Trigger App Scraper** option in the Mod actions menu.

## Settings

| Setting | Description | Default |
|---|---|---|
| Gemini API Key | Required. Get one free from [Google AI Studio](https://aistudio.google.com). | — |
| Automation Mode | Auto (new posts) or Manual Only | Auto |
| Comment Detail Level | Confirmed Only / General / Full | General |
| App Sources to Detect | Play Store, F-Droid, GitHub, GitLab, Codeberg | Play, GitHub, F-Droid |
| Enable Delayed Processing | Wait before processing to confirm post is valid | Enabled |
| Processing Delay | Seconds to wait before the eligibility check (5–100) | 20 |
| Skip if Removed | Abort if post is removed before check runs | Enabled |
| Skip if Filtered | Abort if post is in modqueue before check runs | Enabled |
| Skip if Spam | Abort if post is marked spam before check runs | Enabled |

## Legal
This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/playscraper-bot/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/playscraper-bot/PRIVACY.md)

---
*Built for Reddit's moderator community.*
