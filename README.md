# SadTalker Installation and Setup Guide
Overview
SadTalker generates talking head videos from a single portrait image and audio input.

1. Installation
Prerequisites
Python 3.8

Git

FFmpeg

Step-by-Step Installation
🐧 Linux/Unix
bash
# Clone the repository
git clone https://github.com/OpenTalker/SadTalker.git
cd SadTalker

# Create and activate conda environment
conda create -n sadtalker python=3.8
conda activate sadtalker

# Install PyTorch with CUDA support
pip install torch==1.12.1+cu113 torchvision==0.13.1+cu113 torchaudio==0.12.1 --extra-index-url https://download.pytorch.org/whl/cu113

# Install FFmpeg
conda install ffmpeg

# Install requirements
pip install -r requirements.txt
🪟 Windows
Install Python 3.8 from python.org ✓ Check "Add Python to PATH"

Install Git from git-scm.com

Install FFmpeg - Follow this tutorial

Clone repository: git clone https://github.com/Winfredy/SadTalker.git

Run start.bat from Windows Explorer

 macOS
Refer to the macOS installation guide for detailed instructions.

2. Download Models
🔄 Automatic Download
bash
bash scripts/download_models.sh
📥 Manual Download Options
Main Models:

Google Drive: Download

GitHub Releases: Download

Baidu Cloud: Download (Password: sadt)

GFPGAN Offline Patch:

Google Drive: Download

GitHub Releases: Download

Baidu Cloud: Download (Password: sadt)

📁 Expected Folder Structure:

text
SadTalker/
├── checkpoints/
│   ├── mapping_00229-model.pth.tar
│   ├── SadTalker_V0.0.2_256.safetensors
│   └── SadTalker_V0.0.2_512.safetensors
└── gfpgan/
    └── weights/
3. Running SadTalker
🌐 WebUI Demo (Recommended)
Easy Start:
Windows: Double click webui.bat

Linux/Mac: Run bash webui.sh

Manual Start:
bash
python app_sadtalker.py
💻 Command Line Interface
Basic Usage:
bash
python inference.py --driven_audio <audio.wav> \
                    --source_image <image.png> \
                    --enhancer gfpgan
Full Body Generation:
bash
python inference.py --driven_audio <audio.wav> \
                    --source_image <image.png> \
                    --result_dir <output_directory> \
                    --still \
                    --preprocess full \
                    --enhancer gfpgan
☁️ Online Demos
HuggingFace: Try Online

Google Colab: Open in Colab

⚙️ Configuration Tips
Feature	Command	Description
Face Enhancement	--enhancer gfpgan	Improves face quality
Full Body Video	--still --preprocess full	Generates full body animation
Output Directory	--result_dir <path>	Custom output location
📁 Output Location: Results are saved in results/$TIMESTAMP/ directory

📄 Supported Formats:

Images: PNG, JPG

Audio: WAV

🛠️ Troubleshooting
Common Issues:
Check the FAQs first

Verify all models are downloaded correctly

Confirm Python version is 3.8

Ensure FFmpeg is installed and in PATH

Validate folder structure matches expected layout
