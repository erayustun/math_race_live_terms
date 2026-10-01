# Privacy Policy for Math Race Live

**Effective date:** October 1, 2026

Math Race Live is operated by Eray ÜSTÜN ("we", "us", or "our"). This Privacy Policy explains how information is handled when you use the Math Race Live mobile application and related game services.

For privacy questions, contact [erayustun.dev@gmail.com](mailto:erayustun.dev@gmail.com).

## Information we process

### Authentication and account information

Math Race Live starts with a Firebase anonymous account. You may later authenticate with Google or Apple. Firebase Authentication and the selected sign-in provider process the information needed to authenticate you. Our backend receives a Firebase user identifier, sign-in-provider information, and provider identifiers used to associate the authentication method with the correct game account. A provider may also supply a name claim. We do not use your email address as a public game identity, and the Math Race Live PostgreSQL account records do not store an email address.

If you link Google or Apple to the current anonymous account, the same game account and history are preserved. If the provider already belongs to another Math Race Live account, the app does not merge the two accounts. With your confirmation, it discards the current temporary guest's backend data before switching to the existing provider account.

Signing out does not delete your authenticated account or its game history. It creates a new anonymous session on that device. You can return to the authenticated account by signing in again with its linked provider.

### Profile and public identity

Authenticated users may choose a username. Usernames are case-insensitively unique and may be changed. A chosen username can be visible to other players in match results and leaderboards. If no username exists, the service uses a stable `Player####` public fallback derived from an internal identifier. It does not expose the Firebase user identifier or raw internal identifier.

We store an internal account identifier, the optional username, account creation and update timestamps, account status, and authentication-provider mappings. Anonymous users cannot choose a username.

### Gameplay, results, and leaderboards

We process and store information needed to operate synchronized arithmetic matches, including:

- match participation and join time;
- questions delivered to a player and security tokens or token hashes;
- selected answers, answer receipt and response-time measurements, correctness, and validation outcomes;
- awarded points, match totals, correct-answer counts, ranks, and finalized match results; and
- daily leaderboard statistics derived from authoritative gameplay records.

Public match results and daily leaderboards show a username or `Player####` fallback. Deleted accounts are shown as `Deleted Player` where retained competition records remain visible.

### Activity-based online count

While the app is in the foreground, it periodically sends an authenticated presence refresh. We store the account's latest presence timestamp and use activity within a 45-second window to produce the approximate `N online` count. This is an activity estimate, not exact real-time presence. Presence does not affect gameplay, scoring, or ranking.

### Product analytics

Our backend stores product analytics events such as app/session start, match joined, match completed, result viewed, leaderboard viewed, profile viewed, and session end where available. These records may include a generated session or event identifier, internal account identifier, event time, platform, app version, and a match identifier for match-related events.

Google Analytics for Firebase is also enabled. It automatically processes app-use and engagement information and technical information such as app version, device and operating-system information, and approximate geographic information according to Google's Firebase Analytics behavior and settings. We additionally send only these three custom Firebase Analytics event names: `match_joined`, `match_completed`, and `result_viewed`. We do not attach Firebase UID, internal user ID, username, email, match ID, score, rank, questions, answers, or answer timing as custom parameters to those events.

### Operational and security information

The backend creates operational logs containing information such as request ID, HTTP method and route, response status and size, duration, rate-limit category, and safe error details. Application logs are designed not to include authorization headers, authentication tokens, request bodies, usernames, email addresses, provider identifiers, or database credentials. Hosting and network providers may process normal connection information, such as IP address and device/network metadata, to deliver and secure their services.

We also retain validation and audit records needed for server-authoritative scoring, duplicate prevention, abuse prevention, troubleshooting, and competition integrity.

## How we use information

We use the information described above to:

- authenticate users and preserve or restore game accounts;
- provide profiles, synchronized matches, scoring, results, rankings, and leaderboards;
- show the approximate activity-based online count;
- protect the service against replay, automation, manipulation, abuse, and unauthorized access;
- diagnose failures, maintain availability, and enforce rate limits;
- understand aggregate app engagement and whether players continue playing matches; and
- comply with legal obligations and enforce our Terms and Game Rules.

## Service providers

The current product uses:

- **Google Firebase Authentication** for anonymous, Google, and Apple-linked authentication;
- **Google Sign-In** and **Apple Sign in with Apple** when you choose those providers;
- **Google Analytics for Firebase** for app-level analytics;
- **Google Cloud Run and Google Cloud Logging** to host and operate the backend and its logs;
- **Google Secret Manager** to supply backend secrets at runtime; and
- **Neon PostgreSQL** to store account, gameplay, ranking, presence, and backend analytics data.

These providers process information under their own terms and privacy policies. Math Race Live does not currently include advertising, an advertising SDK used to display ads, or Firebase Crashlytics.

## Retention

Account and gameplay information is retained while needed to operate the service and maintain authoritative competition records. The current service does not apply one general fixed deletion period to all active-account and gameplay records.

Backend product-analytics sessions and events are retained until the account is deleted or they are otherwise removed as part of service operations. Operational logs and Firebase Analytics information are retained according to the applicable Google service configuration and policies.

Presence affects the displayed online count only for 45 seconds after a successful refresh. The latest presence timestamp remains in the database until it is replaced, the associated user row is removed, or the authenticated account is deleted. Authenticated account deletion removes the presence record.

## Account deletion

An authenticated user can start deletion from **Profile → Delete account** and confirm the request. Depending on the linked provider, the app may require recent Google or Apple authentication.

After successful deletion:

- the Firebase Authentication user is deleted;
- Firebase, Google, and Apple authentication mappings are removed from our backend;
- the username is removed and becomes available for another eligible user;
- backend product-analytics sessions and events linked to the account are deleted;
- the account's activity-presence record is deleted; and
- the public identity becomes `Deleted Player`.

We retain a pseudonymous internal record and historical participation, answer, scoring, finalized-result, delivery, and answer-validation records to preserve completed rankings, scoring and ledger integrity, idempotency, and security investigations. These retained records no longer contain the old username or authentication-provider mappings.

For 30 days, we retain a SHA-256 hash of the deleted Firebase identifier to prevent a still-valid token from recreating the deleted account. This tombstone does not contain the raw Firebase identifier.

The in-app deletion transaction does not itself erase information already processed by Google Analytics for Firebase. That information remains subject to Google's Analytics controls, retention settings, and policies.

See [ACCOUNT_DELETION.md](ACCOUNT_DELETION.md) for the current deletion procedure. If you cannot access the app, contact [erayustun.dev@gmail.com](mailto:erayustun.dev@gmail.com). Do not send passwords or authentication tokens by email.

## Security

We use measures including verified Firebase tokens, server-authoritative scoring and timing, scoped database access, rate limiting, encrypted HTTPS connections, restricted production credentials, and structured logs that avoid sensitive request content. No service can guarantee absolute security.

## Children and eligibility

Use of Math Race Live is subject to the eligibility requirements in our [Terms and Game Rules](TERMS.md). We do not knowingly ask users to submit their age in the current app.

## Changes to this policy

We may update this Privacy Policy as the product or legal requirements change. We will update the effective date when a revised policy is published. Material changes may also be communicated in the app or through another appropriate channel.

## Contact

Eray ÜSTÜN

[erayustun.dev@gmail.com](mailto:erayustun.dev@gmail.com)
