🩺 CureVoice-AI

A voice-enabled AI health assistant. Speak your symptoms, optionally upload a photo of the affected area (skin, hair, injury), and get a spoken and written response from an AI "doctor".

⚠️ Disclaimer: CureVoice-AI is an educational project. It is not a medical device and does not replace professional medical advice, diagnosis, or treatment. Always consult a qualified doctor.

<!-- TODO: add a demo GIF or screenshot here --> <!-- ![Demo](assets/demo.gif) -->
✨ Features
🎙️ Voice input: record your symptoms with the microphone (speech-to-text)
🖼️ Image analysis: upload a photo (e.g. acne, dandruff, keloid, white spots, fracture X-ray) for the AI to examine
🧠 AI reasoning: a multimodal model combines your words and the image to produce a response
🔊 Voice output: the reply is converted to speech (text-to-speech)
🌐 Simple web UI built with Gradio
🏗️ How It Works
 Patient's voice ──► Speech-to-Text ──┐
                                      ├──► Multimodal AI ──► Text reply ──► Text-to-Speech ──► Doctor's voice
 Patient's image ─────────────────────┘
File	Role
voice_of_the_patient.py	Records audio from the microphone and transcribes it to text
brain_of_the_doctor.py	Sends the text and image to the AI model and gets the analysis
voice_of_the_doctor.py	Converts the AI's reply into speech (audio file)
gradio_app.py	Gradio web interface that connects all the steps
🧰 Tech Stack
Language: Python
UI: Gradio
Speech-to-Text / Text-to-Speech: <!-- TODO: e.g. SpeechRecognition, gTTS, ElevenLabs -->
AI model: <!-- TODO: e.g. Groq (Llama vision), OpenAI, Gemini -->
Audio handling: PyAudio, pydub, ffmpeg <!-- TODO: confirm -->
🚀 Getting Started
Prerequisites
Python 3.9+ <!-- TODO: confirm your Python version -->
A working microphone
FFmpeg installed and on your PATH
An API key for the AI provider you use
1. Clone the repository
bash
git clone https://github.com/mohit-jat/CureVoiceAi.git
cd CureVoiceAi
2. Install dependencies

Using pip:

bash
python -m venv venv
# Windows
venv\Scripts\activate
# macOS / Linux
source venv/bin/activate

pip install -r requirements.txt

Or using Pipenv:

bash
pipenv install
pipenv shell

Installing PyAudio

Windows: pip install pyaudio (if it fails, download a wheel matching your Python version)
macOS: brew install portaudio && pip install pyaudio
Linux: sudo apt install portaudio19-dev && pip install pyaudio
3. Set up API keys

Create a .env file in the project root:

env
# TODO: use the exact variable names your code reads
GROQ_API_KEY=your_key_here
ELEVENLABS_API_KEY=your_key_here

Never commit your .env file.

4. Run the app
bash
python gradio_app.py

Open the local URL shown in the terminal (usually http://127.0.0.1:7860).

🖼️ Sample Images

Sample images (acne.jpg, dandruff.jpg, keloid.jpg, whitespots.jpg, fracture shoulder.jpg) are included for quick testing.

⚠️ Limitations
The AI can be wrong. Do not rely on it for real medical decisions.
Image-based analysis is not a substitute for clinical examination or lab tests.
Accuracy depends on audio quality, image quality, and the underlying model.
🛣️ Roadmap
 Multi-language support (Hindi, etc.)
 Conversation history
 Deploy a live demo (Hugging Face Spaces / Render)
 Better safety prompts and emergency-symptom warnings
🤝 Contributing

Issues and pull requests are welcome.

📄 License
<!-- TODO: add a LICENSE file (e.g. MIT) and update this line -->

This project is licensed under the MIT License.

👤 Author

Mohit — GitHub