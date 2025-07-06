# 🧠 NeuroMirror – The Mood Reflecting Smart Mirror

## 🎯 Project Objective

NeuroMirror is a smart mirror designed to detect the user's emotional state using facial expressions and respond with personalized messages, visual feedback, and wellness activities. The goal is to promote mental well-being, enhance self-awareness, and support daily productivity — all within a compact and portable system.

This project falls under the **Healthcare** category, with a focus on **mental health innovation**. By offering emotion recognition, stress reduction, mood tracking, and basic skin analysis in an offline, privacy-first solution, NeuroMirror addresses the growing need for accessible, technology-based health and wellness tools.

---

## 🧰 Hardware Requirements

| Component              | Description                           
| ---------------------- | ------------------------------------- 
| Raspberry Pi 5         | Main controller                       
| Raspberry Pi Camera    | Facial emotion + skin analysis        
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
* `Flask` – Web dashboard for mood & skin health tracking
* `pyttsx3` – Offline text-to-speech
* `pygame.mixer` – Audio playback
* `matplotlib` – Mood and skin log plotting
* `sqlite3` – Local database for mood and skin logs
* `cvlib` or `TensorFlow/Keras` – Basic skin condition detection (redness, acne, dryness)

---

## 🔄 Core Functionality Flow

1. 👤 User stands in front of the mirror → camera captures facial image
2. 📷 Emotion is detected using `deepface`
3. 🧴 Skin is analyzed for redness, acne, dryness (using trained ML model or image filters)
4. 🖥️ Mirror display updates with:

   * Emoji and mood label
   * Detected skin condition
   * Background color based on mood
   * Personalized message or health tip
5. 🔉 Speaker plays a relevant voice message or music
6. 🌿 If the emotion is negative, system enters **Wellness Mode**
7. 📊 Mood and skin data is stored in SQLite and visualized via Flask

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

## 🧴 Skin Health Detection (New Feature)

### 🔍 How it works

* Captures face using the camera
* Applies basic skin condition filters or ML model
* Detects signs of:

  * Acne
  * Redness/irritation
  * Dry patches

### 💡 Output Example

```
Detected: Mild acne on right cheek. Consider cleansing regularly.
```

* Suggests skincare tips and routines
* Tracks skin condition changes over time

---

## 🌿 Wellness Mode

### 🎯 Trigger

Automatically activated when detected emotion is:

* `sad`, `angry`, `fear`, or `disgust`

### 🔁 Features

* 🧘 Breathing circle animation on screen
* 🔉 Voice-guided relaxation using `pyttsx3`
* 🎵 Lofi or ambient background music
* 📓 Prompt to write a journal entry (text input)

### 🛑 Exit Criteria

* 3 minutes elapsed
* User performs a gesture or clicks exit

---

## 🌐 Flask Web Dashboard

**URL:** `http://localhost:5000`

### 📋 Features

| Section               | Description                                                   |
| --------------------- | ------------------------------------------------------------- |
| 📊 Mood Graph         | 7-day emotion history (line/bar chart using matplotlib)       |
| 📓 Journal Log        | List of daily journal entries with timestamps                 |
| 📸 Photo Log (opt)    | Daily selfie snapshots with detected emotions (optional)      |
| 🖼️ Live Camera Feed  | Live webcam preview to verify camera feed and lighting setup  |
| 🧠 Real-Time Emotion  | Real-time emotion recognition via browser preview (optional)  |
| 💆 Skin Condition Log | Track changes in skin condition over time with image and tips |
| 📤 Export Data        | Option to export mood and skin logs as CSV                    |

---

## 🧩 Optional Enhancements

* 🔒 Privacy mode (face unlock, hide mood logs)
* 🧠 AI-powered affirmation generator
* ⏳ Pomodoro-style productivity timer
* 📅 Monthly mood + skin calendar view
* 🧍 Multi-user profile support with face ID
* 🔔 Mood or skin alert notifications (e.g., recurring irritation or stress)

---

## 🏁 Conclusion

**NeuroMirror** now combines mental wellness and **basic skin health analysis** using AI and computer vision. It empowers individuals to reflect, reset, and monitor both mood and visible skin health—all from a mirror.

This makes it even more impactful in the **Healthcare** category, targeting both emotional and dermatological awareness.

✨ *Reflect your emotions. Recharge your mind. Refresh your skin.*
