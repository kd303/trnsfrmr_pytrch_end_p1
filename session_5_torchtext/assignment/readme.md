## Assignment 

### Running [DBPedia](/session_5_torchtext/assignment/Assignment_DBPedia_torchtext.ipynb) classification using EmbeddingBag and simple neural net


Here are the training accuracry

```
| epoch   1 |   500/ 8313 batches | accuracy    0.697
| epoch   1 |  1000/ 8313 batches | accuracy    0.909
| epoch   1 |  1500/ 8313 batches | accuracy    0.938
| epoch   1 |  2000/ 8313 batches | accuracy    0.954
| epoch   1 |  2500/ 8313 batches | accuracy    0.958
| epoch   1 |  3000/ 8313 batches | accuracy    0.960
| epoch   1 |  3500/ 8313 batches | accuracy    0.965
| epoch   1 |  4000/ 8313 batches | accuracy    0.968
| epoch   1 |  4500/ 8313 batches | accuracy    0.967
| epoch   1 |  5000/ 8313 batches | accuracy    0.970
| epoch   1 |  5500/ 8313 batches | accuracy    0.969
| epoch   1 |  6000/ 8313 batches | accuracy    0.971
| epoch   1 |  6500/ 8313 batches | accuracy    0.974
| epoch   1 |  7000/ 8313 batches | accuracy    0.973
| epoch   1 |  7500/ 8313 batches | accuracy    0.973
| epoch   1 |  8000/ 8313 batches | accuracy    0.973
-----------------------------------------------------------
| end of epoch   1 | time: 52.93s | valid accuracy    0.975 
-----------------------------------------------------------
| epoch   2 |   500/ 8313 batches | accuracy    0.979
| epoch   2 |  1000/ 8313 batches | accuracy    0.979
| epoch   2 |  1500/ 8313 batches | accuracy    0.980
| epoch   2 |  2000/ 8313 batches | accuracy    0.980
| epoch   2 |  2500/ 8313 batches | accuracy    0.980
| epoch   2 |  3000/ 8313 batches | accuracy    0.981
| epoch   2 |  3500/ 8313 batches | accuracy    0.980
| epoch   2 |  4000/ 8313 batches | accuracy    0.982
| epoch   2 |  4500/ 8313 batches | accuracy    0.983
| epoch   2 |  5000/ 8313 batches | accuracy    0.979
| epoch   2 |  5500/ 8313 batches | accuracy    0.980
| epoch   2 |  6000/ 8313 batches | accuracy    0.981
| epoch   2 |  6500/ 8313 batches | accuracy    0.982
| epoch   2 |  7000/ 8313 batches | accuracy    0.982
| epoch   2 |  7500/ 8313 batches | accuracy    0.981
| epoch   2 |  8000/ 8313 batches | accuracy    0.979
-----------------------------------------------------------
| end of epoch   2 | time: 53.86s | valid accuracy    0.979 
-----------------------------------------------------------
| epoch   3 |   500/ 8313 batches | accuracy    0.985
| epoch   3 |  1000/ 8313 batches | accuracy    0.986
| epoch   3 |  1500/ 8313 batches | accuracy    0.985
| epoch   3 |  2000/ 8313 batches | accuracy    0.986
| epoch   3 |  2500/ 8313 batches | accuracy    0.985
| epoch   3 |  3000/ 8313 batches | accuracy    0.985
| epoch   3 |  3500/ 8313 batches | accuracy    0.985
| epoch   3 |  4000/ 8313 batches | accuracy    0.984
| epoch   3 |  4500/ 8313 batches | accuracy    0.985
| epoch   3 |  5000/ 8313 batches | accuracy    0.986
| epoch   3 |  5500/ 8313 batches | accuracy    0.986
| epoch   3 |  6000/ 8313 batches | accuracy    0.986
| epoch   3 |  6500/ 8313 batches | accuracy    0.986
| epoch   3 |  7000/ 8313 batches | accuracy    0.986
| epoch   3 |  7500/ 8313 batches | accuracy    0.985
| epoch   3 |  8000/ 8313 batches | accuracy    0.985
-----------------------------------------------------------
| end of epoch   3 | time: 54.72s | valid accuracy    0.979 
-----------------------------------------------------------
| epoch   4 |   500/ 8313 batches | accuracy    0.990
| epoch   4 |  1000/ 8313 batches | accuracy    0.990
| epoch   4 |  1500/ 8313 batches | accuracy    0.989
| epoch   4 |  2000/ 8313 batches | accuracy    0.989
| epoch   4 |  2500/ 8313 batches | accuracy    0.989
| epoch   4 |  3000/ 8313 batches | accuracy    0.991
| epoch   4 |  3500/ 8313 batches | accuracy    0.990
| epoch   4 |  4000/ 8313 batches | accuracy    0.990
| epoch   4 |  4500/ 8313 batches | accuracy    0.990
| epoch   4 |  5000/ 8313 batches | accuracy    0.989
| epoch   4 |  5500/ 8313 batches | accuracy    0.990
| epoch   4 |  6000/ 8313 batches | accuracy    0.989
| epoch   4 |  6500/ 8313 batches | accuracy    0.991
| epoch   4 |  7000/ 8313 batches | accuracy    0.990
| epoch   4 |  7500/ 8313 batches | accuracy    0.990
| epoch   4 |  8000/ 8313 batches | accuracy    0.989
-----------------------------------------------------------
| end of epoch   4 | time: 55.17s | valid accuracy    0.981 
-----------------------------------------------------------
| epoch   5 |   500/ 8313 batches | accuracy    0.990
| epoch   5 |  1000/ 8313 batches | accuracy    0.990
| epoch   5 |  1500/ 8313 batches | accuracy    0.990
| epoch   5 |  2000/ 8313 batches | accuracy    0.990
| epoch   5 |  2500/ 8313 batches | accuracy    0.989
| epoch   5 |  3000/ 8313 batches | accuracy    0.991
| epoch   5 |  3500/ 8313 batches | accuracy    0.989
| epoch   5 |  4000/ 8313 batches | accuracy    0.990
| epoch   5 |  4500/ 8313 batches | accuracy    0.990
| epoch   5 |  5000/ 8313 batches | accuracy    0.990
| epoch   5 |  5500/ 8313 batches | accuracy    0.991
| epoch   5 |  6000/ 8313 batches | accuracy    0.990
| epoch   5 |  6500/ 8313 batches | accuracy    0.990
| epoch   5 |  7000/ 8313 batches | accuracy    0.991
| epoch   5 |  7500/ 8313 batches | accuracy    0.990
| epoch   5 |  8000/ 8313 batches | accuracy    0.990
-----------------------------------------------------------
| end of epoch   5 | time: 54.54s | valid accuracy    0.981 
-----------------------------------------------------------
| epoch   6 |   500/ 8313 batches | accuracy    0.990
| epoch   6 |  1000/ 8313 batches | accuracy    0.990
| epoch   6 |  1500/ 8313 batches | accuracy    0.990
| epoch   6 |  2000/ 8313 batches | accuracy    0.991
| epoch   6 |  2500/ 8313 batches | accuracy    0.989
| epoch   6 |  3000/ 8313 batches | accuracy    0.990
| epoch   6 |  3500/ 8313 batches | accuracy    0.991
| epoch   6 |  4000/ 8313 batches | accuracy    0.991
| epoch   6 |  4500/ 8313 batches | accuracy    0.991
| epoch   6 |  5000/ 8313 batches | accuracy    0.990
| epoch   6 |  5500/ 8313 batches | accuracy    0.990
| epoch   6 |  6000/ 8313 batches | accuracy    0.991
| epoch   6 |  6500/ 8313 batches | accuracy    0.991
| epoch   6 |  7000/ 8313 batches | accuracy    0.990
| epoch   6 |  7500/ 8313 batches | accuracy    0.990
| epoch   6 |  8000/ 8313 batches | accuracy    0.991
-----------------------------------------------------------
| end of epoch   6 | time: 54.01s | valid accuracy    0.981 
-----------------------------------------------------------
| epoch   7 |   500/ 8313 batches | accuracy    0.992
| epoch   7 |  1000/ 8313 batches | accuracy    0.992
| epoch   7 |  1500/ 8313 batches | accuracy    0.991
| epoch   7 |  2000/ 8313 batches | accuracy    0.991
| epoch   7 |  2500/ 8313 batches | accuracy    0.991
| epoch   7 |  3000/ 8313 batches | accuracy    0.991
| epoch   7 |  3500/ 8313 batches | accuracy    0.991
| epoch   7 |  4000/ 8313 batches | accuracy    0.991
| epoch   7 |  4500/ 8313 batches | accuracy    0.990
| epoch   7 |  5000/ 8313 batches | accuracy    0.991
| epoch   7 |  5500/ 8313 batches | accuracy    0.990
| epoch   7 |  6000/ 8313 batches | accuracy    0.991
| epoch   7 |  6500/ 8313 batches | accuracy    0.991
| epoch   7 |  7000/ 8313 batches | accuracy    0.990
| epoch   7 |  7500/ 8313 batches | accuracy    0.991
| epoch   7 |  8000/ 8313 batches | accuracy    0.991
-----------------------------------------------------------
| end of epoch   7 | time: 53.21s | valid accuracy    0.982 
-----------------------------------------------------------
| epoch   8 |   500/ 8313 batches | accuracy    0.991
| epoch   8 |  1000/ 8313 batches | accuracy    0.991
| epoch   8 |  1500/ 8313 batches | accuracy    0.991
| epoch   8 |  2000/ 8313 batches | accuracy    0.991
| epoch   8 |  2500/ 8313 batches | accuracy    0.991
| epoch   8 |  3000/ 8313 batches | accuracy    0.990
| epoch   8 |  3500/ 8313 batches | accuracy    0.991
| epoch   8 |  4000/ 8313 batches | accuracy    0.990
| epoch   8 |  4500/ 8313 batches | accuracy    0.992
| epoch   8 |  5000/ 8313 batches | accuracy    0.991
| epoch   8 |  5500/ 8313 batches | accuracy    0.992
| epoch   8 |  6000/ 8313 batches | accuracy    0.991
| epoch   8 |  6500/ 8313 batches | accuracy    0.991
| epoch   8 |  7000/ 8313 batches | accuracy    0.991
| epoch   8 |  7500/ 8313 batches | accuracy    0.990
| epoch   8 |  8000/ 8313 batches | accuracy    0.990
-----------------------------------------------------------
| end of epoch   8 | time: 52.99s | valid accuracy    0.982 
-----------------------------------------------------------
| epoch   9 |   500/ 8313 batches | accuracy    0.991
| epoch   9 |  1000/ 8313 batches | accuracy    0.990
| epoch   9 |  1500/ 8313 batches | accuracy    0.990
| epoch   9 |  2000/ 8313 batches | accuracy    0.991
| epoch   9 |  2500/ 8313 batches | accuracy    0.991
| epoch   9 |  3000/ 8313 batches | accuracy    0.992
| epoch   9 |  3500/ 8313 batches | accuracy    0.990
| epoch   9 |  4000/ 8313 batches | accuracy    0.991
| epoch   9 |  4500/ 8313 batches | accuracy    0.990
| epoch   9 |  5000/ 8313 batches | accuracy    0.992
| epoch   9 |  5500/ 8313 batches | accuracy    0.991
| epoch   9 |  6000/ 8313 batches | accuracy    0.991
| epoch   9 |  6500/ 8313 batches | accuracy    0.991
| epoch   9 |  7000/ 8313 batches | accuracy    0.991
| epoch   9 |  7500/ 8313 batches | accuracy    0.991
| epoch   9 |  8000/ 8313 batches | accuracy    0.991
-----------------------------------------------------------
| end of epoch   9 | time: 54.61s | valid accuracy    0.981 
-----------------------------------------------------------
```
