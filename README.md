# text-based-speaker-classification

## Folder Structure
- main.py: Contains the code to run the binary classifier and multi classfier models built in this work
- data : contains All_Seasons.csv with all utterances and characters from the Shourt Park TV show

### Problem Statement

The goal of this work is to classify speakers by identifying predictable patterns based on text dialogues
from a television show, South Park, using feature engineering techniques like Principal Component
Analysis (PCA), Singular Values Decomposition (SVD), and machine learning algorithms like Logistic
Regression, Boosting, Decision Trees, Support Vector Machines (SVMs), and Transfer Learning.

The South Park dataset contains data from 3950 speakers with 70896 dialogues. Building a
classifier to identify dialogues for all the given speakers would be a difficult task with the current
heavily imbalanced dataset, so this work uses the three main characters of the show using multiclass
classification. This task only uses a subset of the given dataset (24553 dialogues). Also I
present my work on the binary classifier to identify whether a dialogue was uttered by one of the
main characters: 24553 utterances, leveraging relevant language patterns from the entire dataset.
Two systems, a multi-class, and a binary classifier, to capture predictable patterns using the machine
learning models are included in this project. I would like to benchmark the models using contextual
embeddings against models using traditional text feature engineering methods such as word2vec.
I hypothesize that a classifier with contextual embeddings as input would perform better since
it would carry information of long-term dependencies and context across the entire training corpus.

The results from this work reveal that the use of sentence transformer(SBERT [1])
embeddings (transfer learning) along with an SVM classifier yields / achieves 68.2% for
the binary problem & 50.4% for the multi-class problem, in terms of classification accuracy.
This comes with an improvement of approximately 10% over a transfer learning
baseline system (SVM classifier) using word2vec text embeddings.

### Dataset
In this work, the dataset that is called -South Park, and it comes with 70896 dialogues uttered
by all the characters. It has 4 important features – ‘Season’, ‘Episode’, ‘Character’, and ‘Line’.
In this work, I aim to do text-based speaker
classification based on the utterances in ‘Line’ and classify a speaker as one out of the closed-set
3950 unique speakers from ‘Character’.
