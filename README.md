
# Naan-mudhalvan-speech-recognition-

#Naanmudhalvan-speech-reconition-# 

accent_aware_virtual_assistant 1
# Accent-Aware Speech Recognition System for Virtual Assistant

This project implements a **real-time accent-aware speech recognition system** using deep learning and speaker adaptation techniques. It's designed to improve the performance of voice-based virtual assistants by adapting to different speaker accents and voices.

## Features

- Real-time speech-to-text transcription using Wav2Vec2
- Accent and speaker adaptation using x-vector embeddings from SpeechBrain
- RESTful API using Flask for easy integration
- Upload audio and get transcribed text and speaker embedding
- Supports `.wav` files sampled at 16kHz

---

## Requirements

- Python 3.8+
- PyTorch
- Transformers
- Torchaudio
- Librosa
- SpeechBrain
- Flask

---

## Installation

1. **Clone the repository:**

```bash
git clone https://github.com/your-username/accent-aware-virtual-assistant.git
cd accent-aware-virtual-assistant
```

2. **Install dependencies:**

```bash
pip install -r requirements.txt
```

> If `requirements.txt` is missing, manually install:
```bash
pip install torch torchaudio librosa transformers speechbrain flask
```

3. **Run the server:**

```bash
python app/accent_aware_virtual_assistant.py
```

---

## API Usage

### Endpoint:
`POST /transcribe`

### Payload:
Send a `.wav` file using form-data.

**Example using curl:**
```bash
curl -X POST -F "audio=@sample.wav" http://localhost:5000/transcribe
```

### Response:
```json
{
  "transcription": "Turn on the lights in the kitchen.",
  "speaker_embedding": [0.0412, -0.0133, ...]
}
```

---

## File Structure

```
accent-aware-virtual-assistant/
│
├── app/
│   └── accent_aware_virtual_assistant.py
│
├── uploads/
├── pretrained_models/
│   └── spkrec/
├── requirements.txt
├── README.md
└── .gitignore
```

---

## License

This project is licensed under the MIT License.

-------------------------------------------------------------------------

Building a Speech-to-Text Transcription for healthcare 2

# Real-Time Speech-to-Text Transcription System for Healthcare with Noise Robustness

This Python project implements a real-time speech-to-text transcription system designed specifically for healthcare environments. It uses OpenAI’s Whisper model for transcription and includes noise robustness, medical term normalization, and critical keyword detection.

## Features

- **Real-time microphone recording**
- **Speech-to-text transcription** using Whisper (`base` model)
- **Noise robustness** with live audio stream handling
- **Normalization of medical terms** (e.g., "bp" → "blood pressure")
- **Keyword detection** for important healthcare alerts
- **Automatic logging** of transcriptions with timestamps

## Installation

1. **Clone this repository**:
   ```bash
   git clone https://github.com/your-username/healthcare-stt-whisper.git
   cd healthcare-stt-whisper
   ```

2. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

3. **(Optional) Set up a virtual environment**:
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows use: venv\Scripts\activate
   ```

## Usage

Run the main script:

```bash
python main_healthcare.py
```

### Output

The system will:
- Listen to audio in 5-second intervals
- Transcribe the speech
- Normalize common medical shorthand
- Detect and print alerts for keywords (e.g., "emergency", "blood pressure")
- Save all transcriptions in `transcription_log.txt`

### Sample Console Output

```
[INFO] Recording started. Speak now...
Transcription:
The patient's blood pressure is 130 over 85 and shows signs of diabetic condition.
------------------------------------------------------------
[ALERT] Detected medical terms: blood pressure, diabetic
```

## Example Medical Term Normalization

| Detected Term     | Normalized Term     |
|-------------------|---------------------|
| bp                | blood pressure      |
| sugar level       | glucose level       |
| ekg               | ECG                 |
| covid             | COVID-19            |
| diabetes type 1   | Type 1 Diabetes     |

## File Structure

```
healthcare-stt-whisper/
├── main_healthcare.py         # Main Python script
├── requirements.txt           # Dependencies
├── README.md                  # Documentation
├── transcription_log.txt      # Auto-created log of transcriptions
└── .gitignore                 # Common ignored files
```

## Requirements

- Python 3.7+
- whisper
- numpy
- sounddevice
- soundfile
- torch

## License

This project is open-source and licensed under the [MIT License](LICENSE).

---

**Developed for use in healthcare transcription, telemedicine support, and voice-powered diagnostics.**

-------------------------------------------------------------------------------------------------------------------------------

End-to-End Speech Recognition
Pipeline 3

## Overview
This project is an **Accent-Aware Speech Recognition System** that uses **Deep Learning** and **Speaker Adaptation Techniques** to improve speech-to-text transcription for virtual assistants, especially in multilingual or accent-diverse environments.

It leverages:
- `Wav2Vec2` for transcription
- `SpeechBrain ECAPA-TDNN` for speaker embedding
- A `Flask` server to handle real-time API-based transcription

---

## Features
- Real-time speech-to-text transcription
- Speaker adaptation using speaker embeddings
- RESTful API to interact with the model
- Accent-aware preprocessing (optional extension)

---

## Setup Instructions

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/accent-aware-speech-recognition.git
cd accent-aware-speech-recognition
```

### 2. Create a Virtual Environment (optional)
```bash
python -m venv venv
source venv/bin/activate  # On Windows use: venv\Scripts\activate
```

### 3. Install Dependencies
```bash
pip install -r requirements.txt
```

### 4. Run the Flask Server
```bash
python main.py
```

### 5. Test the API
Use Postman, Curl, or Python to POST an audio file (WAV format recommended) to:
```
http://localhost:5000/transcribe
```

---

## Sample Request (Python)
```python
import requests

url = "http://localhost:5000/transcribe"
files = {'audio': open('sample.wav', 'rb')}
response = requests.post(url, files=files)
print(response.json())
```

---

## File Structure
```
âââ main.py                # Main application file
âââ requirements.txt       # Python dependencies
âââ uploads/               # Audio uploads folder
âââ README.md              # Project documentation
```

---

## Dependencies
- torch
- torchaudio
- librosa
- transformers
- speechbrain
- flask
- numpy

---

## License
This project is open-source and available under the MIT License.