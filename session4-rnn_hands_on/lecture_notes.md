## Important learnings/understanding from Lecture

1. Google's [LaMDA model](https://blog.google/technology/ai/lamda/) for conversation modelling
2. How context is different from memory. LSTM/GRU are example of how memory is represented. We or language dont often rely on memory, whilst it is good to have memory one is worried about context in which he or she talking about. 
3. whilst in session 3 it was understood that we may not be able to learn the summation not possible using scaler number using NN. One can convert the numbers in binary and that converts the problem into non-binary. (it would be interesting to try the earlier example)
4. Embedding layer is entire vocabulary learns about the relationships between the word based on where they appear...
    For example : middle east countries - based on the text taken we can learn various relationship in terms of oil producing, wars, politics, ethinicity and could be multiple context based on whatever context that appears in the text - it could be different dimensions can be learnt (ever wonder how biased our language is and imagine using text of certain issues not representing minority views in the country what will embedding matrix will learn?? )
    
5. For plain RNNs, as we pass the output from one neuron to another - the existing input would have larger impact and the context gets lost from earlier words See the image Representation purpose only (Source TSAI)
 
 ![image](/session4-rnn_hands_on/16.gif)

6. Understading of LSTM with various gates

7. Batch size and padding - GPU implication (BucketIterator) - why having different length matrix/vecotrs causes issues

8. Embedding layer - basically learns the context in which the embedding is created. For example a word "red" if learnt in a car color good bad may learn differently from whether the sentence indicate whether the color represents danger or not. So embedding layer in a lay terms learns the memory of context, so for same vocabulary for two different task embedding for same word may be very different (*need to test this*)

9. Dimension of embedding layer depends on the size of the dataset (cause number of dimensions requires the word to be used in that many sentences), size of the dimension would also increase the memory size requried to represent a word and eventually a sentence, would fit a smaller batch size on GPU compared to a embedding vector of smaller dimension.

GloVE - dimension 300 dimension
GPT3 - 12888 tokens -> $ 14 mn to train the model !

10. RNN would loose the context over longer sequences but not in that short like 5-6 words. Usually 15-20 words


