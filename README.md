<div align="center">

<br/>

### `[ PROJECT Z ]`
*codename · final name TBD*

**One client. Open protocol. Your data, your choice.**

<br/>

[![License: AGPL v3](https://img.shields.io/badge/License-AGPL_v3-blue.svg)](https://www.gnu.org/licenses/agpl-3.0)
[![Status](https://img.shields.io/badge/Status-Design_Phase-yellow)]()
[![Built with](https://img.shields.io/badge/Built_with-Go_%7C_Tauri_%7C_TypeScript-informational)]()
[![Protocol](https://img.shields.io/badge/Protocol-Open-brightgreen)]()
[![Made in](https://img.shields.io/badge/Made_in-Israel_🇮🇱-blue)]()

<br/>

[English](#english) · [Русский](README_RU.md)

<br/>

</div>

---

<a name="english"></a>

## What is Project Z?

Project Z is an **open-source communication platform** built on an **open protocol** — designed to be everything Discord promised but never fully delivered.

We are not trying to be *"Discord but faster."*

We are building a platform that **stands for something**.

> *The right to communicate freely, privately, and without fear — regardless of which government you live under.*

---

## Why?

Discord has become bloated, privacy-invasive, and increasingly bows to political and governmental pressure.

Existing alternatives (Matrix, Revolt, Element) either sacrifice UX for openness, or openness for UX. **None of them get both right.**

Project Z is built on a simple belief: you shouldn't have to choose between freedom and a great experience.

---

## Core Values

| Value | What it means |
|---|---|
| 🗣️ **Real freedom of speech** | No political censorship. Red lines based on universal human ethics, not trending politics |
| 🔍 **Structural transparency** | Political content, paid promotion, and bots are always visibly labeled — no hidden influence |
| 🔐 **Your data belongs to you** | Full deletion rights. Personal audit log — you always know what the system has done with your data |
| 🛡️ **No surrender** | We cooperate with law enforcement on real crimes. We do not capitulate to political pressure from any government or entity |
| 📱 **One client, everywhere** | No downloading a new app every time you join a community. One client, one experience |

---

## Architecture

```
┌─────────────────────────────────────────────┐
│           Cloud Registry (global)            │
│  • User identities & profiles                │
│  • Self Hosted server registry               │
│  • Red line enforcement only                 │
└──────────────┬──────────────────────────────┘
               │
       ┌───────┴────────┐
       │                │
┌──────▼──────┐  ┌──────▼──────────────────┐
│   Cloud     │  │      Self Hosted         │
│   Server    │  │      Server              │
│             │  │  VPS / Docker /          │
│  Data at    │  │  Home / Ready Package    │
│  Project Z  │  │                          │
└─────────────┘  │  Data at owner           │
                 │  Full responsibility      │
                 └──────────────────────────┘

Communication Layer:
  Text     ──► Custom open protocol
  Voice  ─┐
  Video  ─┤──► WebTransport P2P
  Stream ─┘    ├─ 2 users    → Direct E2E P2P
               ├─ 3–8 users  → E2E Mesh
               └─ 9+ users   → SFU (encrypted, server-blind)
```

---

## Key Features

<details>
<summary><b>🖥️ Three display modes</b></summary>
<br/>

- **Full Mode** — standard full-window experience
- **Sidebar Mode** — slides out from the side, stays accessible
- **Mini Mode** — inspired by Winamp/AIMP, always on screen while you game, work, or browse

No more dragging Discord between screens.

</details>

<details>
<summary><b>🔒 Real end-to-end encryption</b></summary>
<br/>

- DMs and private channels → full E2E encryption (RSA-2048 + AES-256)
- Public channels → transport encryption (TLS 1.3) with full audit trail
- Voice/video → SRTP, server-blind even on SFU

</details>

<details>
<summary><b>🌍 Self Hosted with Data Residency</b></summary>
<br/>

Run your own server in your own country. Comply with local data laws without depending on us.

- Works identically to Cloud servers — same features, same client
- Registered in global Registry so other users can find it
- You own your data, you are responsible for it

</details>

<details>
<summary><b>🔓 Open Protocol</b></summary>
<br/>

Fully documented. Anyone can build a compatible client or server.

The official client will always be the best — like Chrome for HTTP.

Open protocol = practically impossible to block. No single point of failure.

</details>

<details>
<summary><b>📋 Personal Audit Log</b></summary>
<br/>

Every system action related to your account is logged and visible to you. Always. Including actions by the platform itself.

</details>

<details>
<summary><b>🤖 Bot transparency</b></summary>
<br/>

Every bot must display its developer, purpose, and exact permissions. Bots cannot impersonate humans — ever.

All bot actions are logged in your personal audit log.

</details>

<details>
<summary><b>🎨 MySpace-inspired personalization</b></summary>
<br/>

Profiles and server pages can look unique through CSS Sandboxed — without threatening client stability.

</details>

---

## Tech Stack

| Component | Technology |
|---|---|
| Server | Go |
| Client | Tauri + React + TypeScript |
| Voice / Video | WebTransport P2P + SRTP |
| Encryption | RSA-2048 + AES-256 + TLS 1.3 |
| Protocol | Custom open protocol |

---

## Moderation Policy

We are not a police force. But we are responsible citizens.

```
Red lines (absolute):
  ✗  Content involving minors (under 18)
  ✗  Terrorism planning
  ✗  Human trafficking

On violation:
  → Evidence snapshot (encrypted)
  → Filed with relevant authorities (Interpol, FBI, Europol, local police)
  → Evidence handed over — their responsibility from there

Symmetry principle (applies to everyone):
  ✓  Criminals               → removed
  ✓  Government without court order → refused
  ✓  Political pressure      → refused
  ✓  Corporate pressure      → refused
```

---

## Project Status

**Phase: Design & Architecture**

- [x] Vision and core values defined
- [x] System architecture designed
- [x] Protocol specification designed
- [x] Encryption model designed
- [ ] Protocol documentation
- [ ] Proof of concept
- [ ] First working prototype

---

## Contributing

The project is not yet open for code contributions, but we welcome:

- 🏗️ Architecture feedback
- 📐 Protocol design input
- 🔐 Security review of our approach

Open an issue or start a discussion.

---

## Made in Israel 🇮🇱

An Israeli company. A universal product.

Like Waze, Mobileye, and Check Point — built here, used everywhere.

---

## License

**GNU Affero General Public License v3.0**

Free forever, for everyone. Anyone who uses this code — including as a hosted service — must publish their changes.

See [LICENSE](LICENSE) for details.

---

<div align="center">

*"We came to be a free people in our land."*
*We came to be free users on our platform.*

<br/>

[English](#english) · [Русский](README_RU.md)

</div>
