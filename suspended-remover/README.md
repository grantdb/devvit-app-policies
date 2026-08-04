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

> [!IMPORTANT]
> **ATTENTION MODERATORS — MAJOR FEATURE UPDATE (v1.0.72)**
> **PLEASE REVIEW YOUR APP SETTINGS AFTER UPGRADING!**
> Suspended Remove now operates on a **Two-Stage Enforcement Model**. Items are held during a waiting/verification window before final removal.

> [!WARNING]
> **CRITICAL BEHAVIOR NOTICES**:
> 1. **New Waiting-Stage Behavior Options**:
>    - **Filter** *(Default)* — Keeps items in your review queue with a `[WAITING]` marker so your mod team sees active verification in progress.
>    - **Temporary Remove** — Moves items out of the review queue to the removed queue while multi-day checks run.
> 2. **Recovery & Approval Limits**: If an account becomes accessible again, the app can auto-approve items it temporarily removed. **Note**: Reddit may NOT re-trigger AutoModerator or third-party app checks on approved items like a brand-new submission.
> 3. **Setting Precedence**: The legacy *Mark as spam* setting is now deprecated. Use the new **Final action after threshold** setting (`Remove` vs `Remove as spam`). If both are set, the new setting takes priority.

### Key Changes Summary
- **Two-Stage Enforcement**: Items pass through a waiting stage (`filter_waiting` or `temp_remove_waiting`) before final action (`remove` or `spam`).
- **Independent Mod Notes**: Waiting-period notes (`[WAITING]`) and final removal notes can now be configured and toggled independently.
- **Legacy Timing Preserved**: Defaults remain `recheckDays = 0` and `confirmChecks = 1` for zero rollout friction.
- **Enhanced Settings Documentation**: All settings pages have been rewritten with plain-English moderator guidance.


## Support

For help, bug reports, or feature requests, post in r/grantdb.
Please include the app name, what you expected, what happened, and any error text or screenshots.

## Legal

This application is subject to the following legal agreements:
- [Terms of Service](https://github.com/grantdb/reddit-app-legal/blob/main/suspended-remove/TERMS.md)
- [Privacy Policy](https://github.com/grantdb/reddit-app-legal/blob/main/suspended-remove/PRIVACY.md)

---
*Built for Reddit's moderator community.*
