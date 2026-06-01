# Changelog

All notable releases of the FinPOS app. Each version is also published as a
[GitHub Release](../../releases) with a downloadable APK.

The format is based on [Keep a Changelog](https://keepachangelog.com/);
this project uses [Semantic Versioning](https://semver.org/).

## [0.3.0] — 2026-06-01
More banks, a clearer Banks tab, and a credit-limit fix.

### Added
- **UkrSibbank** is now recognised.
- Each bank in the Banks tab gets a **colour badge** for quick recognition.

### Changed
- **Google Pay is no longer shown as a bank** (it isn't an account — it's still used behind the
  scenes to confirm matching purchases).

### Fixed
- A **credit-limit change** notification ("your credit limit was changed to …") was being counted as
  a spend — it's now correctly ignored.

[0.3.0]: https://github.com/drdanila/finpos-store/releases/tag/v0.3.0

## [0.2.0] — 2026-06-01
See each bank on its own: what came in, what went out, and how much is there now.

### Added
- **Banks tab.** A new tab shows a card per bank with **In** (money received), **Out** (money spent),
  and **Balance now** — the latest balance the bank reported in its notifications (Privat24, ПУМБ and
  monobank all included; Google Pay has no balance, so it shows "—").

### Fixed
- **Money received from a person now counts as income** (monobank "From: …" transfers were being
  counted as spending).

> Note: balances and the "received" fix apply to transactions captured from this version on — older
> entries show "—" for balance until their next notification.

[0.2.0]: https://github.com/drdanila/finpos-store/releases/tag/v0.2.0

## [0.1.3] — 2026-06-01
Real card-to-card transfers between your own cards now show as one entry.

### Fixed
- **Transfer between your own cards = one neutral entry.** A transfer posts two notifications
  (money leaving one card, arriving on another); these are now merged into a single "Transfer" that
  counts as neither spending nor income — calibrated from a real on-device transfer. Previously both
  halves were counted as spending, inflating your total.

> Note: entries captured before this update keep their old label — tap **Clear database** once (or
> just make a new transfer) to see the corrected behavior.

[0.1.3]: https://github.com/drdanila/finpos-store/releases/tag/v0.1.3

## [0.1.2] — 2026-06-01
Tells spending apart from income, and stops counting transfers.

### Added
- **Spending vs income.** Money you receive (top-ups, salary, refunds) no longer counts as
  spending — the summary now shows **Spent** and a separate **Received** total, and each row is
  signed (− spending, + income, green).

### Fixed
- **Card-to-card transfers between your own cards** no longer appear twice or inflate your spending —
  the debit and credit are merged into a single neutral "Transfer" entry, counted as neither.

[0.1.2]: https://github.com/drdanila/finpos-store/releases/tag/v0.1.2

## [0.1.1] — 2026-06-01
Real-device calibration fixes.

### Fixed
- **ПУМБ transactions now captured.** ПУМБ's app uses a different package than expected, so its
  notifications were ignored — corrected, and the "Купівля" format is parsed (the purchase amount,
  never the available-balance line).
- **No more duplicate rows / inflated total.** One purchase now produces exactly one transaction:
  a notification re-delivered by the same source is treated as a duplicate, and a bank purchase
  with its matching Google Pay notification collapses into a single "Confirmed by Google Pay" row.

[0.1.1]: https://github.com/drdanila/finpos-store/releases/tag/v0.1.1

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
