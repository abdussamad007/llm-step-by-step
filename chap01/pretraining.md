For engineers starting with **pre-training or adapting a base model**, the usual first choices are models that are **well-documented, open, and widely supported.** These are commonly used:
Below are the sequence where AI engineers start deep diving - 
1️⃣ BERT -> 2️⃣ RoBERTa -> 3️⃣ GPT-2 -> 4️⃣ T5 -> 5️⃣ LLaMA

This sequence teaches almost every major LLM training paradigm.

### 1. BERT [Original Paper](https://arxiv.org/abs/1810.04805)

BART is the Most common starting point for engineers to pre train it for various purpose such as **Text classification,Question answering,
Named Entity Recognition and Semantic search**

There are various reasons why BERT is chosen as the 1st stpe to pretrain a large langulage model because of its vast ecosystem availability in terms of **Huge ecosystem and tutorials,Available on Hugging Face Transformers and Easy to fine-tune for many tasks.

**BERT (Bidirectional Encoder Representations from Transformers)** is a transformer-based language model introduced by **Google AI in 2018.** It marked a major breakthrough in natural language processing by enabling deep bidirectional understanding of text, setting new performance records on multiple benchmark tasks.

### Some of the features of BERT
* Simple architecture compared to newer LLMs
* BERT architecture is base on Transformer encoder and Bidirectional understanding of text.
* Training tasks: Masked Language Modeling, Next Sentence Prediction
* Model sizes: BERT-Base (110M parameters), BERT-Large (340M)
* Paper: “BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding” (2018)
```
Common configurations of BERT as - 
| Model      | Layers | Hidden Size | Attention Heads | Parameters |
| ---------- | ------ | ----------- | --------------- | -----------|
| BERT Base  | 12     | 768         | 12              | ~110M      |
| BERT Large | 24     | 1024        | 16              |  ~340M     |

```

BERT builds upon the transformer encoder, using self-attention layers to model contextual relationships between all words in a sentence. Unlike earlier unidirectional models, BERT reads text both left-to-right and right-to-left simultaneously. It is pretrained on large text corpora (English Wikipedia and BookCorpus) through two self-supervised tasks: predicting masked words (Masked Language Modeling) and identifying if one sentence follows another (Next Sentence Prediction).

**Fine-tuning and Applications**
After pretraining, BERT can be fine-tuned for diverse downstream tasks with minimal architecture changes. Common applications include question answering, sentiment analysis, named entity recognition, and text classification. Fine-tuning typically requires adding a small output layer and training on task-specific labeled data for a few epochs.

**Variants and Influence**
BERT has inspired many derivatives optimized for size, language, or domain, such as **RoBERTa, DistilBERT, BioBERT, and ALBERT.** It also underpins multilingual and domain-specific models that extend transformer-based NLP across languages and industries.

**Impact**
BERT redefined state-of-the-art benchmarks such as GLUE and SQuAD, shifting the NLP field toward transformer-based pretraining. Its open-source release catalyzed a surge of research and industrial adoption, influencing later large-scale language models including GPT and T5.

### BERT Training Details
* Data: Wikipedia (2.5B words) + BookCorpus (800M words)
* Batch Size: 131,072 words (1024 sequences * 128 length or 256 sequences * 512 length)
* Training Time: 1M steps (~40 epochs)
* Optimizer: AdamW, 1e-4 learning rate, linear decay
* BERT-Base: 12-layer, 768-hidden, 12-head
* BERT-Large: 24-layer, 1024-hidden, 16-head
* Trained on 4x4 or 8x8 TPU slice for 4 days
