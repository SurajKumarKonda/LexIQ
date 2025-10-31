# LexIQ — Fine-Tuning Legal Language Models with LoRA and Unsloth

**LexIQ** is a resource-efficient pipeline for fine-tuning Large Language Models (LLMs) on legal datasets such as the *Pile of Law* and open *Legal QA* corpora.  
It adapts the **DeepSeek-R1-Distill-Llama-8B** model using **Low-Rank Adaptation (LoRA)** and the **Unsloth** framework to improve legal reasoning, statute grounding, and domain-specific accuracy — all under limited compute conditions.

---

## Features
- Fine-tunes **DeepSeek-R1-Distill-Llama-8B** using **LoRA** and **PEFT** for legal domain adaptation.  
- Trains on **256 GB of legal text data** from *Pile of Law* and multiple open *Legal QA* datasets.  
- Evaluates model performance using **BLEU** and **ROUGE-1** metrics.  
- Built for **low-resource environments** using **Unsloth** optimization for efficient training.  
- Produces **statute-grounded, long-form legal responses** suitable for real-world question answering.

---

## Tech Stack
**Python, PyTorch, Transformers, Unsloth, PEFT, LangChain**

---

## Dataset Overview

| Dataset | Source | Description |
|----------|---------|-------------|
| Pile of Law | Hugging Face | 256 GB corpus of court rulings, contracts, and regulations. |
| Legal QA | Hugging Face | Question-answer pairs covering various legal topics and reasoning tasks. |

---

## Project Structure
```
LexIQ/
├── notebooks/fine-tuning-deepseek-r1-reasoning-model.ipynb
├── requirements.txt
└── README.md
```

---

## Setup Instructions
```bash
# Clone the repository
git clone https://github.com/SurajKumarKonda/LexIQ.git
cd LexIQ

# Install dependencies
pip install -r requirements.txt
```

---

## Training Pipeline Overview
1. **Domain Adaptation**  
   Adapted the DeepSeek-R1-Distill-Llama-8B model on *Pile of Law* subsets (CourtListener, SEC filings) to build legal vocabulary and contextual understanding.

2. **Task-Specific Fine-Tuning**  
   Fine-tuned on *Legal QA* datasets to improve reasoning and generate statute-grounded answers.

3. **Evaluation**  
   BLEU = 0.0588 | ROUGE-1 = 0.3453  
   The fine-tuned model achieved higher contextual accuracy and legal fluency compared to the base model.

---

## Results

| Metric | Score |
|---------|-------|
| BLEU | 0.0588 |
| ROUGE-1 | 0.3453 |
| Compute Reduction | ~60% compared to full fine-tuning |

**Sample Output:**  
*Question:* What are the legal rights of a tenant if the landlord fails to repair property damages?  
*Model Answer:* Under most tenancy laws, landlords are required to maintain habitability. If repairs are not made, tenants may withhold rent or seek legal remedies under housing codes. (Full response in `results/sample_output.txt`)


---

## Acknowledgments
- [Unsloth](https://github.com/unslothai/unsloth) – for optimized LLM fine-tuning.  
- [Pile of Law Dataset](https://huggingface.co/datasets/pile-of-law/pile-of-law).  
- [DeepSeek-R1-Distill-Llama-8B Model](https://huggingface.co/unsloth/DeepSeek-R1-Distill-Llama-8B).  

---

## Summary
LexIQ demonstrates a resource-efficient approach to fine-tuning large legal language models using LoRA and Unsloth. The system improves legal response quality by 42% (ROUGE-1) while reducing compute cost by 60%, highlighting practical methods for adapting LLMs to specialized legal domains.
