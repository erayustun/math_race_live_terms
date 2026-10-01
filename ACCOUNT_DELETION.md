# Math Race Live Account Deletion

**Effective date:** October 1, 2026

Math Race Live is operated by Eray ÜSTÜN. This document explains the account-deletion behavior currently implemented in the app.

## Delete an authenticated account in the app

1. Open **Profile**.
2. Select **Delete account**.
3. Read the deletion warning and select **Delete permanently** to confirm.
4. Complete Google or Apple reauthentication if requested.
5. Wait for the app to confirm the deletion and create a fresh anonymous session.

The Delete account action is currently shown for non-anonymous accounts authenticated with Google or Apple. Signing out is not deletion: it leaves the authenticated account, username, scores, and history stored and starts a different anonymous session on the device.

## What is deleted

After a successful in-app deletion:

- the Firebase Authentication user is deleted;
- Firebase, Google, and Apple authentication mappings are removed from the Math Race Live backend;
- the chosen username is removed and becomes available for another eligible user;
- backend product-analytics sessions and events linked to the account are deleted;
- the account's activity-presence record is deleted; and
- the former public identity is replaced with `Deleted Player` in retained public competition records.

Deletion is transactional on the backend. If deletion of the Firebase Authentication user fails, the backend database changes are rolled back so the operation can be retried safely.

## What is retained anonymously

Math Race Live retains the following under a pseudonymous internal record:

- match participation;
- accepted answers and awarded-point transactions;
- question-delivery and answer-attempt validation records;
- finalized match scores, correct counts, and competition ranks; and
- related timestamps and technical integrity fields.

These records are retained to preserve completed match and leaderboard integrity, server-authoritative scoring, duplicate prevention, auditability, and security investigation. They no longer include the old username or Firebase, Google, or Apple identity mappings, and public projections use `Deleted Player`.

Google Analytics for Firebase information is not deleted by the backend account-deletion transaction. It remains subject to Google's Analytics retention settings, controls, and policies and is not used to reconstruct a deleted public game identity.

## Temporary deletion-protection record

For 30 days after deletion, the backend retains a SHA-256 hash of the deleted Firebase identifier. This prevents a previously issued authentication token from recreating the deleted account. The tombstone does not store the raw Firebase identifier and expires after 30 days.

## Temporary guest discard is different

When a user on a temporary anonymous account chooses a Google or Apple provider that already belongs to another Math Race Live account, the app may offer to discard the current guest and switch accounts. If confirmed, the guest's backend user, gameplay, analytics, presence, and authentication mappings are removed before the provider switch. This conflict-resolution flow is not a merge and does not transfer guest points or history to the existing account.

## If you cannot access the app

Contact [erayustun.dev@gmail.com](mailto:erayustun.dev@gmail.com) and state that you need help with account deletion. Do not send a password, Firebase token, Google or Apple credential, or other authentication secret. We will provide the steps supported by the available account and platform tools; no email-only identity-verification procedure is promised here.

For broader information about data handling, see the [Privacy Policy](PRIVACY_POLICY.md).
