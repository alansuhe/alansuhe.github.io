---
docId: healthdash-privacy
fileId: privacy
lang: en
author: Alan
date: '2026-11-19'
title: "Privacy Policy"
description: "Health Dash"
---
{% include lang-selector.md lang=page.lang file=page.fileId langs="en|zh-Hans" titles="English|简体中文" extension=".html" %}

**Effective Date:** `2026-11-19`  
**Developer:** Alan  
**App:** Health Dash (`me.suhe.healthdash`)  
**Contact:** <tosuhe@gmail.com>

Health Dash ("we", "our", or "the App") is built with a **local-first privacy architecture**. We believe your personal and family health records belong strictly to you. This Privacy Policy explains how Health Dash handles your information on iOS and Android.

---

## 1. Local-First Data Storage

All core data you enter into Health Dash is stored **locally on your device** in an on-device SQLite database and secure device storage (`expo-secure-store` / Keychain / Keystore):

- **Profiles:** Display name, biological sex, birth date, and optional blood type.
- **Health Records:** Biomarker observations, measurement dates, units, notes, checkup report metadata (title, facility, date), and custom biomarker definitions.
- **AI Analysis History & Token Ledger:** Saved AI insight summaries and local device token balance records.

We do **not** require account registration, and we do **not** operate a cloud database that stores or syncs your health records.

---

## 2. Optional De-Identified AI Health Insights

Health Dash includes an **optional** AI Health Insights feature. This feature is **strictly user-initiated**—no health data leaves your device unless you explicitly tap to start an AI analysis.

When you request an AI analysis:

1. **On-Device De-Identification:** Before transmitting any request, Health Dash strips personal identifiers. Your profile display name, exact birth date, report facility names, and free-text notes are **not** sent. Only the following de-identified clinical context is transmitted:
   - Age in whole years (calculated on device from birth date)
   - Biological sex and optional blood type
   - Selected biomarker codes, canonical values, units, measurement dates, reference ranges, and status flags
   - Your selected display language (for response localization)
2. **Encrypted Transit & Processing:** The de-identified prompt is transmitted over HTTPS (TLS) through our stateless AI gateway (`ai-gateway.suheapp.org`) to third-party large language model inference providers (such as DeepSeek or Moonshot/Kimi) solely to generate your real-time response.
3. **No User Accounts or Profiling:** Requests are not linked to a user account, email address, phone number, or advertising identifier. Generated insights are saved only on your device.

If you prefer never to transmit any data off your device, simply do not use the AI Health Insights feature; all other tracking, charting, reference evaluation, and backup features work 100% offline.

---

## 3. Backups, Exports & Third-Party Cloud Storage

Health Dash provides user-initiated **Full Backup (JSON)** and **Records Table (CSV)** export and import tools.

- Export files are created locally and handed to your operating system's native share sheet or document picker.
- If you choose to save a backup to **Apple iCloud Drive**, **Google Drive**, or another third-party storage provider, that file is governed by the privacy policy and security controls of your chosen provider.
- Backup files contain your unencrypted health records so they can be restored across devices. Please store them in a trusted, password-protected location.

---

## 4. No Ads, No Tracking, No Data Selling

- Health Dash contains **no third-party advertising SDKs**.
- Health Dash contains **no third-party analytics, behavioral tracking, or cross-app tracking SDKs**.
- We **never sell, rent, or trade** your health or personal data.

---

## 5. Data Retention & Deletion

Because your data is stored locally on your device, you have full and immediate control over it:

- **Delete individual items or profiles:** You can delete any measurement, report, AI insight, or entire profile inside the App at any time. Deletion permanently removes those records from the local SQLite database.
- **Delete all app data:** Uninstalling Health Dash removes the local database from your device. (Any backup files you manually exported to Files, iCloud Drive, or external storage must be deleted separately by you.)

---

## 6. Children's Privacy

Health Dash supports multi-profile family tracking (for example, a parent or guardian recording a child's pediatric checkups on the parent's own device). The App is not directed to children under 13 (or the applicable age of digital consent in your jurisdiction) for independent use, and we do not knowingly collect personal information from children on any server.

---

## 7. Security

We protect your data by minimizing collection and keeping records on your device. We strongly recommend enabling your device's passcode, Face ID / Touch ID, or biometric lock to protect locally stored health information.

---

## 8. Changes to This Privacy Policy

We may update this Privacy Policy from time to time (for example, if we add optional cloud sync or new on-device features in future versions). We will post the updated policy with a revised "Effective Date" at [Privacy Policy](https://alansuhe.github.io/apps/healthdash/privacy.en.html).

---

## 9. Contact Us

If you have any questions or privacy requests regarding Health Dash, please contact us at:

- **Email:** <tosuhe@gmail.com> / <ariessuhe@163.com>
- **Website:** [https://alansuhe.github.io](https://alansuhe.github.io)
