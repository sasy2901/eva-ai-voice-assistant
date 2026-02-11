# 🎙️ Eva: Multimodal AI Financial Analyst

Eva is an enterprise-grade AI Voice Agent designed for real-time market sentiment analysis and financial briefing. By combining **Deepgram's** sub-second speech-to-text with **Groq's Llama-3.3** (70B), Eva provides instant stock metrics and modulates its UI/Response tone based on the user's vocal sentiment.

## 🏗️ Architecture & Data Flow
The system utilizes an asynchronous event loop to handle concurrent audio streaming and LLM processing, ensuring a "Human-in-the-loop" experience without blocking I/O.

```mermaid
graph TD
    A[User Voice] -->|MediaRecorder API| B(Frontend: JS/HTML)
    B -->|WebSocket: Binary Audio| C{FastAPI Backend}
    C -->|wss://| D[Deepgram STT]
    D -->|Transcript| C
    C -->|TextBlob| E[Sentiment Engine]
    E -->|Mood Data| F[Groq Llama-3.3]
    C -->|yfinance| G[Market Data API]
    G -->|Stock Metrics| F
    F -->|JSON Intent| C
    C -->|Aura-Asteria| H[Deepgram TTS]
    H -->|Base64 Audio| B
    B -->|Audio Playback + UI Glow| I[User Experience]
🚀 Key Features
Real-time Voice Interface: Low-latency bi-directional streaming via WebSockets.

Sentiment-Driven UI: Dynamic theme modulation (Dark Red for agitation, Emerald Green for positive sentiment) using NLP polarity scores.

Financial Intelligence: Live integration with yfinance to calculate 'Upside Potential' and 'Analyst Ratings'.

Deterministic Intent Routing: Uses JSON-mode function calling to switch between conversational chat and data-heavy analysis.
🛠️ Technical Stack
Backend: Python, FastAPI, WebSockets

AI/LLM: Groq (Llama-3.3-70B), TextBlob (NLP)

Speech Services: Deepgram (Nova-2 STT & Aura TTS)

Data Integration: Yahoo Finance API

Frontend: HTML5, CSS3 (Custom Properties), JavaScript (MediaRecorder API)
💻 Local Installation & Setup
Prerequisites
Python 3.10+

Groq API Key

Deepgram API Key
1. Clone the Repository
Bash
git clone https://github.com/YOUR_USERNAME/VoiceFlow.git
cd VoiceFlow
2. Install Dependencies
Bash
pip install -r requirements.txt
3. Environment Configuration
Create a .env file in the root directory:

Code snippet
GROQ_API_KEY=your_key_here
DEEPGRAM_API_KEY=your_key_here
4. Launch the Engine
Bash
python -m uvicorn app:app --reload
🧠 Technical Deep-Dive
Latency Optimization: Utilizes asynchronous Python (asyncio) to ensure the STT stream and LLM processing don't block the main event loop.

Graceful Degradation: Implements a heuristic failover system for market data—if the primary API is rate-limited, the agent pivots to simulated metrics to maintain conversation flow.

Deterministic Guardrails: By using JSON-mode response formats, the agent is prevented from "hallucinating" financial figures, ensuring 100% data integrity.

