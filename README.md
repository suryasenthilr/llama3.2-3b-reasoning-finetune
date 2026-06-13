# Llama3-R1-Reasoning

A reasoning-focused fine-tuning of Llama 3.2 3B Instruct using Unsloth and LoRA.

## Overview

This repository contains the training workflow, model configuration, and deployment setup for a reasoning-oriented language model. The model was trained on problem-solving data containing questions, reasoning traces, and final answers.

## Features

* Llama 3.2 3B Instruct base model
* LoRA/QLoRA fine-tuning with Unsloth
* Reasoning-focused instruction following
* GGUF export support
* Ollama compatibility

## Model

Hugging Face: https://huggingface.co/sxrya/Llama3-R1-Reasoning

## Usage

```bash
ollama create my_model -f Modelfile
ollama run my_model
```

## Tech Stack

* Unsloth
* Hugging Face Transformers
* TRL
* PyTorch
* Ollama

## Author

Surya S
