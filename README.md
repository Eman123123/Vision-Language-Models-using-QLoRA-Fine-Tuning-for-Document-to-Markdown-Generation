# Vision-Language-Models-using-QLoRA-Fine-Tuning-for-Document-to-Markdown-Generation
📋 Overview
This project implements QLoRA (Quantized Low-Rank Adaptation) fine-tuning of the Qwen2-VL-2B-Instruct vision-language model for converting document images to structured Markdown format. The model is trained on the Nougat dataset and demonstrates the effectiveness of parameter-efficient fine-tuning for document understanding tasks.

🎯 Key Features
QLoRA Fine-tuning: 4-bit quantization with LoRA adapters for efficient training

Document-to-Markdown: Convert scanned documents, screenshots, and images to clean Markdown

Multiple Prompt Styles: Standard, detailed, and concise prompting strategies

Comprehensive Evaluation: ROUGE, BLEU metrics with visual comparisons

Interactive Gradio UI: User-friendly web interface for inference

Dual GPU Support: Optimized for multi-GPU training environments

Early Stopping: Prevents overfitting with validation-based early stopping

🏗️ Architecture
Model Details
Base Model: Qwen2-VL-2B-Instruct

Quantization: 4-bit NF4 with double quantization

LoRA Configuration:

Rank: 16

Alpha: 32

Dropout: 0.05

Target Modules: q_proj, v_proj, k_proj, o_proj, up_proj, down_proj, gate_proj

Trainable Parameters: ~18.5M (1.49% of total)

Training Configuration
Samples: 160 training, 32 validation, 40 test

Epochs: 5 (configurable)

Batch Size: 1 (with gradient accumulation of 4)

Learning Rate: 1e-4 with cosine scheduler

Precision: BF16 mixed precision

Optimizer: paged_adamw_8bit

📊 Dataset
The project uses the Nougat Training Dataset from Kaggle, containing document images with corresponding .mmd (Markdown) files.

Dataset Statistics
Total Pairs: 14,218 valid image-MMD pairs

Image Format: PNG, JPG, JPEG

Content: Scientific papers, academic documents, structured content

Text Length: Average 1,800+ characters per document

Processing: Automatic resizing, validation, and ChatML formatting

