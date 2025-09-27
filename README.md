Project Summary

This project is a Streamlit-based application that processes documents and media into useful insights. It can handle PDFs, Word documents, Excel files, audio and video files, microphone recordings, and even YouTube links. The workflow extracts or transcribes content, translates it from English into a target language, summarizes it into concise bullet points, and detects tone.

It uses local modules (pdf.py, word.py, speech.py) and cloud services (OpenAI GPT, Whisper, and optionally Gemini). A lightweight RAG pipeline (st_rag.py) allows question answering over the extracted text. Every run is logged silently using the metrics_silent.py module, saving transcripts, translations, summaries, tone analysis, and metadata into a results/ folder for later review 

metrics_silent

.

Setup

Clone the project
Copy all source files (app.py, pdf.py, word.py, speech.py, st_rag.py, metrics_silent.py, install_ffmpeg.py) into a working folder.

Create a virtual environment

python -m venv venv
source venv/bin/activate    # on Linux/macOS
venv\Scripts\activate       # on Windows


Install dependencies
Install required packages:

pip install -r requirements.txt


At minimum, you need:

streamlit

openai

pdfminer.six

python-docx

moviepy

jiwer

langdetect

pandas

Optional but recommended:

PyPDF2

streamlit-mic-recorder

yt-dlp

Set up API keys
Create a .env file in your project folder and add your keys:

OPENAI_API_KEY=your_openai_key


Optionally add Gemini and Google Cloud credentials if you want to use those.

Install FFmpeg
Some features (like YouTube audio extraction and audio conversion) require FFmpeg. On Windows, run:

python install_ffmpeg.py


This script downloads and configures FFmpeg for you

install_ffmpeg

. On macOS/Linux, install via Homebrew or apt:

brew install ffmpeg   # macOS
sudo apt install ffmpeg  # Ubuntu/Debian

Run

Start the Streamlit app:

streamlit run app.py


After starting, you’ll see a local URL in your terminal, for example:

Local URL: http://localhost:8501
Network URL: http://192.168.1.xxx:8501


Open the local URL in your browser.

Usage

Choose an input method:

Upload PDF, Word, Excel, audio, or video files

Record from your microphone (no FFmpeg needed)

Paste a YouTube URL (FFmpeg and yt-dlp required)

Pick a target language from the sidebar.

Click to process. The app will:

Extract or transcribe text

Translate it into your chosen language

Summarize it into bullet points

Detect tone

Download translation and summary as .txt files.

Metrics and run artifacts are saved automatically into the results/ folder

metrics_silent

.

Would you like me to also add a Troubleshooting section (for common issues like missing FFmpeg, expired Google Cloud credentials, or model errors) so your README covers the problems you’ve been running into?
