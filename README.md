# Question-Answer Generation Pipeline (qa-generator-pipeline-aied2024)

This project generates questions and answers from PDF lecture slides using different AI models.

## Contents

- [Overview](#overview)
- [Setup](#setup)
  - [Requirements](#requirements)
  - [Installation](#installation) 
- [Usage](#usage)
- [Code Structure](#code-structure)
- [Models](#models)
  - [Llama 2 13B](#llama-2-13b)
  - [GPT-3.5 Turbo](#gpt-35-turbo)
  - [Flan-T5-XXL](#flan-t5-xxl)  
- [Results](#results)
- [Contributing](#contributing)

## Overview

The workflow follows these steps:

1. Extract text from PDF slides
2. Generate answers from slide text using Llama 2 
3. Generate questions for each answer using Llama 2
4. Generate additional questions using GPT-3.5 Turbo
5. Generate additional questions using Flan-T5-XXL
6. Save question-answer pairs to JSON file

The code provides examples for generating questions from a set of sample lecture slides on Pattern Recognition.

## Setup

### Requirements

- Python 3.10+
- PyTorch
- Transformers
- OpenAI API key
- Hugging Face auth token

### Installation

Clone the repo:

```
git clone https://github.com/limu-research/qa-generator-pipeline-aied2024.git
cd qa-generator-pipeline-aied2024
```

Install requirements:

```
pip install -r requirements.txt
```

## Usage

Run the notebooks in order:

1. `extract_text.ipynb` - Extract text from PDFs 
2. `generate_qa.ipynb` - Generate Q&A pairs
3. `generate_questions.ipynb` - Generate additional questions

Set the `OPENAI_API_KEY` and `HF_AUTH_TOKEN` environment variables before running.

## Code Structure

- `pdf_slides/` - Folder containing sample PDF slides 
- `extract_text.ipynb` - Notebook to extract text from PDFs
- `generate_qa.ipynb` - Generate Q&A pairs with Llama 2
- `generate_questions.ipynb` - Generate additional questions with GPT-3.5 Turbo and Flan-T5-XXL
- `qa_pairs.json` - JSON file containing generated question-answer pairs
- `requirements.txt` - Python requirements

## Models

### Llama 2 13B

[Llama 2](https://huggingface.co/models/meta-llama/Llama-2-13b-chat-hf) is used to generate answers and initial questions from the PDF slide text.

### GPT-3.5 Turbo 

[GPT-3.5 Turbo](https://platform.openai.com/docs/models/gpt-3.5-turbo) is used to generate additional questions for each answer. 

### Flan-T5-XXL

[Flan-T5-XXL](https://huggingface.co/google/flan-t5-xxl) generates additional questions for each answer.

## Results

The output is a JSON file `qa_pairs.json` containing the generated question-answer pairs.

## Contributing

Pull requests are welcome! Feel free to open an issue for any enhancements or bugs.
