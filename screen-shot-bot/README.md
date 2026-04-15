# Terminal Text Extractor
Automatically extracts and transcribes text from screenshots of terminals, command lines, and boot logs.

> [!IMPORTANT]
> **Requirement:** A **Google Gemini API Key** is required for this bot to function. You can get a free key from [Google AI Studio](https://aistudio.google.com/).

## Overview
Terminal Text Extractor is an accessibility and utility tool designed to make technical support subreddits easier to navigate. Instead of forcing users to manually type out error messages from screenshots, the bot automatically reads the image and posts a perfectly formatted text block of the terminal output. 

## How It Works
The application scans incoming image submissions and analyzes them for command-line interfaces or terminal windows using Gemini Vision AI. If terminal text is detected, the bot automatically extracts the text verbatim and pins a formatted comment to the top of the post containing the transcribed code.

## Setup Instructions
1. Install the bot to your subreddit.
2. Go to your **Subreddit Settings** -> **Apps** -> **Terminal Text Extractor**.
3. Locate the **"Gemini API Key"** setting.
4. Paste your API key from Google AI Studio and save.

## Features
- **Automated Transcription:** Instantly pulls text from terminal screenshots, saving time for both posters and helpers who need to copy/paste log snippets.
- **Improved Code Searchability:** By converting screenshots of code into text, errors and logs become fully searchable within your subreddit. 
- **Manual Extraction Tool:** Includes a handy post action menu button so moderators can manually trigger text extraction on older posts or missed images.
- **Smart Filtering:** The bot intelligently avoids trying to extract text from generic desktop showcases, gaming screenshots, or web browsers, focusing strictly on terminal content.
