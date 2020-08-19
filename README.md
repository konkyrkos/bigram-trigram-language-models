# Language Models - Bigrams - Trigrams

This repository provides my solution for the 1st Assignment for the course of Text Analytics for the MSc in Data Science at Athens University of Economics and Business. 

In the project i have implemented a bigram and a trigram language model for word sequences using Laplace smoothing. 

As corpus for this project I have choosen the Brown corpus which was the first million-word electronic corpus of English, created in 1961 at Brown University.

The models are trained on a training subset of a corpus.

In the vocabulary are only included words that occur at least 10 times in the training subset and also the same vocabulary is used in bot the bigram and trigram models.

All out-of-vocabular (OOV) words are replaces by a special token
*UNK*. 

Each sentence is assumed to start with the pseudo-token *start* (or two pseudotokens *start1*, *start2* for the trigram model) and to end with the pseudo-token *end*.

## Comparing probabilities

I compare the log-probabilities that the trained models return when given (correct) example sentences from the test subset vs. (incorrect) sentences of the same length (in words) consisting of randomly selected vocabulary words. 

## Cross-entropy & Perplexity

I estimate the language cross-entropy and perplexity of the models on a test subset of the corpus, treating the entire test subset as a single sequence, with *start* (or *start1*, *start2*)
at the beginning of each sentence, and *end* at the end of each sentence. Probabilities of the form P(*start*|…) (or P(*start1*|…) or P(*start2*|…)) are note included in the computation of cross-entropy and perplexity, but probabilities of the form
P(*end*|…) are included.

## Combined model

I combine the two models using linear interpolation and check if the combined model performs better in terms of cross-entropy and perplexity. I also tune the λ hyper-parameters on a development subset of the corpus.

## More info

More information about the project can be found in the latex file contained in the project.

