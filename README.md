
---
title: AlterEgo
emoji: 🤖
colorFrom: blue
colorTo: purple
sdk: gradio
app_file: app.py
pinned: false
---

# 🤖 AlterEgo

AlterEgo is a conversational AI designed to act as a digital twin. Built using **Gradio** and **OpenAI**, this application serves as an intelligent, interactive portfolio that can discuss my career, background, skills, and experience with potential clients, employers, or visitors.

Live Demo: [Hugging Face Spaces](https://huggingface.co/spaces/LordTesla/alterEgo)

## ✨ Features

* **Context-Aware Persona:** Ingests context from a personal PDF (`me/me.pdf`) and a text summary (`me/summary.txt`) to accurately represent professional background and skills.
* **OpenAI Function Calling:** The AI is equipped with custom tools to handle specific interactions dynamically:
  * 📥 `record_user_details`: Automatically captures a visitor's name, email, and notes if they express interest in getting in touch, steering the conversation toward email contact.
  * ❓ `record_unknown_question`: Logs any questions the AI is unable to answer to ensure gaps in knowledge are tracked.
* **Real-Time Push Notifications:** Integrates with the **Pushover API** to instantly send mobile alerts whenever a user leaves their contact details or asks an unknown question.

## 🛠️ Tech Stack

* **Interface:** [Gradio](https://gradio.app/)
* **AI/LLM:** [OpenAI](https://openai.com/) (`gpt-4o-mini`)
* **Document Parsing:** `pypdf`
* **Notifications:** Pushover API (`requests`)
* **Environment Management:** `python-dotenv`

## 📂 Project Structure

```text
AlterEgo/
├── app.py                # Main application script containing UI, AI logic, and tools
├── requirements.txt      # Python dependencies for Hugging Face/local deployment
├── README.md             # Project documentation and Hugging Face YAML metadata
└── me/
    ├── me.pdf            # PDF document (e.g., Resume/LinkedIn profile)
    └── summary.txt       # Text file containing a brief background summary
```

## 🚀 Running Locally

### 1. Clone the repository
```bash
git clone [https://github.com/DhruvJain7/AlterEgo.git](https://github.com/DhruvJain7/AlterEgo.git)
cd AlterEgo
```

### 2. Set up a virtual environment (Recommended)
```bash
python3 -m venv venv
source venv/bin/activate  # On Windows use `venv\Scripts\activate`
```

### 3. Install dependencies
```bash
pip install -r requirements.txt
```

### 4. Configure Environment Variables
Create a `.env` file in the root directory and add your API keys:
```env
OPENAI_API_KEY=sk-your-openai-api-key
PUSHOVER_USER=your-pushover-user-key
PUSHOVER_TOKEN=your-pushover-app-token
```

### 5. Add your context files
Ensure you have the following files present in the `me/` directory to give the AI context:
* `me/me.pdf`
* `me/summary.txt`

### 6. Run the application
```bash
python3 app.py
```
The application will launch locally at `http://127.0.0.1:7860`.

## ☁️ Deployment

This app is natively configured to be deployed on **Hugging Face Spaces**. 
1. Create a Gradio Space on Hugging Face.
2. Add `OPENAI_API_KEY`, `PUSHOVER_USER`, and `PUSHOVER_TOKEN` to your Space's **Secrets** in the settings.
3. Push the repository to the Space using Git

