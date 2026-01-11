# Optional AI Logic (Privacy-First) - Ramadan 365

## 🧠 On-Device Intelligence
To maintain the "Lightweight" and "Minimal Permissions" goals, we avoid cloud-based AI. Instead, we use simple on-device heuristics and optionally **TensorFlow Lite** or **ML Kit** for more advanced features if needed.

### 1. Adaptive Scheduling (The "Gentle Reminder" AI)
- **Goal**: Find the perfect time to remind the user without being intrusive.
- **Logic**: 
  - The app tracks (locally) when the user usually completes their daily action.
  - If the user consistently completes it at 7:00 AM, the AI shifts the notification from the default 8:00 AM to 6:45 AM.
  - If the user misses a few days, the AI suggests a different time: *"Perhaps an evening moment of peace would suit you better? 🌙"*

### 2. Contextual Worship Suggestions
- **Goal**: Match the worship to the user's current environment.
- **Logic**:
  - **Time of Day**: Morning (Adhkar), Noon (Gratitude), Night (Forgiveness/Reflection).
  - **Consistency Level**: If a user is on a long "Glow" streak, the AI might suggest a slightly more challenging Monthly Task. If they are struggling, it reverts to the simplest 10-second Dhikr.

### 3. Sentiment-Aware Messages
- **Goal**: Provide encouraging feedback.
- **Logic**:
  - Based on the time taken to complete or the frequency of "listening" to audio, the app selects different encouraging messages.
  - *Example*: User listens to audio 3 times -> *"May this peace stay in your heart all day 🤍"*

## 🛡️ Privacy Guarantee
- **No Data Collection**: All "learning" stays in the app's local storage.
- **No Cloud Processing**: No API calls to LLMs (OpenAI, etc.) to ensure 100% offline capability and zero data leaks.
- **User Control**: AI features can be toggled off in settings, reverting to fixed schedules.
