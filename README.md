# Named Entity Recognition (NER) with HMM and MEMM

![image](https://github.com/SaadElDine/Named-Entity-Recogniotion-Using-HMM-and-MEMM/assets/113860522/5c73f2d3-a099-4f2e-9d58-8e05e305a30a)


## Overview
This project focuses on Named Entity Recognition (NER), which is the task of identifying and classifying named entities in text into predefined categories such as names of persons, organizations, locations, etc. Two models are implemented for NER: Hidden Markov Model (HMM) and Maximum Entropy Markov Model (MEMM).

### HMM
The HMM is a probabilistic model that models sequences of observations. In the context of NER, the observations are words in a sentence, and the hidden states represent the named entity categories. The HMM calculates the most likely sequence of hidden states (named entity tags) given the observed sequence (sentence).

![image](https://github.com/SaadElDine/Named-Entity-Recogniotion-Using-HMM-and-MEMM/assets/113860522/97e6147c-11aa-4984-80ae-76a60016c4e2)


### MEMM
The MEMM is an extension of the HMM that uses a Maximum Entropy classifier to model the transition probabilities between hidden states. Unlike the HMM, which assumes independence between observations, the MEMM considers the entire context of the sentence when predicting named entity tags.

## Code Explanation

### HMM Code
The HMM code consists of the following key components:

- **Initialization**: The model is initialized with the transition probabilities, emission probabilities, and initial state probabilities.
- **Forward Algorithm**: This algorithm calculates the probability of observing a sequence of words given the model parameters.
- **Decoding**: The model predicts the named entity tags for a given sentence using a greedy decoding approach and also Viterbi Algorithm: This algorithm calculates the most likely sequence of hidden states (named entity tags) given the observed sequence (sentence).

### MEMM Code
The MEMM code consists of the following key components:

- **Initialization**: The model is initialized with the transition probabilities, emission probabilities, and initial state probabilities, similar to the HMM.
- **Feature Extraction**: Features are extracted for each word in the sentence to predict the named entity tag. This includes word features and tag features from prior words.
- **Training**: The MEMM model is trained using Maximum Likelihood Estimation (MLE) on a corpus of tagged sentences.
- **Decoding**: The model predicts the named entity tags for a given sentence using a greedy decoding approach.

## Usage
To use the HMM and MEMM models for NER, follow these steps:

1. Initialize the models with the desired parameters.
2. Train the models on a corpus of tagged sentences.
3. Use the models to predict named entity tags for new sentences.

Example code:
```python
# Initialize HMM
hmm_model = HMM(transition_prob, emission_prob, initial_prob)

# Initialize MEMM
memm_model = MEMM(dic, decode_type, regex_features)

# Train MEMM model
memm_model.train(corpus)

# Tag a sentence using HMM
hmm_tags = hmm_model.viterbi_decode(sentence)

# Tag a sentence using MEMM
memm_tags = memm_model.greedy_decode(sentence)
