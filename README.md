# Hey-Term

Hey-Term is a voice-activated terminal automation tool that allows users to execute commands using natural language. It utilizes Whisper for speech-to-text conversion and DeepSeek-R1:8B (via LangChain and Ollama) for natural language processing. A macOS Automator hotkey triggers the system, enabling seamless hands-free terminal interaction.

## Features
- **Voice Command Execution**: Speak commands, and they get executed in the terminal.
- **Whisper Integration**: Converts spoken words into text.
- **DeepSeek-R1:8B with LangChain**: Interprets the text and generates appropriate terminal commands.
- **Mac Automator Hotkey**: Quick access via a user-configurable keyboard shortcut.
- **PyAudio for Audio Capture**: Listens and records audio seamlessly.

## How It Works
1. The user presses a configured hotkey.
2. PyAudio records the audio input.
3. The recorded audio is processed by Whisper to convert it into text.
4. The transcribed text is sent to DeepSeek-R1:8B via LangChain.
5. The AI model generates an appropriate terminal command.
6. The generated command is executed in the macOS terminal.

## Installation
### Prerequisites
- macOS
- Python 3.9+
- [Whisper](https://github.com/openai/whisper)
- [LangChain](https://python.langchain.com/)
- [Ollama](https://ollama.ai/)
- [DeepSeek-R1:8B](https://github.com/DeepSeek-AI)
- PyAudio (`brew install portaudio && pip install pyaudio`)
- macOS Automator (built-in)

### Steps
1. **Clone the repository:**
   ```bash
   git clone https://github.com/yourusername/hey-term.git
   cd hey-term
   ```
2. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```
3. **Set up Ollama and DeepSeek-R1:8B:**
   - Follow the [Ollama setup guide](https://ollama.ai/docs) to run DeepSeek locally.
   - Ensure the model is available and running.

4. **Configure macOS Automator:**
   - Open Automator and create a new "Quick Action."
   - Set it to "Receive no input" and select "Run Shell Script."
   - Add the command to trigger the Hey-Term script.
   - Save and assign a hotkey in macOS settings.

## Usage
1. Press the configured hotkey.
2. Speak your command.
3. Wait for processing.
4. The terminal executes the corresponding command.

## Example
**You say:**
> "Create a new directory called test-folder and move into it."

**Executed command:**
```bash
mkdir test-folder && cd test-folder
```

## Limitations
- May misinterpret complex commands.
- Whisper accuracy depends on the quality of the audio input.
- Requires proper handling of system-critical commands to prevent unintended executions.

