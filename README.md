# Hong-Kong-Protest-News-Classification

Detect differnent journalistic tones and viewpoints based on Hong Kong protest news from Mainland China and U.S. newspaper by Machine Learning models and NLP technologies. 

Mainland China Newspaper(English Version): China Daily, People's Daily, Xinhua Agent

U.S. Newspaper: Wall Street Journal, New York Times, Washington Post

Team Members:

Michael Siebel, Junchi Tian, Bixuan Huang

![image](https://github.com/Junchi0905/Hong-Kong-Protest-News-Classification/blob/master/Images/news_image.png)
![image](https://github.com/Junchi0905/Hong-Kong-Protest-News-Classification/blob/master/Images/news_image_.png)

# Goal

The goal of this project is to test a variety of NLP techniques in order to see which combination of techniques can best classify 
each newspaper’s country of origin. This classification is attempted on one topic to evaluate how text pre-processing can detect different, possibly nationalistic, tones (i.e., journalistic attitudes). The inspiration for this project was in part Müller, Porcaro 
and von Nordheim (2018), who used topic modeling across four European countries’ newspapers in order to identify where each country 
placed blame regarding the 2008 economic recession. We instead chose to set-up a classification design in which the journalist writings on the 2019 Hong Kong protests were classified by their country of origin—Mainland China or the U.S. 

# Background
We know that U.S. and Chinese newspapers largely take a different view on the Hong Kong Protests with U.S. newspapers largely framing 
it in terms of protests for democracy and Chinese newspapers focusing on the violence of the protesters. Our goal is to determine which
parameters, primarily within a bag of words methodology, can best identify these differences. We seek to identify word context using 
word frequency, TF-IDF, sentiment analysis, topic identification and varying n-grams. We also conclude with which combination of text pre-processing 
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

![image](https://github.com/Junchi0905/Hong-Kong-Protest-News-Classification/blob/master/Images/Modeling_Image.png)
![image](https://github.com/Junchi0905/Hong-Kong-Protest-News-Classification/blob/master/Images/compare.png)

# References

* Müller, H., Porcaro, G., & von Nordheim, G. (2018). Tales from a crisis: diverging narratives of the euro area. Polity Contribution, Bruegel.

* Brownlee, J. (2017). A gentle introduction to the bag-of-words model. Retrieved from https://machinelearningmastery.com/gentle-introduction-bag-words-model/

* Çano, E., and Maurizio, M. (2019.) Word embeddings for sentiment analysis: A comprehensive empirical survey. ArXiv abs/1902.00753.

* Satapathy, R., Guerreiro, C., Chaturvedi, I., and Cambria, E. (2017). Phonetic-based microtext normalization for twitter sentiment analysis. In 2017 IEEE International Conference on Data Mining Workshops (ICDMW). IEEE: 407-413.

* Silge, J., and Robinson, D. (2018). Analyzing word and document frequency: TF-IDF. In Text Mining with R: A Tidy Approach. Retrieved from https://www.tidytextmining.com/tfidf.html

