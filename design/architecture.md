# App Architecture - Ramadan 365

## 🏗️ Technical Stack
To meet the requirements of being lightweight, scalable, and offline-first:

- **Framework**: **Flutter** (Primary recommendation for high-quality UI/UX and easy scaling to iOS).
- **Local Database**: **SQLite (via sqflite)** or **Hive** (NoSQL, extremely fast for offline-first).
- **State Management**: **Riverpod** (Robust, testable, and clean).
- **Storage**: **SharedPreferences** for simple settings (theme, notifications).
- **Audio**: **just_audio** for micro-content audio clips.
- **Background Tasks**: **workmanager** for gentle fasting reminders and daily content refresh.

## 🏛️ Layered Architecture (Clean Architecture Lite)
Given the app's simplicity, we will use a "Lite" version of Clean Architecture to keep it maintainable without over-engineering.

### 1. Presentation Layer (UI)
- **Screens**: Main (Home), Monthly Challenges, Settings.
- **Widgets**: DailyCard, FastingReminder, StreakGlow.
- **Animations**: Rive (for the "growing light" effect) or standard Flutter Animations.

### 2. Domain Layer (Business Logic)
- **Models**: `WorshipAction`, `MonthlyChallenge`, `FastingDay`, `UserProgress`.
- **Use Cases**: `CompleteDailyWorship`, `GetNextChallenge`, `ToggleFastingReminder`.

### 3. Data Layer (Repository & Sources)
- **Repositories**: `WorshipRepository`, `ProgressRepository`.
- **Sources**: 
  - `LocalDataSource`: SQLite/Hive for offline data.
  - `AssetDataSource`: Bundled JSON for micro-content (Initial 365 days of content).

## 📴 Offline-First Strategy
- All core micro-content (365 days of worship) is bundled within the app assets.
- User progress is saved locally immediately.
- Syncing (optional/future) would be a background task, but the core experience never requires internet.

## 📦 Size Optimization
- SVG for all icons and illustrations.
- Compressed OGG/MP3 for optional audio.
- No heavy external libraries.
- Target APK size: ~15-20MB.
