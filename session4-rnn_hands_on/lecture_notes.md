## Important learnings/understanding from Lecture

1. Google's [LaMDA model](https://blog.google/technology/ai/lamda/) for conversation modelling
2. How context is different from memory. LSTM/GRU are example of how memory is represented. We or language dont often rely on memory, whilst it is good to have memory one is worried about context in which he or she talking about. 
3. whilst in session 3 it was understood that we may not be able to learn the summation not possible using scaler number using NN. One can convert the numbers in binary and that converts the problem into non-binary. (it would be interesting to try the earlier example)
4. Embedding layer is entire vocabulary learns about the relationships between the word based on where they appear...
    For example : middle east countries - based on the text taken we can learn various relationship in terms of oil producing, wars, politics, ethinicity and could be multiple context based on whatever context that appears in the text - it could be different dimensions can be learnt (ever wonder how biased our language is and imagine using text of certain issues not representing minority views in the country what will embedding matrix will learn?? )
    
5. For plain RNNs, as we pass the output from one neuron to another - the existing input would have larger impact and the context gets lost from earlier words See the image Representation purpose only (Source TSAI)
 
 ![image](/session4-rnn_hands_on/16.gif)

6. 
