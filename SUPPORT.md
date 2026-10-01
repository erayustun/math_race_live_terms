# Math Race Live Support

**Effective date:** October 1, 2026

Math Race Live is operated by Eray ÜSTÜN.

For support, email [erayustun.dev@gmail.com](mailto:erayustun.dev@gmail.com). Please describe the device platform, app version, what you expected, and what happened. Do not send your password, Firebase token, Google or Apple credential, or other authentication secret.

## Sign-in help

- The app starts with an anonymous account automatically.
- On Android, an anonymous user can continue with Google. On iOS, an anonymous user can continue with Apple or Google.
- Linking a provider for the first time preserves the current account and its game history.
- If the selected provider already belongs to another Math Race Live account, the app asks whether to keep the current guest or discard it and switch. The two accounts are not merged, and guest points are not transferred.
- Signing out starts a fresh anonymous account on the device. It does not delete the signed-out account. Sign in again with the same provider to return to that account.
- Anonymous accounts may be unrecoverable after uninstalling the app, clearing app data, or switching away from the guest.

If sign-in fails, confirm that the device is online, that Google Play services or Apple sign-in is available, and that the intended provider account is selected. Then retry from Profile.

## Connectivity and synchronization

Matches are synchronized globally and controlled by server time. Joining during an active round may mean entering the current question sequence late. A weak or interrupted connection can delay question delivery, prevent an answer from reaching the server before the deadline, or delay results.

If LIVE remains unable to synchronize:

1. Confirm the device has working internet access.
2. Leave the app in the foreground briefly so it can reconnect at the next authoritative boundary.
3. Close and reopen the app if the problem continues.
4. Contact support with the approximate time, platform, app version, and the visible error message.

## Usernames

Only Google- or Apple-authenticated users can choose a username. It must be 3–20 characters, start with a letter, and contain only ASCII letters, numbers, or underscore. Usernames are case-insensitively unique.

If a username is reported as taken, choose another one. Changing a username releases the old username under the current product rules. Users without a username appear as a stable `Player####` fallback.

## Match results and the daily leaderboard

Scores, ranks, and leaderboards come from authoritative backend records. A result may take a short time to finalize after gameplay ends. Players with equal scores may share a competition rank.

The daily leaderboard and match results are different views. Match results apply to one synchronized match; the daily leaderboard aggregates qualifying authoritative gameplay records for the current daily period.

When reporting an issue, do not send answer tokens or authentication credentials. A screenshot and the approximate match time are usually more useful.

## Account deletion

Authenticated users can choose **Profile → Delete account**, review the warning, and confirm. Google or Apple may require verification before deletion. Deletion is different from signing out and cannot be undone.

For details about what is deleted and what anonymized competition records remain, see [ACCOUNT_DELETION.md](ACCOUNT_DELETION.md) and [PRIVACY_POLICY.md](PRIVACY_POLICY.md).

If you cannot access the app to start deletion, contact [erayustun.dev@gmail.com](mailto:erayustun.dev@gmail.com). Explain that you need account-deletion assistance, but do not email passwords or tokens. We will respond with the steps that are appropriate to the account and available platform tools; this document does not promise an unimplemented email-only verification process.

## Legal documents

- [Privacy Policy](PRIVACY_POLICY.md)
- [Terms and Game Rules](TERMS.md)
- [Account Deletion](ACCOUNT_DELETION.md)
