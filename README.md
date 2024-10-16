# Finetuning-Gemma2b

## Overview
- LoRA(Low Rank Adaptation) fine tuning of Gemma 2b model on Dolly 15k dataset

- LoRA is a fine-tuning technique which greatly reduces the number of trainable parameters for downstream tasks by freezing the weights of the model and inserting a smaller number of new weights into the model. This makes training with LoRA much faster and more memory-efficient, and produces smaller model weights (a few hundred MBs), all while maintaining the quality of the model outputs.


## Problem Objective
- To fine tune a Large Language model Gemma 2b with Dolly 15k dataset.

## Methodology

The method involves:
- Loading Dataset

- Loading the Large Language model Gemma2b

- Getting completions from the model before fine tuning

- LoRA fine tuning

- Completions after fine tuning the model

### 1 - Dataset
- `Databricks-dolly-15k` is an open source dataset of instruction-following records generated by thousands of Databricks employees in several of the behavioral categories outlined in the InstructGPT paper, including brainstorming, classification, closed QA, generation, information extraction, open QA, and summarization.

![Dataset](https://github.com/Pratik872/Finetuning-Gemma2b/blob/main/readme%20resources/dataset%20sample.png)

### 2 - Large Language model Gemma2b
- Gemma is a family of lightweight, state-of-the art open models built from the same research and technology used to create the Gemini models.

- Large Language Models (LLMs) like Gemma have been shown to be effective at a variety of NLP tasks. An LLM is first pre-trained on a large corpus of text in a self-supervised fashion. Pre-training helps LLMs learn general-purpose knowledge, such as statistical relationships between words. An LLM can then be fine-tuned with domain-specific data to perform downstream tasks (such as sentiment analysis).

![Gemma](https://github.com/Pratik872/Finetuning-Gemma2b/blob/main/readme%20resources/gemma.png)

### 3 - Completions before Fine Tuning
- Asking about Europe trip
![Europe](https://github.com/Pratik872/Finetuning-Gemma2b/blob/main/readme%20resources/inferences%20before%20finetuning1.png)

- Asking about Photosynthesis
![Photosynthesis](https://github.com/Pratik872/Finetuning-Gemma2b/blob/main/readme%20resources/inferences%20before%20finetuning2.png)

<b> Note here that the model response contains words that might not be easy to understand for a child such as chlorophyll. To get better responses from the model, fine-tune the model with Low Rank Adaptation (LoRA)

### 4 - Fine tuning using `LoRA`
![LoRA](https://github.com/Pratik872/Finetuning-Gemma2b/blob/main/readme%20resources/lora.png)

- Note that enabling LoRA reduces the number of trainable parameters significantly (from 2.6 billion to 2.9 million)


### 5 - Inferences after Fine tuning
- Asking about Europe trip
![Europe2](https://github.com/Pratik872/Finetuning-Gemma2b/blob/main/readme%20resources/inf%20after%20lora1.png)

<b>Note that the model now recommends places to visit in Europe.

- Asking about Photosynthesis
![Photosynthesis2](https://github.com/Pratik872/Finetuning-Gemma2b/blob/main/readme%20resources/inf%20after%20lora2.png)

<b>Note that the model now explains photosynthesis in simpler terms. 


### Built with 🛠️
- Packages/Repo : Langchain, Jupyter, Streamlit, Groq

- Coded on : Jupter Notebook (modelling), VSCode(building application)

