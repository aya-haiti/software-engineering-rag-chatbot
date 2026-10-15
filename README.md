# Software Engineering Chatbot

A collaborative academic project comparing three Deep Learning and NLP approaches for building a chatbot specialized in **Software Engineering**:

1. **Seq2Seq with Attention from Scratch**
2. **Fine-Tuned FLAN-T5**
3. **Retrieval-Augmented Generation (RAG)**

The objective of this project was to evaluate which architecture provides the best balance between response quality, robustness, contextual grounding and hallucination reduction for a specialized educational chatbot.

---

## Project Overview

The chatbot is designed to answer questions related to Software Engineering topics such as:

- Object-Oriented Programming
- UML
- Design Patterns
- Software Testing
- Databases
- APIs
- Git
- DevOps
- Agile methodologies
- Software Architecture

The project implements and compares three different architectures using dedicated Software Engineering datasets and consistent evaluation protocols. :chatgpt-content-reference{index="1"}

---

## Approaches Compared

### 1. Seq2Seq with Attention

The first approach is a generative chatbot trained entirely from scratch.

Main components:

- Bidirectional LSTM encoder
- LSTM decoder
- Bahdanau Attention
- GloVe embeddings
- Word2Vec embeddings

The training corpus was collected from:

- Stack Overflow
- CodeSearchNet
- GitHub Issues

The final vocabulary contains approximately **13,445 tokens**. :chatgpt-content-reference{index="2"}

---

### 2. Fine-Tuned FLAN-T5

The second approach is based on:

- `google/flan-t5-base`
- Fine-tuning on a curated Software Engineering QA dataset
- FAISS semantic retrieval
- CrossEncoder reranking
- English/French support

The model was fine-tuned for 3 epochs using FP16 training and early stopping. :chatgpt-content-reference{index="3"}

---

### 3. Retrieval-Augmented Generation

The third approach implements a complete RAG pipeline combining:

- Multilingual E5 embeddings
- FAISS dense retrieval
- BM25 sparse retrieval
- Hybrid retrieval
- CrossEncoder reranking
- FLAN-T5 generator
- LoRA fine-tuning
- Gradio interface

The goal is to ground the generated answers in retrieved knowledge and significantly reduce hallucinations. :chatgpt-content-reference{index="4"}

---

## Datasets

Three different datasets were used:

| Approach | Dataset Size |
|---|---:|
| From Scratch | 12,693 examples |
| Fine-Tuning | 655 examples |
| RAG | 809 examples |

The RAG dataset was augmented using paraphrasing and conversational reformulation to improve robustness to question variation. :chatgpt-content-reference{index="5"}

---

## Evaluation Metrics

The three approaches were evaluated using:

- BLEU
- Accuracy@K
- MRR
- ROUGE-1
- ROUGE-L
- Semantic Similarity

These metrics were selected depending on whether the task involved retrieval or text generation. :chatgpt-content-reference{index="6"}

---

## Results

### Seq2Seq from Scratch

```text
BLEU: 0.0003
