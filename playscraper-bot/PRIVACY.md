# Privacy Policy for playscraper-bot

Last updated: April 13, 2026

## 1. Information Collection
The `playscraper-bot` Devvit application is designed to enhance subreddit posts by automatically fetching information about Google Play Store applications linked in the community. 

- **Data we access:** The bot reads the content of posts and comments to identify Google Play Store URLs and Android package IDs. 
- **Data we collect:** The bot does NOT collect, store, or transmit any personally identifiable information (PII), user data, account details, or browsing history of Reddit users. 
- **External Services:** The bot securely sends the extracted Package ID to the **Google Gemini API** (`generativelanguage.googleapis.com`) to retrieve public, structured app data via Google Search Grounding.

## 2. Storage and Security
The bot does not maintain a database or permanent storage. Post data is processed ephemerally in memory during the execution of the Devvit trigger.

## 3. Third-Party Access
We do not share, sell, or distribute any user information to third parties. App data retrieval is strictly limited to network requests between the Reddit Devvit server and the Google Gemini API.

## 4. Consent
By installing and using `playscraper-bot` in your subreddit, you consent to the bot reading public post content strictly for the purpose of executing its core functionality.

## 5. Contact
If you have any questions or concerns regarding this privacy policy, please contact the bot developer via Reddit.
