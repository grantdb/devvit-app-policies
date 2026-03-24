# Suspended Account Remover
Automatically detects and removes queue items from suspended or shadowbanned users to keep your moderation queue clean.

## Overview
Suspended Account Remover is a lightweight, fully automated moderation tool that monitors your subreddit's mod queue and spam filters. Its primary purpose is to quickly identify and manage content originating from suspended or shadowbanned users, reducing manual moderation overhead.

## How It Works
Once installed, the application runs a background task every five minutes to scan recent queue items. If it detects a post or comment submitted by an account that Reddit has suspended or shadowbanned, it takes the following actions automatically:

- Removes the reported content from the standard queues.
- Appends a private removal note to the item.
- Adds an internal moderator note to the user's profile detailing the suspension status.

## Features
- **Zero Configuration:** Operates entirely in the background without requiring manual intervention, commands, or complex setup.
- **Massive Subreddit Safety:** Strictly caps background scans to a maximum of 100 standard and 100 spam queue items per interval. By streaming the data individually, the app is 100% resilient against Devvit execution timeouts, even on subreddits with multi-thousand item backlogs.
- **Efficient Caching:** Utilizes local cache indexing to instantly skip over already processed items and verified users, ensuring operations remain fast and compliant with platform limits.
- **Independent Action Handling:** Gracefully handles edge cases, such as when Reddit's global filters have already removed an item, ensuring that moderator notes are still dependably applied.

## Setup
There is no setup required. Simply install the application to your community. The core background monitoring job is triggered and officially begins routing data as soon as the installation process completes.
 
 
