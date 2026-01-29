# Moni Extension — Security & Privacy

Moni Extension is an open-source browser extension that overlays analytics and trading tools on supported websites to help users evaluate crypto projects and social signals. This README documents security and privacy practices for users, auditors, and contributors.

---

## Table of contents

- [Quick summary](#quick-summary)
- [Installation](#installation)
- [Permissions](#permissions)
- [What we never do](#what-we-never-do)
- [Client architecture](#client-architecture)
- [Server-side features & data storage](#server-side-features--data-storage)
- [Contacts](#contacts)

---

## Quick summary

- **Privacy-first by design.** We collect and transmit only the minimum data required for features you enable.
- **Client-side processing.** Sensitive operations (including anything related to private keys) are performed locally in your browser where possible.
- **Open and auditable.** Source code is public; we publish release bundles and instructions to run builds.
- **Clear reporting channels.** We maintain a dedicated security contact and a vulnerability disclosure process.

---

## **Installation**

**From Chrome Web Store (Recommended)**

1. Visit [extension.getmoni.io](https://extension.getmoni.io/)
2. Click "Download now"

**From Source (For Developers)**

1. Open chrome://extensions/
2. Enable "Developer mode"
3. Click "Load unpacked"

## Permissions

Moni Extension requests the smallest set of browser permissions required for its features. Typical permissions and their purpose:

| Permission       | Purpose                                                                                                      |
|------------------|--------------------------------------------------------------------------------------------------------------|
| `storage`        | To store user's authorization data and settings                                                              |
| `sidePanel`      | Provide quick access panel without opening a new tab                                                         |
| `identity`       | Sign in with Google in order to securely verify the user’s identity and link it to an account in our service |
| `webNavigation`  | To update injected UI depends on navigation                                                                  |
| `system.display` | To adjust the popup’s display position                                                                       |
| `tabs`           | For seamless UI updates on injected website                                                                  |

We follow the **principle of least privilege**: permissions are requested only when the feature that needs them is enabled.

---

## What we *never* do

- **Store private keys or seed phrases.** Moni Extension is not a wallet and never stores your private keys on the client or our servers. Transaction signing are handled by audited third-party gateway.
- **Read clipboard contents or monitor arbitrary form input.** We only accept numeric inputs you explicitly provide for trading actions (amounts, percentages).
- **Run mining or hidden processes.** The extension contains no background miner or cryptomining code.
- **Collect full browsing history.** Only minimal context (e.g. the current URL when a feature is active) is accessed and only for features that require it.

---

## Client architecture

- The extension is implemented to run most logic client-side to minimize data sent to servers.
- We follow Manifest V3 (MV3) and rely on vetted third-party libraries.
- We publish release bundles (the built artifacts uploaded to the Chrome Web Store) and provide instructions so independent auditors can reproduce the build from the source tree.

We publish the release checksum alongside each tagged release in the `releases` section on GitHub. Auditors should verify that the checksum of the published bundle matches the checksum in the release notes and that the bundle contents are consistent with the source code.

---

## Server-side features & data storage

- Role-based access control for staff and admin operations.
- Audit logging of privileged operations.
- Encrypted backups and recovery testing.
- Transactions signing processing is performed by certified providers — we do not store your private keys.
---

## Contacts

If you have suggestions for improvements, write to [**Echo**](https://t.me/echo0x) or use the support channel on the Chrome Web Store.