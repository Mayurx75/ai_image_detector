# AI Image Detector 🚀

Welcome to the **AI Image Detector**! This project uses a **Vision Transformer (ViT)** model to classify images as either **AI-generated** or **real**. Built with **Gradio**, the tool offers a simple and interactive way to detect AI-generated art.

## 📖 Overview

This tool uses the power of a **pre-trained ViT model** to classify images that are either AI-generated or real. It was designed with artistic images in mind, meaning it works best for images generated by AI tools like **Midjourney**, **Stable Diffusion**, **DALLE-2**, and others.

### ✨ Features
- Detects AI-generated images with high accuracy.
- Built with **Gradio (v3.4.1)** for an intuitive, user-friendly interface.
- Supports various image formats and works in real-time.

## ⚙️ Installation

To get started with the AI Image Detector, follow these simple steps:

### 1️⃣ Step 1: Clone the Repository

Clone this repository to your local machine:

```bash
git clone https://github.com/yourusername/ai-image-detector.git
```

### 2️⃣ Step 2: Install Dependencies

Navigate to the project directory and install the required dependencies:

```bash
cd ai-image-detector
pip install -r requirements.txt
```

### 3️⃣ Step 3: Run the Application

Launch the app by running the following command:

```bash
python app.py
```

Once the app is running, you can open the **Gradio interface** in your browser to upload an image and check if it’s AI-generated.

## 🧑‍💻 Usage Example

Here’s an example of how to use the AI Image Detector in Python:

```python
import gradio as gr
from transformers import pipeline

# Load the image classification pipeline
pipe = pipeline("image-classification", "umm-maybe/AI-image-detector")

def image_classifier(image):
    outputs = pipe(image)
    results = {}
    for result in outputs:
        results[result['label']] = result['score']
    return results

# Setup Gradio interface
title = "Maybe's AI Art Detector"
description = """
This app is a proof-of-concept demonstration of using a ViT model to predict whether an artistic image was generated using AI.
"""

demo = gr.Interface(fn=image_classifier, inputs=gr.Image(type="pil"), outputs="label", title=title, description=description)
demo.launch(show_api=False)
```

### 📝 Features of the Code:
- **Gradio Interface**: Simple interface for image uploads.
- **Pipeline Integration**: Uses the pre-trained model (`umm-maybe/AI-image-detector`) to classify images.

## 🤝 Contribution


We welcome contributions to improve the AI Image Detector! If you find bugs or want to add new features, feel free to submit a pull request or open an issue.

1. Fork the repository.
2. Create a branch for your feature.
3. Commit your changes.
4. Push your changes and open a pull request.


---

<p align="center">
  <img src="https://img.shields.io/badge/SDK-Gradio%203.4.1-6a1b9a" alt="Gradio SDK" />
  <img src="https://img.shields.io/badge/Python-3.x-blue" alt="Python Version" />
</p>

&copy; 2024 **AI Image Detector**. All rights reserved.

### Emoji Breakdown:
1. **📖 Overview**: Represents general information about the project.
2. **✨ Features**: Highlights the main features of the project.
3. **⚙️ Installation**: Indicates setup and configuration steps.
4. **1️⃣ Step 1, 2️⃣ Step 2, 3️⃣ Step 3**: Clear steps for installation.
5. **🧑‍💻 Usage Example**: Code-related section for usage.
6. **📝 Features of the Code**: Describes the code functionality.
7. **🤝 Contribution**: Encourages contributions.
8. **📜 License**: Mentions licensing details.

### How to Use:
- Simply copy and paste the markdown content into your `README.md` file.
- GitHub will render the file with proper formatting and the badges will appear automatically.

This **single markdown** file includes everything needed for your project: installation steps, usage instructions, code snippets, contribution guidelines, and more!
