# AI Real-time GYM Coach 🏋️

A personal AI fitness trainer that watches you work out through your webcam, counts your reps automatically, and gives you voice coaching after every set — powered by MediaPipe and Groq AI.

**Live App → [realtime-ai-gym-coach-by-mr-rvr.streamlit.app](https://realtime-ai-gym-coach-by-mr-rvr.streamlit.app)**

---

## What it does

You open the app, pick your exercise, set your target sets and reps, and hit Start Workout. Your webcam turns on and the app starts tracking your body in real time. It counts every rep as you move, tracks your sets, and once you finish a set, an AI coach gives you spoken feedback on your performance — like a real trainer would.

No wearables. No manual tracking. Just your camera and your body.

---

## Features

- **Real-time pose detection** using MediaPipe — tracks 33 body landmarks live
- **Automatic rep counting** based on joint angle analysis
- **AI voice coaching** after every set using Groq LLaMA3 + gTTS
- **5 exercises supported** — Squats, Bicep Curls, Push-ups, Shoulder Press, Lunges
- **Set & rep tracking** with a configurable workout plan
- **Workout history** to log and review past sessions
- **Login system** for personalized sessions

---

## Tech Stack

- **Streamlit** + **streamlit-webrtc** — frontend and camera stream
- **MediaPipe Pose** — body landmark detection
- **Groq API (LLaMA3-8B)** — AI coaching messages
- **gTTS** — text to speech
- **OpenCV** — frame processing
- **SQLite** — local workout history
- **Streamlit Cloud** — deployment

---

## Run it locally

```bash
git clone https://github.com/mr-Raghu-veera-reddy/Realtime-Ai-Gym-Coach.git
cd Realtime-Ai-Gym-Coach
python -m venv .venv
.venv\Scripts\activate
pip install -r requirements.txt
```

Create `.streamlit/secrets.toml` and add your Groq key:

```toml
GROQ_API_KEY = "your_key_here"
```

Then run:

```bash
streamlit run main.py
```

---

## Project structure

```
├── main.py
├── core/              # Base exercise class
├── detectors/         # Rep detection logic per exercise
├── services/
│   ├── auth/          # Login
│   ├── coaching/      # Groq LLM + TTS voice pipeline
│   ├── persistence/   # Workout history
│   ├── tracking/      # Rep and set metrics
│   └── vision/        # Video frame processor
├── ml_models/         # MediaPipe pose model
└── static/            # CSS
```

---

Built by **Raghu Veera Reddy** 
[GitHub](https://github.com/mr-Raghu-veera-reddy)