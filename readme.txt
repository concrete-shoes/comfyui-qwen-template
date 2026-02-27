Variables selection

Download Z-Image Turbo:

DOWNLOAD_Z_IMAGE=true

Auth tokens:

HUGGINGFACE_HUB_TOKEN=""
CIVITAI_TOKEN=""
SSH_PUBLIC_KEY=""

Ports:
8188     (ComfyUI)
8888     (Jupyter)
22       (SSH) 


Civitai Downloader:
📖 Usage

Download a model using its ID:
./download_with_aria.py -m 123456

# Download to specific directory
./download_with_aria.py -m 123456 -o ./models

# Use custom filename
./download_with_aria.py -m 123456 --filename "my_custom_model.safetensors"

# Force re-download (ignore existing files)
./download_with_aria.py -m 123456 --force

# Provide token via command line (not recommended for security)
./download_with_aria.py -m 123456 --token "your_token_here"

Command Line Arguments
Argument	Short	Description	Default
--model-id	-m	CivitAI model version ID (required)
--output	-o	Output directory      
--token	    -	CivitAI API token       
--filename	-	Override default filename
--force	    -	Force re-download

🎯 Examples
Download a LoRA model
./download_with_aria.py -m 245589

# Download character LoRA
./download_with_aria.py -m 245589 -o ./models/lora/characters

# Download style LoRA
./download_with_aria.py -m 234567 -o ./models/lora/styles

# Download checkpoint
./download_with_aria.py -m 345678 -o ./models/checkpoints

Batch download with a simple script
#!/bin/bash
# download_batch.sh

models=(245589 234567 345678 456789)
for model_id in "${models[@]}"; do
    ./download_with_aria.py -m "$model_id" -o ./models
done