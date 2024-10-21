# Amazon Product Review Summarization using Pretrained Language Models

## Project Overview

This project demonstrates the use of three prominent pretrained language models—**BART**, **PEGASUS**, and **T5**—for the task of **text summarization**. The goal was to summarize 1000 Amazon product reviews, each ranging between 150 and 350 words, without fine-tuning the models. Given the absence of ground truth labels for the summarization task, traditional evaluation metrics like ROUGE were not applicable. As an alternative, we used **BERTScore** to assess the semantic similarity between the original product reviews and the generated summaries.

## Models Used

1. **BART** (Bidirectional and Auto-Regressive Transformers) - A model designed for text generation tasks, including summarization.
2. **PEGASUS** (Pretraining with Extracted Gap-sentences for Abstractive Summarization Sequence-to-sequence models) - A model specifically optimized for summarization.
3. **T5** (Text-To-Text Transfer Transformer) - A model that casts all NLP tasks into a text-to-text format.

## Data

- **Amazon Product Reviews**: 1000 reviews were collected, with each review containing between 150 and 350 words. 
- The models were applied to generate summaries for each review.

## Evaluation

Due to the absence of labeled data (i.e., no ground truth summaries), **ROUGE** could not be used to evaluate the summarization quality. Instead, **BERTScore** was employed to compute the similarity between the original reviews and the generated summaries, which is based on **token similarity in embedding space**.

### BERTScore Results

| Model    | BERTScore |
|----------|-----------|
| **BART**    | 0.906     |
| **PEGASUS** | 0.9059    |
| **T5**      | 0.84      |

- **BART** and **PEGASUS** achieved nearly identical scores, reflecting strong semantic similarity between the generated summaries and the original reviews.
- **T5**, however, lagged behind with a lower BERTScore of **0.84**, indicating comparatively weaker performance in generating semantically similar summaries.

## Requirements

- **Python 3.7+**
- **Transformers** (Hugging Face)
- **BERTScore**
- **Torch**

To install the required dependencies, use the following command:

```bash
pip install transformers bert-score torch
```

## Project Structure

```
.
├── source.ipynb               # Jupyter Notebook containing the code for summarization and evaluation
├── README.md                   # Project description and instructions (this file)

```

## How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/amazon-review-summarization.git
   cd amazon-review-summarization
   ```

2. Open the Jupyter Notebook:
   ```bash
   jupyter notebook source.ipynb
   ```

3. Run the cells in the notebook to summarize the reviews using the pretrained models and evaluate the summaries.

4. View the results in the output of the notebook.


## Conclusion

This project showcases the application of **BART**, **PEGASUS**, and **T5** models for summarizing Amazon product reviews. While **BART** and **PEGASUS** perform almost identically in terms of semantic similarity with the original reviews, **T5** exhibits a slightly weaker performance. The use of **BERTScore** provides an effective evaluation measure when ground truth summaries are unavailable.
