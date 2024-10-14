# 📣 Argument Mining in BioMedicine: Zero-Shot, In-Context Learning and Fine-tuning with LLMs 📣

Argument Mining (AM) aims to extract the complex argumentative structure of a text and Argument Type Classification (ATC) is an essential sub-task of AM. Large Language Models (LLMs) have shown impressive capabilities in most NLP tasks and beyond. However, fine-tuning LLMs can be challenging. In-Context Learning (ICL) has been suggested as a bridging paradigm between training-free and fine-tuning settings for LLMs. In ICL, an LLM is conditioned to solve tasks using a few solved demonstration examples included in its prompt. We focuse on AM in the biomedical AbstRCT dataset. We address ATC using quantized and unquantized LLaMA-3 models through zero-shot learning, in-context learning, and fine-tuning approaches. We introduce a novel ICL strategy that combines $k$NN-based example selection with majority vote ensembling, along with a well-designed fine-tuning strategy for ATC. In zero-shot setting, we show that LLaMA-3 fails to achieve acceptable classification results, suggesting the need for additional training modalities. However, in our ICL training-free setting, LLaMA-3 can leverage relevant information from only a few demonstration examples to achieve very competitive results. Finally, in our fine-tuning setting, LLaMA-3 achieves state-of-the-art performance on ATC task in AbstRCT dataset.

# 🧮 Data

We consider the `AbstRCT` dataset which consists of abstracts of `650 Randomized Controlled Trials` selected from PUBMed. The Neoplasm train set (Neo-train) consists of 350 abstracts whereas the three test sets (Neoplasm, Glaucoma and Mixed tests sets/Neo-test, Gla-test and Mix-test, respectively) consist of 100 abstracts each. The `argument type classification (ATC)` task consists of predicting the type of each argument component (AC) as `Claim` or `Premise`.

# 🎛️ Modalities

We use LLMs for three classification tasks:

1) **Zero-Shot Classification (ZSC):** Zero-shot classification is a Deep Learning technique where the pre-trained model is used *off the shelf* (i.e. witout any further training) for inference on completely unseen data samples.
2) **In-Context Learning (ICL):** In-Context Learning is a Deep Learning technique where a model is *guided* for accurate inference with the help of a few solved demonstrations added in the model's input prompt.
3) **Fine-Tuning (FT):** Fine-tuning involves further training of a pre-trained model on a downstream dataset. This helps general-purpose model training to be complemented with task specific supervised training.

# ⛓️ Models

We experiment with the following models:

- **LLaMA-3-8B-Instruct**
- **LLaMA-3-8B-Instruct-bnb-4bit**
- **LLaMA-3-70B-Instruct-bnb-4bit**

<br>

# 📦 Requirements

We use the following versions of the packages:

```
torch==2.4.0
gradio==4.43.0
pydantic==2.9.0
LLaMA-Factory==0.9.0
transformers==4.44.2
bitsandbytes==0.43.1
```

<br>

# 💻 Platform and Compute

- For fine-tuning LLMs, we use [**LLaMA-Factory.**](https://github.com/hiyouga/LLaMA-Factory)
- For model checkpoints, we use [**Unsloth.**](https://unsloth.ai/)
- We also use [**Hugging Face.**](https://huggingface.co/)

All experiments have been performed on the High Performance Cluster at [**La Rochelle Université.**](https://www.univ-larochelle.fr/)
