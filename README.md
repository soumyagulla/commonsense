## The main objective of this project is to find the commonsense validation and evaluation of the semeval task 2020 for Task A.
Given a set of two sentences, this project finds which sentence makes sense and which sentence does not makes sense.
For instance consider two sentences:
sentence 1 : 
he put a turkey into the fridge 
sentence 2 : 
he put an elephant into the fridge

Out of these two sentences sentence 1 makes sense and it has to be identified as the correct sentence that makes sense.From the above sentences, "he put a turkey into the fridge" and "he put an elephant into the fridge", the first sentence makes sense and the system is expected to predict this statement as the correct one. Moreover, both the sentences are similar in syntactic structure and they usually differ by few words.For instance, in the above sentences, they only differ by the words "elephant" and "turkey" whereas the rest of the sentences are similar. For common sense validation task, we identify the words that are different in both the correct sentence and against common sense sentence. For instance, in the sentences "he put an elephant into the fridge" and "he put a turkey into the fridge", elephant and turkey are different words and rest of the sentences sound similar. By identifying different words, we get an idea of how the correct statements and against commonsense statements are different from each other.

## BERT:

We explore using Bidirectional Encoder Representations from Transformers (BERT) model to determine the commonsense of the sentences.  BERT is composed to pre-train bidirectional representations from unsupervised data by joining the information from both the left and right contexts. For instance, if we consider a sentence "I want to go bank to make a deposit" to predict accurately the nature of the word "bank" we have to consider both the left and right contexts of the word. This indicates, the bidirectional nature of the BERT that helps to predict the words accurately.We pre-process the data such that it will match the data on which BERT is trained. Text in the data set is moved to lowercase, we tokenized the sentences, removed the stop words such as 'a','an','the', added CLS and SEP tokens at the correct places and words are separated into word pieces. BERT uses "masked language model" which masks some of the words in the input and it is expected to predict the actual word in the place of the masked word mainly depending on the context of the word. For instance, consider the sentence "he put an [Mask] into the fridge"  the model has to predict the missing word whether it is elephant or turkey depending on the context of the words. Along with the Masked Language Model, BERT also uses "Next sentence prediction" for tasks that deals with understanding the relationships between the sentences.  For the pre-trained BERT model, fine tuning can be done by adding one additional output layer to it . For the first sub task validation, perplexities of the sentences are calculated and the one with the lower score is chosen as the correct statement where as the one with higher score is considered as against common sense statement.


## LSTM:

In this work, we are using Long Short Term Memory(LSTM) as our second model to identify the sentence that makes sense from both the sentences given in validation task. LSTM's structure is different from traditional RNN's, which are recurrent as they perform the same task repetitively for each element in the sequence and the computational output is dependent on the previous inputs and also they have a memory unit to capture information about the computations that have been calculated. In theory, RNN's are able to capture long-term dependencies however, in practice they are restricted to look back only few words. This limitation is addressed by LSTM, a special type of RNN and is capable of capturing long-term dependencies. Key of LSTM is the cell state and it is referred as memory unit in LSTM, which makes the decision process of what to keep in and what to remove from the memory. Moreover,LSTM has three gates namely input gate, output gate and forget gate to protect and manage the cell state. 

## Installing
# on windows
pip install -r requirement.txt
# on linux
pip3 install -r requirement.txt


## Training


usage: main.py    [--mode 'train']
                  [--ModelPath 'Model']
                  [--linesToTrain 10000]
                  [--data_sent_path './data_all.csv']
                  [--data_answer_path './taskA_answers_all.csv']
                  [--epochs 3]
                  
## Estimating



usage: main.py    [--mode 'estimate']
                  [--data_sent_path './data_all.csv']
                  [--data_output './']
                  [--n_lines 2000]
                  

## predicting



usage: main.py    [--mode 'predict']
                  [--sentence 'He drinks milk']
                  

## get Accuracy


usage: main.py    [--mode 'getAcc']

## Role of Each Team Member
Indumathy Sandrasekaran: Training and Estimating
Soumya Gulla: Predicting, Estimation and Accuracy

