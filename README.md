# Llama3-R1-Reasoning

A reasoning-focused adaptation of Llama 3.2 3B Instruct fine-tuned using LoRA with Unsloth.

## Overview

Llama3-R1-Reasoning is a lightweight reasoning model designed to improve step-by-step problem solving, logical reasoning, and instruction-following capabilities while maintaining efficient deployment requirements.

The model was trained on datasets containing questions, reasoning traces, and final answers, enabling it to generate structured reasoning before producing responses.

## Model Details

| Attribute          | Value                 |
| ------------------ | --------------------- |
| Base Model         | Llama 3.2 3B Instruct |
| Architecture       | Transformer           |
| Parameters         | 3 Billion             |
| Fine-Tuning Method | LoRA                  |
| Training Framework | Unsloth               |
| Precision          | 4-bit QLoRA Training  |
| Deployment Formats | Hugging Face, GGUF    |
| Inference Support  | Transformers, Ollama  |

## Key Features

* Reasoning-oriented instruction tuning
* Step-by-step problem solving
* Efficient LoRA fine-tuning
* GGUF export for local inference
* Ollama compatibility
* Consumer GPU friendly deployment

## Hugging Face Model

Model Repository:

https://huggingface.co/sxrya/Llama3-R1-Reasoning

## Installation

### Hugging Face Transformers

```bash
pip install transformers torch
```

```python
from transformers import AutoTokenizer, AutoModelForCausalLM

model_name = "sxrya/Llama3-R1-Reasoning"

tokenizer = AutoTokenizer.from_pretrained(model_name)
model = AutoModelForCausalLM.from_pretrained(model_name)

prompt = "Solve: If a train travels 60 km in 1 hour, how far will it travel in 3 hours?"

inputs = tokenizer(prompt, return_tensors="pt")
outputs = model.generate(**inputs, max_new_tokens=256)

print(tokenizer.decode(outputs[0], skip_special_tokens=True))
```

## Ollama Usage

Create a Modelfile:

```bash
FROM ./Llama3-R1-Reasoning.gguf
```

Build and run:

```bash
ollama create llama3-r1-reasoning -f Modelfile
ollama run llama3-r1-reasoning
```

## Training Stack

* Unsloth
* Hugging Face Transformers
* TRL
* PEFT
* PyTorch
* Ollama

## Intended Use

This model is intended for:

* Educational problem solving
* Mathematical reasoning
* Logical reasoning tasks
* Research and experimentation
* Local LLM deployment

## Author

Surya S

