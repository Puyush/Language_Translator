# Language Translator Model Using Encoder And Decoder

Here, I am building a flexible train and predict/inference process where Model should handle variable size of input/output and with high accuracy.
Enoder encodes the sequence input into a new representation. This representation is called Context Vector. Decoder decodes the Context Vector into output sequence

I am using Teacher forcing in which during training, decoder receives the correct output from the training set as the previously decoded result to predict the next output. However, during inference decoder receives the previously decoded result to predict the next output. This improves training process.
