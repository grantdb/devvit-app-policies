# Suspended Remove

![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)
![Devvit](https://img.shields.io/badge/Devvit-FF4500?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Moderation-blue?style=for-the-badge)
![Type](https://img.shields.io/badge/Type-Security-8A2BE2?style=for-the-badge)

**Suspended Remove** is a professional-grade security utility designed to automatically manage content submitted by suspended or shadowbanned users. Since the Reddit API restricts interacting with suspended profiles, this app safely monitors your community queues in the background, verifying account statuses over a configurable window before taking final action.

## Key Features

- **Two-Stage Enforcement**: Content from suspended accounts is first held through a configurable waiting-period action, then subject to a separate final action once all verification checks pass. Moderators stay informed throughout.
- **Configurable Waiting-Stage Options**: Choose between keeping items in the review queue with a `[WAITING]` marker (default), or temporarily moving them to the removed queue while checks continue.
- **Recovery Support**: When Temporary Remove is used and a later check shows the account is accessible again, the app can automatically approve the item it removed.
- **Advanced Audit Integration**: Automatically appends internal mod notes to items and the user's profile at each stage, with separate note text and toggles for the waiting period and final action.
- **Multi-Day Verification**: Built-in retry logic verifies account accessibility across multiple checks before acting, protecting users experiencing temporary API glitches. Items are automatically expired from the queue after 14 days.

## How It Works

![Logic Flowchart](https://raw.githubusercontent.com/grantdb/reddit-app-legal/main/assets/flowcharts/suspended-remove-flowchart.png)

1. The app runs a background scan of your subreddit's modqueue and spam queue — covering both **posts and comments**.
2. It attempts to load the author's profile via the Reddit API.
3. If the profile is inaccessible (suspended or shadowbanned), the item is queued for verification.
4. On the first confirmed inaccessibility, the **waiting-period action** is applied:
   - **Filter** *(default)*: keeps the item in the review queue with a `[WAITING]` mod note so moderators can see it during the checking window.
   - **Temp Remove**: moves the item to the removed queue while checks continue.
5. The app re-checks the account on the configured schedule. If the account becomes accessible again, the item may be approved (Temp Remove path only, if enabled).
6. If the account remains inaccessible after all checks, the **final action** is applied (Remove or Remove as spam) and the action is logged via Mod Notes.
7. Items are automatically expired from the queue after 14 days.

> **Note on approval**: approving a temporarily removed item restores its visibility, but may not cause AutoModerator or other moderation apps to re-run on it the same way a brand-new submission would.

## Setup & Configuration

1. **Install**: Add **Suspended Remove** via the App Directory.
2. **App Settings**: Navigate to your subreddit's App Settings to configure:
   - The number of checks required before final action (default: 1).
   - The waiting-period action: Filter (default) or Temp Remove.
   - The final action: Remove (default, recommended) or Remove as spam.
   - Separate mod note text and toggles for the waiting period and final action.
   - Optional mod note on the user's profile at final action time.
3. **Usage**: The application immediately begins scanning queues in the background. Moderators can also trigger an instant scan via the "GuardHub: Scan Modqueue for Suspended Users" menu item.

## What Changed

**v1.0.72** adds clearer waiting-stage behavior options.

- **Two waiting-stage options** are now available:
  - **Filter** *(default)* — keeps the item in the review queue with a `[WAITING]` marker in the mod note so moderators can see it during the checking period.
  - **Temporary Remove** — moves the item to the removed queue while checks continue. If a later check shows the account is accessible again, the app can approve the item it removed.
- **Legacy timing defaults are preserved** — `recheckDays = 0` and `confirmChecks = 1` are unchanged. Existing installed subreddits will not see a change in timing behavior after upgrading.
- **Recovery approval** — when Temporary Remove is used and the account later becomes accessible, the app can approve the item it removed. This is on by default and can be turned off. Note: approving a removed item restores its visibility but may not cause AutoModerator or other moderation apps to re-run on it as though it were a brand-new submission.
- **Deprecated spam setting retained** — the older "Mark as spam" setting is still shown for compatibility. If you had it configured, it continues to work. The new "Final action" setting takes priority if both are set.
- **Separate note controls** — waiting-period notes and final-action notes can now be toggled independently. Both default to on. If you had notes turned off before, that preference is preserved through the upgrade.
- **Settings help text** is rewritten in plain moderator language throughout.

## Support

For help, bug reports, or feature requests, post in r/grantdb.
Please include the app name, what you expected, what happened, and any error text or screenshots.

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/suspended-remove/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/suspended-remove/PRIVACY.md)

---
*Built for Reddit's moderator community.*
