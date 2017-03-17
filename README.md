# Topic Modelling
Topic Modelling using LDA to understand the subtopics in reviews

0. json_to_csv.py : converts json file from /data folder and saves it back as csv in the same folder.

1. loading_reviews.py : Loads the business,users and reviews file and process it by aplying various filters to reduce the size of reviews to handle
   2.1 Business are filtered for Restaurants that are open. Cities with more number of restaurants are identified and only Restaurants in those cities are taken for analysis.
   2.2 Reviews that have atleast one useful vote are considered

2. preprocessing.py : Does linguistic processing of review text like 
   3.1 stopword removal
   3.2 remove special characters
   3.3 pos tagging
   3.4 lemmatization
   3.5 filter for tokens that have only 'NN'&'NNS', i.e Noun singular and plural

   after preprocessing step each review is represented by a set of tokens ,that is a noun.

3. word2vec.py : uses gensim library to perform LDA on processed reviews and store the resulting model to local directory

4. nmf.py : Performs topic modelling using Non-Negative Matrix Factorization.

5. validation.py : Analyse the model results by listing the words per topic.

6. classifier.py : classifies any new review submitted through the LDA model trained by using Gensim.

7. cofigurations.py : Conatins all file related configurations .This file must be changed based on your data location.By Default it looks for files /data location form the current directory. 

7. Dockerfile : contains the instructions to create a docker image.
