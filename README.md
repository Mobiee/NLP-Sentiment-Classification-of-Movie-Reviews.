# NLP-Sentiment-Classification-of-Movie-Reviews.
Sentiment of Movie Reviews


## DATA

Before starting with Data pre-processing the data itself explored to check if any null values could be
taken care of and analyse the number of unique words in the text and website name columns.
Pre-processing is an important step before training as most texts are taken from the three sites of
Yolo, IMBD and amazon as most of these texts might contain unwanted stop words, special
characters and numbers. To Clean and standardize the data and make it prepared for training a
function was made for cleaning the text column of the data given. In which first all the sentences
text in text columns are normalized by converting all sentences into lower case. Removing numbers,
punctuations, special characters, hyperlinks, white spaces from back and front, and brackets as
these does not have any impact or contributions to sentiment.
Removing stop words: Stop words are the most common words that add little significance to the
context of the text, such as "the," "is," "in," "at," and so on. This step involves importing stop words
from the nltk.corpus library and applying them to the cleaned text as additional steps since this is
sentiment analysis and the word “not” is excluded from the list of removing stop words.
Lemmatization: The process of grouping together the various inflected forms of a word so that they
can be analysed as a single object is known as lemmatization. Lemmatization is similar to stemming
in that it adds meaning to sentences.
Tokenization: Tokenization is the method of breaking down an expression, sentence, or paragraph
into smaller units, such as individual word. These smaller units are referred to as tokens.
Tokenization is accomplished by splitting the text column into tokens using the split process.
Contractions: Handling contractions was another step that was done for cleaning the text data,
which are shortened sentences or syllables or words with apostrophes in them. The contractions are
handled by removing the apostrophes and reformatting them for easy classification of sentiment
(e.g., “didn’t” to “did not”).
In order to decide whether to use unigrams or bigrams the distribution of these ranges were
explored through visualising them as can be seen in figure 1, it shows the top 20 unigrams of the
data before cleaning, which mostly consist of common stop words of “the”, ”and”, ”it”, ”is” which
would make no contribution for sentiment analysis, hence after data cleaning the clean unigrams is
explored as shown in Figure 2, which shows a better result as compared to Figure 1.

<img src="https://github.com/Mobiee/NLP-Sentiment-Classification-of-Movie-Reviews/blob/main/screenshots%20/barchart1.png" width="400" height="300" />

<img src="https://github.com/Mobiee/NLP-Sentiment-Classification-of-Movie-Reviews/blob/main/screenshots%20/barchart2.png" width="400" height="300" />

The distribution of bigrams is also explored, just like unigram before data cleaning, bigrams before
data cleaning mostly consist of stop words. After data cleaning, most of the bi-grams have
understandable meaning for example before cleaning the bigram "of the" would not have
contributed to sentiment analysis but after cleaning the bigram "did not" will contribute to the
classification of sentiment analysis.

<img src="https://github.com/Mobiee/NLP-Sentiment-Classification-of-Movie-Reviews/blob/main/screenshots%20/barchart3.png" width="400" height="300" />

<img src="https://github.com/Mobiee/NLP-Sentiment-Classification-of-Movie-Reviews/blob/main/screenshots%20/barchart4.png" width="400" height="300" />



## Analysis of Predictions for the Classifier
Amongst all the three classifiers which are explored above, all three classifiers have similar
performance but MultinomialNB performs much better by 83.7 % on the validation set and having
the best score of 81.9% through grid search with an alpha value of 0.5. This classifier has a True
positive Rate of 96.5%, False positive rate of 4.2%. a true negative rate of 95.8%, a false negative
rate of 3.5% and an accuracy of 96.14% for Amazon

<img src="https://github.com/Mobiee/NLP-Sentiment-Classification-of-Movie-Reviews/blob/main/screenshots%20/chart5.png" width="400" height="300" />

As for IMDB, this classifier has a true positive rate of 94.3%, a false-positive rate of 4.5%, a true
negative rate of 95.5% and a false-negative rate of 5.8% accuracy of 94.9%


<img src="https://github.com/Mobiee/NLP-Sentiment-Classification-of-Movie-Reviews/blob/main/screenshots%20/chart6.png" width="400" height="300" />

For yelp, this classifier has a true positive rate of 97% and a false-positive rate of 4%, a true negative
rate of 96% and a False-negative rate of 3.3% accuracy 96.4%.

<img src="https://github.com/Mobiee/NLP-Sentiment-Classification-of-Movie-Reviews/blob/main/screenshots%20/chart7.png" width="400" height="300" />


In terms of False positive rate overall Yelp has the lowest False positive rate of 4%, Yelp also had the
lowest false-negative rate of 3.3%, highest true positive rate of 97%, a highest true negative rate of
96% and an accuracy rate of 96.4%. As to why it is performing the best for Yelp might be due to the
nature of the language used in yelp reviews or the number of positive and negative sentiment words
within feature ser of a particular review.
The classifier is also tested on some other texts to observe how well it performs with long positive
and negative sentences.

<img src="https://github.com/Mobiee/NLP-Sentiment-Classification-of-Movie-Reviews/blob/main/screenshots%20/chart8.png" width="400" height="300" />
For long negative and positive sentences also it has an accepted performance as negative sentences
correctly classified with 0.862 probability and positive sentence is correctly classified as positive with
highs probability of 0.93.
