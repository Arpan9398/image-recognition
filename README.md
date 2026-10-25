# 🖼️ Image Recognition

Classify images into 1,000 everyday categories (dogs, cars, food, objects...) using pretrained deep-learning models.

## Features
- Upload an image **or** take a photo with your webcam
- Choose between **ViT (Vision Transformer)** and **ResNet-50**
- Shows top-K predictions with confidence bars
- Runs locally — **no API key required**

## Tech Stack
| Part | Tool |
|------|------|
| UI | Streamlit |
| Model | Hugging Face Transformers (`google/vit-base-patch16-224`, `microsoft/resnet-50`) |
| Backend | PyTorch |

## Setup
```bash
# 1. Create a virtual environment
python -m venv venv
# Windows
venv\Scripts\activate
# Mac/Linux
source venv/bin/activate

# 2. Install dependencies
pip install -r requirements.txt

# 3. Run
streamlit run app.py
```
App opens at http://localhost:8501

> First run downloads the model (~350 MB). After that it works offline.

## How It Works
1. Image is resized and normalized to 224×224.
2. It's split into patches (ViT) or passed through conv layers (ResNet).
3. The model outputs a probability for each of 1,000 ImageNet classes.
4. We show the top-K classes.

## Ideas to Extend
- Fine-tune on your own dataset (e.g. plant diseases, Indian food)
- Add object detection with `facebook/detr-resnet-50`
- Deploy free on Streamlit Community Cloud / Hugging Face Spaces
