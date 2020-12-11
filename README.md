# embeddings

In this project I'm exploring some NLP techniques. 
1. Document similarity (use case: recommend movies)
2. Text classification using pretrained word vectors (use case: article labeling)

I'm using Google's pretrained word2vec model that contains 3 million words.

## Document similarity

Calculating cosine similarity between vectors:
- CountVectorizer and TfidfVectorizer
- word2vec word embeddings aggregated to sentence vectors
- doc2vec (todo)

## Text classification

(1) Using sentence vectors as input to trees ensembles and (2) word2vec vectors as input to neural network's Embedding() layer. 

Scoreboard:
1. Neural net with embedding layer with LSTM: 92.76%
2. Neural net with embedding layer w/o LSTM: 91.53%
3. Random forest using sentence vectors: 89.59%

Clear winner is the **bidirectional LSTM model with pretrained word vectors in embedding layer**

biLSTM model's confusion matrix:

                        PREDICTED                          
                        0 = computers 1 = baseball 2 = medicine
    TRUE 0 = computers           158            7            5
         1 = baseball              4          183           15
         2 = medicine              8            2          185


<img src='https://www.i2tutorials.com/wp-content/media/2019/05/Deep-Dive-into-Bidirectional-LSTM-i2tutorials.jpg' width=400>
