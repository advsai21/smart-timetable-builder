# 📅 Smart Timetable Assistant AI Agent

A conversational AI-powered timetable scheduler built with **Groq API** (LLaMA 3.3 70B) and **Gradio**, designed to run on Google Colab.

## 🚀 Features

- **Natural language scheduling** — just describe your event, the AI extracts title, start time, and end time automatically
- **Conflict detection** — prevents overlapping events on the same date
- **Live timetable dashboard** — real-time table view that updates after every action
- **Persistent local storage** — events saved to a JSON file within the Colab session
- **One-click reset** — clear all scheduled events instantly

## 🛠️ Tech Stack

| Layer | Tool |
|---|---|
| LLM Backend | Groq API — `llama-3.3-70b-versatile` |
| UI | Gradio (`gr.Blocks` with Soft theme) |
| Storage | Local JSON (`groq_calendar_db.json`) |
| Runtime | Google Colab |

## ⚙️ Setup & Usage

### 1. Add your Groq API Key to Colab Secrets

In Colab, click the 🔑 **key icon** in the left sidebar and add:

```
Name:  GROQPROJ_API_KEY
Value: your_groq_api_key_here
```

Get a free key at [console.groq.com](https://console.groq.com).

### 2. Open in Colab

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/)

Upload `smart_timetable_aiagent.ipynb` and run all cells.

### 3. Install dependencies

The notebook handles this automatically:

```bash
pip install gradio groq
```

### 4. Use the app

1. Pick a **date** from the date picker
2. Type a natural language instruction, e.g.:
   - *"Schedule an AI Agent Lab session from 14:00 to 15:30"*
   - *"Add a Math lecture at 9am to 10am"*
   - *"Book a project review meeting from 3pm to 4pm"*
3. Click **Submit to Agent** — the AI parses your input and adds the event
4. The timetable dashboard updates live on the right

## 📁 Project Structure

```
├── smart_timetable_aiagent.ipynb   # Main Colab notebook
├── smart_timetable_agent.py        # Standalone Python script
├── README.md                       # This file
```

> **Note:** `groq_calendar_db.json` is generated at runtime and is not committed to the repo.

## 🔒 Security

- API key is read from **Colab Secrets** (never hardcoded)
- No data is sent to external servers beyond the Groq API call

## 📌 Known Limitations

- Storage is session-scoped — data resets when the Colab runtime restarts
- Designed for single-user use within a Colab environment
- Requires a valid Groq API key with access to `llama-3.3-70b-versatile`

## 🧑‍💻 Author

Built by **NotPoet** — [grey.sketches.ink](https://instagram.com/grey.sketches.ink)
