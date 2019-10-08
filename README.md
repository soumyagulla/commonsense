## The main objective of this project is to find the commonsense validation and evaluation of the semeval task 2020 for Task A.
Given a set of two sentences, this project finds which sentence makes sense and which sentence does not makes sense.
For instance consider two sentences sentence 1 : he put a turkey into the fridge sentence 2 : he put an elephant into the fridge
Out of these two sentences sentence 1 makes sense and it has to be identified as the correct sentence that makes sense.


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

