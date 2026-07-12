# Screen Shot Bot

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Utility](https://img.shields.io/badge/Category-Utility-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-AI_Analyzer-8A2BE2?style=for-the-badge)

**Screen Shot Bot** is a specialized accessibility and support tool designed to bridge the gap between technical image uploads and searchable community data. Rather than forcing users to manually re-type long error logs from a photo, this bot uses advanced AI to automatically transcribe text from terminal windows, boot logs, and configuration screens into clean, indexable comments.

## Key Features

- **Automated AI Transcription**: Integrates with Gemini to instantly and accurately extract precise text strings from complex, grainy, or poorly lit technical images.
- **Searchable Indexing**: By converting static images of crash logs into text-based stickied comments, it ensures that your subreddit's error reports are fully searchable by future users experiencing the same issue.
- **Configurable Targets**: Granular settings allow you to choose exactly what the bot looks for. You can configure it to transcribe *all* terminal images, or only activate when it detects specific contexts (like Errors, System Info, or Config files).
- **Mod Approval Coverage**: Safely operates alongside your existing moderation workflow. It will automatically check new posts, and intelligently re-process posts if they are held and later approved by a moderator.
- **Manual Actions**: Moderators can manually trigger an on-demand transcription of older posts using the Mod Actions menu.

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/screen-shot-bot-flowchart.png)

1. A user submits a post containing an image (e.g., a photo of a kernel panic).
2. The bot intercepts the image and securely sends it to the AI engine for contextual analysis.
3. The AI determines if the image matches your configured target category (e.g., "Errors & Crash logs").
4. If it matches, the AI performs Optical Character Recognition (OCR), extracting the text cleanly.
5. The bot replies to the post with the transcribed text, formatting it in a code block for readability.

## Setup & Configuration

1. **Install**: Add **Screen Shot Bot** to your subreddit via the App Directory.
2. **App Settings**: 
   - Add your Google Gemini API key to the settings.
   - Select your "Extraction Target" from the dropdown list.
3. **Usage**: The bot runs automatically. To use it manually on an old post, use the "Extract text from image (Gemini)" menu item in the post's mod menu.

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/screen-shot-bot/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/screen-shot-bot/PRIVACY.md)

---
*Built for Reddit's moderator community.*
