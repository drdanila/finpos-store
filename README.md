# FinPOS — store & releases (public)

**Public home of the FinPOS Android app** — privacy policy, Google Play store assets, and
versioned releases. This repo contains **no source code**; development happens in a separate
**private** repo.

> FinPOS is a privacy-first personal spending tracker: it reads your bank / Google Pay
> notifications **on-device only** and never sends anything anywhere (no internet permission).

## What's here
- **Privacy policy** — published at <https://drdanila.github.io/finpos-store/>
  (source: [`index.html`](index.html) / [`PRIVACY_POLICY.md`](PRIVACY_POLICY.md)).
- **Store listing** — copy + assets in [`store/`](store/): title/descriptions
  ([`listing.md`](store/listing.md)), `icon-512.png`, `feature-graphic.png`,
  `screenshots/`.
- **Releases** — every shipped version is a [GitHub Release](../../releases) with notes and a
  downloadable APK. History in [`CHANGELOG.md`](CHANGELOG.md).

## Install (test build)
Grab the latest APK from [Releases](../../releases/latest), enable "install unknown apps", open it,
and grant **Notification access** when prompted. The Google Play build ships via the Internal
testing track.

## Repos
| Repo | Visibility | Purpose |
|------|-----------|---------|
| **finpos-store** (this one) | Public | Privacy policy, store assets, releases |
| **finpos-dev** | Private | App source code / development |
