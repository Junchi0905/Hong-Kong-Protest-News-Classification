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

This summer, protests broke out in Hong Kong, at first related to an extradition treaty that the protesters viewed as an encroachment of mainland China into the special administrative region of Hong Kong.  U.S. and Chinese newspapers largely take a different view on these protests.  U.S. newspapers are more likely to frame them in terms of protests for democracy, while Chinese newspapers are more likely to focus on the violence of the protesters. Our goal is to determine which parameters, primarily within a bag of words methodology, can best identify these differences. We seek to identify word context using word frequency, TF-IDF, sentiment analysis, topic identification and varying n-grams. We also conclude with which combination of text pre-processing led to better classification scores.

# Modeling

Using this BOW framework, we ran a total of 27 models, in which we varied three parameters: the minimum sparsity threshold, the term weights, and the n-grams.  We attempted three variations of each of the parameters.  Each model was run using a gradient-boosted decision tree with a logistic classifier and a log-likelihood cost function.  Table below displays each model configuration.  

![image](https://github.com/Junchi0905/Hong-Kong-Protest-News-Classification/blob/master/Images/Modeling_Image.png)

These models were preprocessed using conventional methods such as term case transformation, stemming, stopword removal, and setting a maximum sparsity threshold of 90%—meaning that words that appeared in 90% or more of documents were removed under the same logic as stopword removal.  

# Evaluation

We evaluated our models based on their F1-scores.  Using this evaluation metric, we found that classification proved easy for our bag of words technique.  A 1% minimum sparsity threshold proved better than a 5% or 10%, but only by a little.  Moreover, term weights and n-grams made little difference.  Figure 2 shows the nine models run with a 1% minimum sparsity threshold—all containing similar F1-scores ranging from 0.955 to 0.979.  

![image](https://github.com/Junchi0905/Hong-Kong-Protest-News-Classification/blob/master/Images/compare.png)

Our best model configuration included a bigram with binary term weights (i.e., one-hot-encoding) and a 1% minimum sparsity threshold. It contained an F1-score of 0.979.  On our test set, comprise of 331 news articles (30% of our corpus), we had only 7 misclassifications—3 false positives and 4 false negatives.  

# Motivation

Chinese newspapers focused attention to the violence of the protesters and the Hong Kong government’s response.  In doing so, they tended to talk about narrow, day-to-day events and did not link the protest story to wider global politics.  By contrast, U.S. newspapers paid more attention to wider issues and democracy.  Because they linked the protest story to wider US-China relations and global politics, their news contained more variance in content. 

Overall, the similarity between Chinese newspapers is high, which likely improved our ability to distinguish it from U.S. newspapers.  As a result, the model configurations did not vary in their effectiveness.  We find that this corpus cannot meaningfully distinguish between BOW parameters.  This is most likely due to the amount substantively important terms that are unique between the articles’ country of origin.  

# References

* Müller, H., Porcaro, G., & von Nordheim, G. (2018). Tales from a crisis: diverging narratives of the euro area. Polity Contribution, Bruegel.

* Brownlee, J. (2017). A gentle introduction to the bag-of-words model. Retrieved from https://machinelearningmastery.com/gentle-introduction-bag-words-model/

* Çano, E., and Maurizio, M. (2019.) Word embeddings for sentiment analysis: A comprehensive empirical survey. ArXiv abs/1902.00753.

* Satapathy, R., Guerreiro, C., Chaturvedi, I., and Cambria, E. (2017). Phonetic-based microtext normalization for twitter sentiment analysis. In 2017 IEEE International Conference on Data Mining Workshops (ICDMW). IEEE: 407-413.

* Silge, J., and Robinson, D. (2018). Analyzing word and document frequency: TF-IDF. In Text Mining with R: A Tidy Approach. Retrieved from https://www.tidytextmining.com/tfidf.html

