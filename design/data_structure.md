# Data Structure - Ramadan 365

## 📊 Local Database Schema (SQLite/Hive)

### 1. `worship_actions` (Static/Seed Data)
| Field | Type | Description |
| :--- | :--- | :--- |
| `id` | INT (PK) | Unique ID |
| `type` | STRING | 'dhikr', 'dua', 'ayah', 'deed' |
| `content_ar` | TEXT | Arabic text (optional) |
| `content_en` | TEXT | English translation/instruction |
| `audio_path` | STRING | Path to local asset |
| `day_of_year` | INT | 1 to 365 |

### 2. `user_progress` (Dynamic Data)
| Field | Type | Description |
| :--- | :--- | :--- |
| `date` | DATE (PK) | The specific day |
| `action_id` | INT | FK to `worship_actions` |
| `is_completed` | BOOLEAN | Completion status |
| `completion_time` | DATETIME | When it was done |

### 3. `monthly_challenges` (Static/Seed Data)
| Field | Type | Description |
| :--- | :--- | :--- |
| `id` | INT (PK) | Unique ID |
| `month_index` | INT | 1 (Muharram) to 12 (Dhul-Hijjah) |
| `title` | STRING | Challenge name |
| `description` | TEXT | Short task description |

### 4. `user_settings` (KeyValue/Preferences)
| Key | Type | Default |
| :--- | :--- | :--- |
| `daily_reminder_time` | TIME | 08:00 AM |
| `fasting_reminders_enabled`| BOOLEAN | TRUE |
| `silent_mode` | BOOLEAN | FALSE |
| `theme_mode` | STRING | 'system' |

## 📁 File Structure for Assets
```text
assets/
  audio/
    dhikr_01.mp3
    dua_01.mp3
  data/
    content_v1.json  <-- Initial seed for 365 days
  images/
    glow_animations/
    icons/
```
