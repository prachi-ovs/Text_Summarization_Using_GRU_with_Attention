# News Articles Summarizations 
Using Bi-directional GRU with Attention mechanism

## Overview
A sequence2sequence Text Summarization model to generate Abstractive summaries of news articles using GRU encoder-decoder and Attention.

## Introduction
Text Summarization is one of those Natural Language Processing (NLP) applications which is sure to have a major impact on our day to day lives.
Text summarization can broadly be divided into two categories: 
   
   1) **Extractive Summarization**: These methods rely on extracting several parts, such as phrases and sentences, from a piece of text and stack them together to create a summary. Therefore, identifying the right sentences for summarization is of utmost importance in an extractive method.
   
   2) **Abstractive Summarization**: These methods use advanced NLP techniques to generate an entirely new summary. Some parts of this summary may not even appear in the original text.
 
## Model Details
The model was run for 24 epochs and the best performing training epoch is saved as the final model. 


The *Encoder* takes a sequence of text as input and produces a list of hidden states in each time step. The list of hidden layers is the input to the *Decoder* along with the token *sos* (to indicate start of statement) and hidden states. Attention takes the current *decoder’s* hidden state and the list of *encoder* hidden states to calculate the Attention score and creates a context vector based on this score. The context vector and the *decoder* output are concatenated and passed to a *fully connected feedforward layer* to generate the output. These steps are repeated until either the maximum sentence length is achieved or the *eos* is predicted.

## Files
The different files present in the repository are listed below with their individual uses:

    Data --> Folder used for storing the training and testing datasets along with the raw data
    models --> Folder with Ipython notebooks for different models used (simple RNN vs GRU with dropout)
    requirements --> text file containing all the required libraries 
                    To install using `pip3 install -r requirements.txt`

## Best Results
The training and testing loss and PPL are:

Data Set| Loss |  PPL
--- | --- | ---
Training | 2.264 | 9.618
Testing |  3.265 | 26.191
