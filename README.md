# 🧠 NeuroMirror – The Mood Reflecting Smart Mirror

## 🎯 Project Objective

NeuroMirror is a smart mirror designed to detect the user's emotional state using facial expressions and respond with personalized messages, visual feedback, and wellness activities. The goal is to promote mental well-being, enhance self-awareness, and support daily productivity — all within a compact and portable system.

---

## 🧰 Hardware Requirements

| Component              | Description                           
| ---------------------- | ------------------------------------- 
| Raspberry Pi 5         | Main controller                       
| Raspberry Pi Camera    | Facial emotion recognition            
| LCD Display (HDMI/DPI) | Screen behind the mirror              
| Two-way Acrylic Mirror | Reflective surface over LCD display   
| Speakers (3.5mm/USB)   | Audio output for voice/music playback 
| SD Card (16GB+)        | OS and project files                  
| Power Supply (5V 3A)   | For Raspberry Pi                     
| Frame (Wood/Plastic)   | Housing for the mirror unit           

---

## 🧪 Software & Libraries

**Platform:** Raspberry Pi OS (Lite/Full)

**Language:** Python 3

**Libraries Used:**

* `OpenCV` – Camera input and image processing
* `deepface` – Facial emotion recognition
* `Flask` – Web dashboard for mood tracking
* `pyttsx3` – Offline text-to-speech
* `pygame.mixer` – Audio playback
* `matplotlib` – Mood graph plotting
* `sqlite3` – Local database for mood logs

---

## 🔄 Core Functionality Flow

1. 👤 User stands in front of the mirror → camera captures facial image
2. 📷 Emotion is detected using `deepface`
3. 🖥️ Mirror display updates with:

   * Emoji and mood label
   * Matching background color
   * Personalized suggestion or quote
4. 🔉 Speaker plays a relevant voice message or music
5. 🌿 If the emotion is negative, system enters **Wellness Mode**
6. 📊 Mood data is stored in SQLite and visualized via Flask

---

## 🌈 Emotion-to-Response Mapping

| Emotion         | Mirror Background | Response                                  |
| --------------- | ----------------- | ----------------------------------------- |
| 😊 Happy        | Green/Yellow      | Cheerful quote + productivity tip         |
| 😢 Sad          | Blue              | Breathing animation + calming music       |
| 😠 Angry        | Red/Orange        | Voice-guided deep breathing + soft music  |
| 😐 Neutral      | Grey/White        | "Would you like a focus tip for the day?" |
| 😨 Fear/Disgust | Purple            | Comfort suggestion + journal option       |

---

## 🌿 Wellness Mode

### 🎯 Trigger

Automatically activated when detected emotion is:

* `sad`, `angry`, `fear`, or `disgust`

### 🔁 Features

* 🧘 Breathing circle animation on screen
* 🔉 Voice-guided relaxation using `pyttsx3`
* 🎵 Lofi or ambient background music
* 

### 🛑 Exit Criteria

* 3 minutes elapsed
* User performs a gesture or clicks exit

---

## 🖼 Mirror Display UI Design

```
+---------------------------------------------------+
|    🕒 12:42 PM    ☁️ 32°C       😢 Sad             |
|                                                   |
|     "You seem down today. Let’s take a deep       |
|       breath together..."                         |
|                                                   |
|     🧘 [  Breathing Circle Animation  ]            |
|                                                   |
|     🎵 Now Playing: Calm Rain Sounds               |
|                                                   |
|   
+---------------------------------------------------+
```

---

## 🌐 Flask Web Dashboard

**URL:** `http://localhost:5000`

### 📋 Features

| Section              | Description                                                  |
| -------------------- | ------------------------------------------------------------ |
| 📊 Mood Graph        | 7-day emotion history (line/bar chart using matplotlib)      |
| 📓 Journal Log       | List of daily journal entries with timestamps                |
| 📸 Photo Log (opt)   | Daily selfie snapshots with detected emotions (optional)     |
| 🖼️ Live Camera Feed | Live webcam preview to verify camera feed and lighting setup |
| 🧠 Real-Time Emotion | Real-time emotion recognition via browser preview (optional) |
|          |

---

## 🗂 Folder Structure

```
NeuroMirror/
├── main.py
├── detector/
│   └── face.py
├── ui/
│   └── display.py
│   └── breathing.py
├── flask_app/
│   └── app.py
│   └── templates/
│   └── static/
├── audio/
│   └── lofi.mp3
├── data/
│   └── mood_log.db
└── assets/
    └── icons/, quotes.json
```

---

## 🛠 Assembly Tips

* Secure LCD in a wooden or plastic frame
* Place the acrylic mirror over the display
* Mount camera behind a tinted area or small cut-out
* Position speakers behind or to the side
* Set app to auto-run on boot using `~/.bashrc` or `systemd`

---

## 🧩 Optional Enhancements

* 🔒 Privacy mode (face unlock, hide mood logs)
* 🧠 AI-powered affirmation generator
* ⏳ Pomodoro-style productivity timer
* 📅 Monthly mood calendar view
* 🧍 Multi-user profile support with face ID
* 🔔 Mood alert notifications (e.g., multiple sad days)

---

## 📽 Presentation Tips

* ✅ Live demo of real-time emotion recognition and mirror display
* 📊 Highlight 7-day mood tracking on Flask dashboard
* 🎤 Explain impact: “Affordable, offline wellness tech for students, elderly, and remote users”
* 🚀 Closing pitch: “NeuroMirror is not just a mirror. It's your mental wellness companion.”

---

## 🏁 Conclusion

**NeuroMirror** merges AI, emotional intelligence, and smart technology into a single reflective interface. It’s affordable, offline-capable, privacy-friendly, and purpose-built to support mental wellness in real-world scenarios — from classrooms to homes.

✨ *Reflect your emotions. Recharge your mind.*
