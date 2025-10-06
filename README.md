# SocraticMath: Boosting Large Language Models with the Socratic Method for Conversational Mathematics Teaching

This repository contains the official implementation and dataset for the paper:

**"Boosting Large Language Models with Socratic Method for Conversational Mathematics Teaching"**  
*Yuyang Ding, Hanglei Hu, Jie Zhou, Qin Chen, Bo Jiang, Liang He*  
Published at **CIKM '24**  
[![DOI](https://img.shields.io/badge/DOI-10.1145%2F3627673.3679881-blue)](https://doi.org/10.1145/3627673.3679881)

---

## 📌 Overview

Traditional Large Language Models (LLMs) often provide direct solutions to math problems, which is suboptimal for educational settings. In contrast, **Socratic teaching** emphasizes guided inquiry—helping learners discover knowledge through thoughtful questioning.

We introduce:
- **SocraticLLM**: A knowledge-enhanced LLM fine-tuned to act as a Socratic math tutor, using a structured dialogue strategy (review → heuristic → rectification → summarization).
- **SocraticMATH**: A high-quality, human-annotated dataset of Socratic-style math tutoring dialogues covering **513 primary school math knowledge points**.

Our approach significantly improves both **teaching quality** and **reasoning reliability** compared to standard LLMs like ChatGPT and GPT-4.

---

## 🗂️ Dataset: SocraticMATH

### Features
- **6,846** multi-turn Socratic tutoring conversations
- Covers **513** primary school math knowledge points (e.g., GCD, LCM, fractions, geometry)
- Each conversation includes:
  - Original math problem (fill-in-the-blank, multiple-choice, etc.)
  - Step-by-step solution & final answer
  - Socratic dialogue between tutor and student
  - Annotated knowledge tags and difficulty levels
- Average **~5 turns** per conversation, **~86 words** per utterance

### Comparison to Existing Datasets
| Dataset       | Socratic? | Conversational? | Knowledge Tags | Math Teaching Focus |
|---------------|-----------|------------------|----------------|---------------------|
| **SocraticMATH** | ✅        | ✅               | ✅             | ✅                  |
| GSM8K         | ❌        | ❌               | ❌             | ❌                  |
| MathQA        | ❌        | ❌               | ❌             | ❌                  |
| MathDial      | ❌        | ⚠️ (semi-auto)   | ❌             | Limited             |

> ✅ **SocraticMATH is the first dataset designed explicitly for Socratic-style math tutoring.**

---

## 🧠 Model: SocraticLLM

### Architecture
- Base model: **Qwen1.5-7B**
- Fine-tuned with **LoRA (Low-Rank Adaptation)**
- Input includes:
  - Socratic-style prompt (role, rules, strategy)
  - Math question
  - Extra knowledge (solution, answer, key concepts)

### Teaching Strategy
Each response follows a 4-phase structure:
1. **Review**: Clarify concepts or prior knowledge
2. **Heuristic**: Ask guiding questions to promote discovery
3. **Rectification**: Detect and correct student errors
4. **Summarization**: Reinforce learning and conclude

### Example
**Student**: "Two coprime composite numbers have LCM 90. What are they?"  
**SocraticLLM**:  
> "Great question! First, can you recall what 'coprime' means?"  
> *(After student responds)*  
> "Correct! Now, can you factorize 90 into primes?"  
> ... *(guides step-by-step without giving the answer)*

---

## 📜 License

- Code: MIT License
- Dataset: CC BY-NC 4.0 (Non-commercial use only)

> For commercial use, please contact the authors.

---


## 📚 Citation

If you use SocraticMATH or SocraticLLM in your research, please cite:

```bibtex
@inproceedings{ding2024socratic,
  title={Boosting Large Language Models with Socratic Method for Conversational Mathematics Teaching},
  author={Ding, Yuyang and Hu, Hanglei and Zhou, Jie and Chen, Qin and Jiang, Bo and He, Liang},
  booktitle={Proceedings of the 33rd ACM International Conference on Information and Knowledge Management},
  series={CIKM '24},
  year={2024},
  publisher={ACM},
  doi={10.1145/3627673.3679881}
}
```

---

🌟 **Empowering AI tutors to teach—not just tell.**
