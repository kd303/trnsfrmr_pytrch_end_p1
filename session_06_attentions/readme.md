## Session 6: Attention Models in Sequence to Sequence models

# Data Sets
## 1. [Carnegie Mellon Q&A](http://www.cs.cmu.edu/~ark/QA-data/) - licensed as stated in original work GNU & CC ##

    - [Data v 1.2](http://www.cs.cmu.edu/~ark/QA-data/data/Question_Answer_Dataset_v1.2.tar.gz)
    - [Read Me](http://www.cs.cmu.edu/~ark/QA-data/data/README.v1.2)
   
    ### Description: 
          Primarily it is a Question answer dataset, where the Q/A are derived from wiki pedia article, with difficulty rating given for each article
    
 ## 2. [Quora dataset](https://quoradata.quora.com/First-Quora-Dataset-Release-Question-Pairs) ##
    - [Data set link](http://qim.fs.quoracdn.net/quora_duplicate_questions.tsv) 
    
    ### Description:
        This basically derives the work where two questions are compared to see whether they are same or not
        - Ground truth labels contain some amount of noise and they are not guranteed to be different then actual.
        Q&A dataset containing 6 columns namely
            - id - id of the record
            - qid1 - id of question 1
            - qid2 - id of question 2
            - Question 1 - text for question 1
            - Question 2 - text for question 2
            - is duplicate - whether the question is sementically duplicate or not - 1 - same, 0 - different
