# Playscraper Bot

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Moderation-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-AI_Analyzer-8A2BE2?style=for-the-badge)

**Playscraper Bot** is a professional moderator utility that leverages AI to extract and summarize metadata from app stores and open-source repositories. By automatically posting standardized, highly informative comment headers on submissions containing links to these platforms, it helps moderators and users verify shared software content at a glance without having to click away from Reddit.

## Key Features

- **Multi-Source Detection**: Seamlessly identifies links from the Google Play Store, F-Droid, GitHub, GitLab, and Codeberg.
- **AI-Powered Summaries**: Integrates with Gemini 2.5 Flash to rapidly extract key metrics like developer name, download counts, categories, user ratings, and content ratings.
- **Eligibility-First Processing**: Employs a sophisticated delayed-processing pattern. It waits a configurable amount of time to confirm a new post is still live (not caught by Reddit's spam filters or AutoModerator) before making any expensive external API calls, saving your quota.
- **Automated or Manual Automation**: Can run automatically on all new posts, or be set to manual mode where it only scans when a moderator clicks "Trigger App Scraper" in the Mod menu.
- **Configurable Detail Levels**: Tailor the output comment's length by choosing between "Confirmed Only", "General Details", or "Full Details".

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/playscraper-bot-flowchart.png)

1. A user posts a link to a supported app store or repository.
2. The bot schedules a short delay. Once the delay passes, it checks if the post was removed by Reddit's filters or AutoModerator.
3. If the post is still valid, the bot scrapes the external URL.
4. The raw HTML is fed to Gemini to extract structured metadata.
5. A highly readable, stickied comment is posted summarizing the app for the community.

## Setup & Configuration

1. **Install**: Add **Playscraper Bot** via the App Directory.
2. **API Key Requirement**: Obtain a free Google Gemini API Key from Google AI Studio.
3. **App Settings**: 
   - Input your Gemini API Key into the app settings.
   - Choose which sources to detect (e.g., enable GitHub but disable Play Store).
   - Set your preferred Comment Detail Level.
4. **Monitoring**: The bot operates silently in the background unless configured for Manual mode.

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/playscraper-bot/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/playscraper-bot/PRIVACY.md)

---
*Built for Reddit's moderator community.*
