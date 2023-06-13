# Language Translator Model Using Encoder And Decoder

Here, I am building a flexible train and predict/inference process where Model should handle variable size of input/output and with high accuracy.
Enoder encodes the sequence input into a new representation. This representation is called Context Vector. Decoder decodes the Context Vector into output sequence

I am using Teacher forcing in which during training, decoder receives the correct output from the training set as the previously decoded result to predict the next output. However, during inference decoder receives the previously decoded result to predict the next output. This improves training process.

Steps :-

1. Import Dependanices
2. Import dataset for training
3. Cleaning data
4. Tokenization and Vectorization
5. Pad Sequence and Masking: First, We will apply Padding to the input and output datasets. Then, we will append the Masking layer to the Encoder-Decoder model to efficiently process the padded data
6. Design Encoder & Decoder Using LSTM Layers:
Decoder produces the output sequence one by one. For each output, the decoder consumes a context vector and an input.
The initial context vector is created by the encoder. The initial input is a special symbol i.e. <start> for decoder to make it start.
Using initial context and initial input, decoder will generate the first output.
  
For the next output, decoder will use its current state as the context vector, we (the teacher) will provide the correct output to the decoder as input
8. Train model with 25 epochs
9. Build reference and Predictions:
For variable output sequence size, we will modify the decoder such that it will work in a loop and stop generating output when a condition is met. This condition  can be in satisfied in two ways:
(i) If the decoder generated the maximum number of outputs defined by the user, *or*
(ii) If the decoder generated a special "STOP" symbol
