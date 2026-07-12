# Suspended Remove

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Moderation-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Security-8A2BE2?style=for-the-badge)

**Suspended Remove** is a professional-grade security utility designed to automatically manage content submitted by suspended or shadowbanned users. Since the Reddit API restricts interacting with suspended profiles, this app safely monitors your community queues in the background, verifying account statuses and silently removing invalid content without manual moderator effort.

## Key Features

- **Automated Perimeter Defense**: Constantly monitors the modqueue and spam queues for contributions from accounts that are no longer accessible (shadowbanned or suspended).
- **Silent Conflict Resolution**: Instantly removes flagged content to keep your queues clean. Can be configured to mark as spam or remove silently to prevent penalizing false-positive shadowbans.
- **Advanced Audit Integration**: Automatically appends internal mod notes to the removed content and the user's profile, ensuring transparent, long-term records for the mod team.
- **Multi-Day Verification**: Built-in retry logic verifies account accessibility across multiple days before acting, protecting users experiencing temporary API glitches.

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/suspended-remove-flowchart.png)

1. The app runs a background scan of your subreddit's modqueue and spam queue.
2. It attempts to load the author's profile via the API.
3. If the profile is inaccessible (returns undefined/404), the user is flagged.
4. The app checks the user multiple times over several days (based on your settings) to ensure it's not a temporary glitch.
5. If the account remains inaccessible, the app removes the content and logs the action via Mod Notes.

## Setup & Configuration

1. **Install**: Add **Suspended Remove** via the App Directory.
2. **App Settings**: Navigate to your subreddit's App Settings to configure:
   - The number of checks required before removal (1-3).
   - Whether to mark the items as spam.
   - The specific text to use for the automated Mod Notes.
3. **Usage**: The application immediately begins scanning queues in the background. No manual interaction is required.

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/suspended-remove/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/suspended-remove/PRIVACY.md)

---
*Built for Reddit's moderator community.*
