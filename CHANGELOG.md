# Changelog

All notable releases of the FinPOS app. Each version is also published as a
[GitHub Release](../../releases) with a downloadable APK.

The format is based on [Keep a Changelog](https://keepachangelog.com/);
this project uses [Semantic Versioning](https://semver.org/).

## [0.1.0] — 2026-06-01
First test release (Google Play **Internal testing** / sideload).

### Added
- Reads bank / Google Pay notifications on-device (monobank, Privat24 / ПриватБанк, ПУМБ,
  Google Pay / Wallet) and parses each transaction (amount, currency, merchant, masked card, time).
- Automatic **spending categories** (Groceries, Restaurants, Transport, Subscriptions, Shopping,
  Health, …) with a spending-summary card (total + proportion bar + per-category breakdown).
- **Dedup** between a bank charge and its Google Pay twin (Possible / Confirmed match).
- **Raw log** of captured notifications for transparency.
- "Clear database" to wipe all local data.

### Privacy
- No `INTERNET` permission, no networking, no analytics, `allowBackup="false"` — all data stays
  on-device. (Verified on the release build via `aapt dump permissions`.)

[0.1.0]: https://github.com/drdanila/finpos-store/releases/tag/v0.1.0
