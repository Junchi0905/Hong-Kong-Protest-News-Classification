# Hong-Kong-Protest-News-Mining
Detect differnent journalistic tones based on Hong Kong protest news from Mainland China and U.S. newspaper by Machine Learning models and NLP technologies 

Team Members:

Michael Siebel, Junchi Tian, Bixuan Huang

# Goal
The goal of this project is to test a variety of NLP techniques in order to see which combination of techniques can best classify 
each newspaper’s country of origin. This classification is attempted on one topic to evaluate how text pre-processing can detect different, possibly nationalistic, tones (i.e., journalistic attitudes). The inspiration for this project was in part Müller, Porcaro 
and von Nordheim (2018), who used topic modeling across four European countries’ newspapers in order to identify where each country 
placed blame regarding the 2008 economic recession. We instead chose to set-up a classification design in which the journalist writings on the 2019 Hong Kong protests were classified by their country of origin—Mainland China or the U.S. 

# Background
We know that U.S. and Chinese newspapers largely take a different view on the Hong Kong Protests with U.S. newspapers largely framing 
it in terms of protests for democracy and Chinese newspapers focusing on the violence of the protesters. Our goal is to determine which
parameters, primarily within a bag of words methodology, can best identify these differences. We seek to identify word context using 
word frequency, TF-IDF, sentiment analysis, topic modeling and varying n-grams. We also conclude with which combination of text pre-processing 
led to better classification scores.

# Evaluation and Modeling
Our goal is to build a binary classifier for balanced data(around 550 articles from Mainland China newspaper 
and 550 from U.S. newspaper). Therefore, we believe a simple accuracy metric should be a valid method of evaluating success. 
We additionally observe whether we are over predicting or under predicting a given country of origin and use an F1 score 
as an alternative measure of success as it provides a harmonic average of precision and recall.

We use Naive Bayes and XGBoost to build models and test each parameter one-by-one, from simple (e.g., term weights) to complex (e.g., word embeddings). 
Therefore, each model contain one parameter change such as changing from a term frequency weight (model 1) to a 
TF-IDF weight (model 2) with the resulting accuracy scores indicating which was better at determining word importance.
After testing all term weights, we will take the “best” parameter and use it in models that vary n-gram combinations of words 
(e.g., uni-gram, bi-gram, and tri-gram combinations). This is, therefore, a sequential process of accepting the best parameters.  

# Works Cited

Müller, H., Porcaro, G., & von Nordheim, G. (2018). Tales from a crisis: diverging narratives of the euro area. Polity Contribution, Bruegel.


