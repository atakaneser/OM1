# 🐧 Linux Installation Guide

Follow these steps to set up and run OM1 on Linux:

1. **Install prerequisites**
   - Python 3.10+
   - Git
   - FFmpeg
   - PortAudio development package

   Example for Debian/Ubuntu:
   ```bash
   sudo apt update
   sudo apt install -y python3 python3-venv python3-pip git ffmpeg portaudio19-dev
Clone the repository and initialize submodules

bash
Copy code
git clone https://github.com/OpenMind/OM1.git
cd OM1
git submodule update --init
Install uv

bash
Copy code
curl -LsSf https://astral.sh/uv/install.sh | sh
Create and activate a virtual environment

bash
Copy code
uv venv
source .venv/bin/activate
Install dependencies

bash
Copy code
uv pip install -r requirements.txt
Set up environment variables
Copy the example environment file:

bash
Copy code
cp env.example .env
Then edit .env to add your OpenMind API key or update config/spot.json5.

Run OM1

bash
Copy code
uv run src/run.py spot
This will start the Spot agent, which uses your webcam and microphone to generate AI responses in your local WebSim environment (accessible via localhost:8000).

✅ Tested on: Ubuntu 22.04 and Debian 12
🧩 Tip: You can also run OM1 in Docker using the provided docker-compose.yml file.
