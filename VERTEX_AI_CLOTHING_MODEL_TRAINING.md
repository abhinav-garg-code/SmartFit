🚀 Overview

You will learn how to:

Mount Google Drive

Install required dependencies

Authenticate Google Cloud

Prepare dataset in JSONL format

Upload images + JSONL to Google Cloud Storage

Create a Vertex AI dataset

Fine-tune an AutoML Image Classification model

Retrieve model ID

Deploy and use the fine-tuned model

Vertex AI Fine-tuning Guide (Google Colab)

This file contains the entire step-by-step process to fine-tune an AutoML Image Classification model on Google Cloud Vertex AI using Google Colab.

✅ STEP 1: Mount Google Drive
from google.colab import drive
drive.mount('/content/drive')

print("✓ Google Drive mounted!")
print("Your data is at: /content/drive/My Drive/")


Check:

import os
os.listdir('/content/drive/My Drive/')

✅ STEP 2: Install Required Packages
!pip install google-cloud-aiplatform google-cloud-storage python-dotenv
!pip install pillow numpy pandas

print("✓ All packages installed!")

✅ STEP 3: Authenticate Google Cloud
from google.colab import auth
auth.authenticate_user()

print("✓ Authenticated with Google Cloud!")

✅ STEP 4: Set Google Cloud Project Details
PROJECT_ID = "your-project-id"
BUCKET_NAME = "your-bucket-name"
REGION = "us-central1"

print(f"Project ID: {PROJECT_ID}")
print(f"Bucket: {BUCKET_NAME}")
print(f"Region: {REGION}")

✅ STEP 5: Prepare Dataset Into JSONL
import json
import os
from pathlib import Path

DATASET_PATH = "/content/drive/My Drive/img"
OUTPUT_FILE = "/content/training_data.jsonl"

all_data = []

print("Scanning dataset...")

for gender in ['MEN', 'WOMEN']:
    gender_path = os.path.join(DATASET_PATH, gender)
    
    if not os.path.exists(gender_path):
        print(f"WARNING: {gender_path} not found!")
        continue
    
    print(f"\nProcessing {gender}...")
    
    for clothing_type in os.listdir(gender_path):
        clothing_path = os.path.join(gender_path, clothing_type)
        
        if not os.path.isdir(clothing_path):
            continue
        
        for img_file in os.listdir(clothing_path):
            if img_file.lower().endswith(('.jpg', '.jpeg', '.png', '.gif', '.webp')):
                img_path = os.path.join(clothing_path, img_file)
                
                data = {
                    "image_uri": img_path,
                    "text_snippet": f"Gender: {gender}, Type: {clothing_type}"
                }
                all_data.append(data)

print(f"\nFound {len(all_data)} images total")

with open(OUTPUT_FILE, 'w') as f:
    for data in all_data:
        f.write(json.dumps(data) + '\n')

print("✓ Saved to training_data.jsonl")
