<div align="center">

# 💊 MedVision ✨

### 📸 Snap a medicine packet → ✅ confirm → ⏰ get reminded → 📖 track it all

*A cute, accessible medicine tracker for iOS — built for the people who need it most.* 🧓💕

<br/>

![iOS](https://img.shields.io/badge/iOS-SwiftUI-000000?style=for-the-badge&logo=apple&logoColor=white)
![Swift](https://img.shields.io/badge/Swift-F05138?style=for-the-badge&logo=swift&logoColor=white)
![Supabase](https://img.shields.io/badge/Supabase-3ECF8E?style=for-the-badge&logo=supabase&logoColor=white)
![Status](https://img.shields.io/badge/status-early%20build-yellow?style=for-the-badge)

<br/>

<img src="https://user-images.githubusercontent.com/74038190/212284100-561aa473-3905-4a80-b561-0d28506553ee.gif" width="100%" />

</div>

<br/>

## 🌟 What is MedVision?

> **📱 Photograph a medicine packet → confirm the details → set a schedule → never miss a dose.**

MedVision is a **personal medicine tracking app for iOS** 💊. Point your camera at a medicine packet, and it pulls out the name, dosage, and form for you — you just confirm, schedule, and go.

Built **accessibility-first** for the elderly 🧓 and anyone juggling lots of daily meds:

🔤 Large text &nbsp;•&nbsp; 🌗 High contrast &nbsp;•&nbsp; 👆 Minimal taps &nbsp;•&nbsp; ✅ Always confirm before saving

*Personal-use only — no social feeds, no caregiver sharing, no clutter.* 🚫

<br/>

## 🔄 The Core Loop

<div align="center">

📸 **Snap** → ✏️ **Confirm & Edit** → ⏰ **Schedule** → 🔔 **Remind** → ✅ **Mark Taken** → 📖 **History**

</div>

<br/>

## ✨ Features

| | Feature | What it does |
|:--:|:--|:--|
| 📸 | **Packet Recognition** | Capture a packet and extract name, dosage & form via OCR |
| ✅ | **Confirm & Edit** | You review every scan before it saves — nothing is auto-saved |
| ✍️ | **Manual Fallback** | Add or edit meds by hand for damaged packets or failed scans |
| ⏰ | **Scheduling** | Set times & frequency per medicine, including "with food" flags |
| 🔔 | **Smart Reminders** | Local notifications when a dose is due, bundled to avoid spam |
| 📖 | **Dose History** | A timeline of doses taken, skipped, or missed |
| 💡 | **Drug Info** | Look up medicine details through a secure backend proxy |

<br/>

## 📸 Screenshots

> 🖼️ *Drop your screenshots or a demo GIF here!*

<div align="center">

| Today 🗓️ | Scan 📸 | History 📖 |
|:--:|:--:|:--:|
| _`add screenshot`_ | _`add screenshot`_ | _`add screenshot`_ |

</div>

<br/>

## 🛠️ Tech Stack

<div align="center">

| Layer | Technology |
|:--:|:--|
| 📱 **App** | Native iOS — SwiftUI, SwiftData |
| ☁️ **Backend** | Supabase — Auth, Postgres, Storage, RLS, Edge Functions |
| 👁️ **Recognition** | Typhoon OCR (proxied through the backend) |
| 💊 **Drug Info** | Public drug database API (proxied through the backend) |

</div>

<br/>

## 🏗️ Architecture

- 📱 **iOS app** (`MedVision/`) — SwiftUI interface with local SwiftData persistence. Recognition lives behind a single service, so the OCR provider can be swapped without touching the UI.
- ☁️ **Backend** (`backend/`, `supabase/`) — Supabase owns cloud data, auth, and secrets. Edge Functions proxy OCR and drug-info calls so API keys never reach the client, and every row is protected with Row Level Security 🔒.

### 🧩 Data Model

- 💊 **Medicine** — name, dosage, form, photo, notes
- ⏰ **Schedule** — times and frequency for a medicine
- 📖 **DoseEvent** — a dose taken, skipped, or missed, with a timestamp
- 🔍 **RecognitionJob** — an OCR upload with raw text, parsed result & failure reason

<br/>

## 📂 Project Structure

```
MedVision-main/
├── 📱 MedVision/            # iOS app (SwiftUI)
│   ├── App/                # Entry point, onboarding, configuration
│   ├── Features/           # Today, Scan, Medicines, History, Profile
│   ├── Models/             # Medicine, DoseEvent, and supporting types
│   └── Services/           # Recognition and notifications
├── 🛠️ MedVision.xcodeproj/  # Xcode project
├── ☁️ backend/              # Shared logic and unit tests
├── 🗄️ supabase/             # Migrations, Edge Functions, config
└── 📚 docs/                 # Specs and implementation plans
```

<br/>

## 🚦 Status

> 🌱 **Early build**, targeting a demo. The iOS app runs locally with SwiftData while the cloud-backed Supabase backend is being built out.

<br/>

<div align="center">

Made with 💊 + 💕 for the people who need it most

<img src="https://user-images.githubusercontent.com/74038190/212284158-e840e285-664b-44d7-b79b-e264b5e54825.gif" width="400" />

</div>
