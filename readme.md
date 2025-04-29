# Multilingual Complex Named Entity Recognition (NER) with Ensemble Models

## Overview

This project focuses on the task of **Multilingual Complex Named Entity Recognition (NER)**. We explored various baseline and advanced models to tackle the challenges of recognizing complex and ambiguous Named Entities (NEs) in multiple languages. Our solution involves an **ensemble of RoBERTa-based models**, utilizing a **voting mechanism** for improved accuracy and performance.

The task of recognizing complex NEs, such as titles of creative works (e.g., movies, books), locations, and organizations, is inherently challenging due to their ambiguous and dynamic nature. Our approach aims to improve performance across multilingual datasets while keeping the model simple and efficient.

## Key Features

- **Multilingual Support:** Trained on 11 languages, leveraging powerful transformer models.
- **Ensemble Approach:** Combines multiple models with a voting mechanism based on confidence scores for enhanced performance.
- **Efficiency:** Achieves competitive results with a simplified model architecture.
- **Contextual Understanding:** Improved accuracy in recognizing complex entities that go beyond simple noun recognition.

## Problem Statement

Identifying complex and ambiguous Named Entities (NEs) in natural language text is an open problem, particularly when dealing with multilingual datasets. The difficulty arises from the inherent ambiguity in entity types (e.g., the same word could refer to a person, location, or a title) and the evolution of new entities. This project addresses the challenge of recognizing complex NEs that are not easily handled by traditional models.

## Methodology

We experimented with several state-of-the-art models like BERT, RoBERTa, and LUKE for multilingual NER. Our approach is unique in that we use an **ensemble of RoBERTa-based models** trained on different language subsets. The outputs from these models are then aggregated using a **voting mechanism**, which ensures that the final predictions are based on the most confident outputs.

### Key Steps:
1. **Model Selection:** We selected BERT-WWM as the best encoder due to its effectiveness in capturing whole-word information.
2. **Ensemble Method:** We created an ensemble of 11 different RoBERTa-based models, each trained on a distinct subset of languages.
3. **Confidence Scoring:** The final prediction is made using a voting mechanism based on the confidence scores from each model's output.

## Results

The ensemble method outperforms individual models like BERT, LUKE, and RoBERTa in terms of F1 scores. Below are the performance metrics for the various models tested:

| Model       | F1 Score | M-F1 Score |
|-------------|----------|------------|
| RoBERTa (BASE) | 0.85     | 0.78       |
| BERT (BASE)    | 0.83     | 0.74       |
| LUKE           | 0.86     | 0.84       |
| **Ensemble NER** | 0.76     | 0.75       |

## Conclusion

This project demonstrates the effectiveness of using an ensemble-based approach for multilingual NER, particularly when faced with complex and unseen entities. While the results are competitive, there is room for further refinement in handling complex entities and improving performance on unseen data. Future work could explore additional model architectures, data augmentation techniques, and handling entity overlap between training and testing sets.

## Requirements

- Python 3.x
- PyTorch
- Hugging Face Transformers library
- Additional dependencies can be found in `requirements.txt`

## Installation

To get started, clone the repository and install the necessary dependencies:

```bash
git clone https://github.com/yourusername/multilingual-ner.git
cd multilingual-ner
pip install -r requirements.txt

## Dataset Link
https://drive.google.com/drive/folders/1r_SChmmfc8eA_AzuvBa6nkBbb7sj4fSV?usp=share_link
