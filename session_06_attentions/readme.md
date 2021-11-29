# Session 6: Attention Models in Sequence to Sequence models

## Data Sets

## Parsing Class a generic class for both Dataset
A common approach take to parse the TSV classes, have created ```dataset_parser``` class to extend what was already done in the class. Appropriate columns are picked from based on the dataset here is the class:
```
class dataset_parser:
    def __init__(self, file_path, MAX_LEN):
        self.file_path = file_path
        self.MAX_LEN = MAX_LEN

    def normalizeString(self, s):
        s = self.unicodeToAscii(s.lower().strip())
        s = re.sub(r"([.!?])", r" \1", s)
        s = re.sub(r"[^a-zA-Z.!?]+", r" ", s)
        return s


    def is_max_length_match(self, p):
        return (len(p[0].split(' ')) < self.MAX_LEN
                and len(p[1].split(' ')) < self.MAX_LEN)

    ## I found some characters which I dont understand, thou shall ignore those.
    def unicodeToAscii(self, s):
        return ''.join(
            c for c in unicodedata.normalize('NFD', s)
            if unicodedata.category(c) != 'Mn'
        )

    def filter_pairs(self, pairs):
        return [p for p in pairs if self.is_max_length_match(p)]

    def parseFile(self, file_type):
        lines = open(self.file_path, encoding='utf-8').read().strip().split('\n')

        # for Quora dataset, ignore rest of the columns
        if file_type == 'QUORA':
            pairs = [[self.normalizeString(l.split('\t')[3]), self.normalizeString(l.split('\t')[4])] for l in lines[1:] if len(l.split('\t')) > 4]
        else:  # CMU
            pairs = [[self.normalizeString(l.split('\t')[1]), self.normalizeString(l.split('\t')[2])] for l in lines[1:] if len(l.split('\t')) > 2]
            # [pair for pair in pairs if len(pair[0].split(' ')) < MAX_LEN and len(pair[1].split(' ')) < MAX_LEN]
        return self.filter_pairs(pairs)
  ```

## 1. [Carnegie Mellon Q&A](http://www.cs.cmu.edu/~ark/QA-data/) - licensed as stated in original work GNU & CC ##
>
- [Data v 1.2](http://www.cs.cmu.edu/~ark/QA-data/data/Question_Answer_Dataset_v1.2.tar.gz)
- [Read Me](http://www.cs.cmu.edu/~ark/QA-data/data/README.v1.2)
   
    ### Description: 
         - Primarily it is a Question answer dataset, where the Q/A are derived from wiki pedia article, with difficulty rating given for each article
         - Here are interested in **2 & 3** from the TSV, hence taking those, ignoring any parsing erros - ideal would be to use ```csv``` module to parse
     ### Sample Code
     ```
           def parseFile(self, file_type):
                lines = open(self.file_path, encoding='utf-8').read().strip().split('\n')

                # for Quora dataset, ignore rest of the columns
                if file_type == 'QUORA':
                    pairs = [[self.normalizeString(l.split('\t')[3]), self.normalizeString(l.split('\t')[4])] for l in lines[1:] if len(l.split('\t')) > 4]
               ** else:  # CMU
                    pairs = [[self.normalizeString(l.split('\t')[1]), self.normalizeString(l.split('\t')[2])] for l in lines[1:] if len(l.split('\t')) > 2]
                    # [pair for pair in pairs if len(pair[0].split(' ')) < MAX_LEN and len(pair[1].split(' ')) < MAX_LEN]
               ** return self.filter_pairs(pairs)
     ```
    
 ## 2. [Quora dataset](https://quoradata.quora.com/First-Quora-Dataset-Release-Question-Pairs) ##
>
- [Data set link](http://qim.fs.quoracdn.net/quora_duplicate_questions.tsv) 
    
    ### Description: 
        This basically derives the work where two questions are compared to see whether they are same or not
        - Ground truth labels contain some amount of noise and they are not guranteed to be different then actual.
        Q&A dataset containing 6 columns namely
            - id - id of the record, qid1 - id of question 1,  qid2 - id of question 2,  Question 1 - text for question 1, Question 2 - text for question 2
            - We are interested in column **4 & 5** we will pick those columns, again ignoring any parsing errors
         
         
         
     ### Sample Code
               def parseFile(self, file_type):
                lines = open(self.file_path, encoding='utf-8').read().strip().split('\n')

                # for Quora dataset, ignore rest of the columns
               **if file_type == 'QUORA':
                    pairs = [[self.normalizeString(l.split('\t')[3]), self.normalizeString(l.split('\t')[4])] for l in lines[1:] if len(l.split('\t')) > 4]
               **else:  # CMU
                    pairs = [[self.normalizeString(l.split('\t')[1]), self.normalizeString(l.split('\t')[2])] for l in lines[1:] if len(l.split('\t')) > 2]
                    # [pair for pair in pairs if len(pair[0].split(' ')) < MAX_LEN and len(pair[1].split(' ')) < MAX_LEN]
               return self.filter_pairs(pairs)
          
            
            
