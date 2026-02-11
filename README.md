# 🎙️ Eva: Multimodal AI Financial Analyst

Eva is an enterprise-grade AI Voice Agent designed for real-time market sentiment analysis and financial briefing. By combining **Deepgram's** sub-second speech-to-text with **Groq's Llama-3** (70B), Eva provides instant stock metrics and modulates its UI/Response tone based on the user's vocal sentiment.



## 🚀 Key Features
* **Real-time Voice Interface:** Low-latency bi-directional streaming via WebSockets.
* **Sentiment-Driven UI:** Dynamic theme modulation (Dark Red for agitation, Emerald Green for positive sentiment) using NLP.
* **Financial Intelligence:** Live integration with Market Data APIs to calculate 'Upside Potential' and 'Analyst Ratings'.
* **Deterministic Intent Routing:** Uses JSON-mode function calling to switch between conversational chat and data-heavy analysis.

## 🛠️ Technical Stack
* **Backend:** Python, FastAPI, WebSockets
* **AI/LLM:** Groq (Llama-3.3-70B), TextBlob (NLP)
* **Speech Services:** Deepgram (STT & TTS)
* **Data Integration:** Yahoo Finance API (yfinance)
* **Frontend:** HTML5, CSS3 (Custom Properties), JavaScript (MediaRecorder API)

## 🏗️ Architecture
The system utilizes an asynchronous event loop to handle concurrent audio streaming and LLM processing, ensuring a "Human-in-the-loop" experience without blocking I/O.

---

## 💻 Local Installation & Setup

### **Prerequisites**
* Python 3.10+
* Groq API Key
* Deepgram API Key

### **1. Clone the Repository**
```bash
git clone [https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git](https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git)
cd YOUR_REPO_NAME
Gemini said
This is the "Senior Engineer" move that separates you from everyone else. A professional README.md file isn't just a manual; it’s a high-impact sales pitch for your skills. It tells an HR manager exactly what you built, how you built it, and why you are hireable.

Here is the exact template to paste into your GitHub.

Step 1: Create the README
On your GitHub repository page, click Add file -> Create new file.

Name the file: README.md

Paste the following content (I’ve written this to make you look like a pro):

Markdown
# 🎙️ Eva: Multimodal AI Financial Analyst

Eva is an enterprise-grade AI Voice Agent designed for real-time market sentiment analysis and financial briefing. By combining **Deepgram's** sub-second speech-to-text with **Groq's Llama-3** (70B), Eva provides instant stock metrics and modulates its UI/Response tone based on the user's vocal sentiment.



## 🚀 Key Features
* **Real-time Voice Interface:** Low-latency bi-directional streaming via WebSockets.
* **Sentiment-Driven UI:** Dynamic theme modulation (Dark Red for agitation, Emerald Green for positive sentiment) using NLP.
* **Financial Intelligence:** Live integration with Market Data APIs to calculate 'Upside Potential' and 'Analyst Ratings'.
* **Deterministic Intent Routing:** Uses JSON-mode function calling to switch between conversational chat and data-heavy analysis.

## 🛠️ Technical Stack
* **Backend:** Python, FastAPI, WebSockets
* **AI/LLM:** Groq (Llama-3.3-70B), TextBlob (NLP)
* **Speech Services:** Deepgram (STT & TTS)
* **Data Integration:** Yahoo Finance API (yfinance)
* **Frontend:** HTML5, CSS3 (Custom Properties), JavaScript (MediaRecorder API)

## 🏗️ Architecture
The system utilizes an asynchronous event loop to handle concurrent audio streaming and LLM processing, ensuring a "Human-in-the-loop" experience without blocking I/O.

---

## 💻 Local Installation & Setup

### **Prerequisites**
* Python 3.10+
* Groq API Key
* Deepgram API Key

### **1. Clone the Repository**
```bash
git clone [https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git](https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git)
cd YOUR_REPO_NAME
2. Install Dependencies
Bash
pip install -r requirements.txt
3. Environment Configuration
Create a .env file in the root directory and add your credentials:

Code snippet
GROQ_API_KEY=your_key_here
DEEPGRAM_API_KEY=your_key_here
4. Launch the Engine
Bash
python -m uvicorn app:app --reload
Navigate to http://localhost:8000 to initiate the voice uplink.

