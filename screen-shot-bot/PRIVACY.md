# Privacy Policy for screen-shot-bot

Last updated: March 12, 2026

## 1. Information Collection
The `screen-shot-bot` Devvit application is designed to extract text from images (screenshots, terminal photos) posted on Reddit.

- **Data we access:** The bot reads images attached to posts and comments.
- **Data we collect:** The bot does NOT collect, store, or transmit any personally identifiable information (PII), user data, account details, or browsing history. 
- **External Services:** 
    - The bot sends image data to the **Google Gemini API** (`generativelanguage.googleapis.com`) to extract text.
    - If the extracted text is too long for a Reddit comment, it may be uploaded to **dpaste.com** or **rentry.co** to provide a full-text link.

## 2. Storage and Security
The bot does not maintain a database or permanent storage of your images. Data is processed ephemerally in memory during execution.

## 3. Third-Party Access
We do not share or sell any user information. Access to third-party APIs (Google Gemini, Pastebin services) is limited to the data required for text extraction and hosting.

## 4. Consent
By using `screen-shot-bot` or images in a subreddit where it is active, you acknowledge that the bot will process the image for text extraction purposes.

## 5. Contact
If you have any questions or concerns, please contact the developer via Reddit.
