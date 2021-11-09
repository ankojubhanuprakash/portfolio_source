# Encode Text Data


## Bag of Words
Bag of words is method to represent raw text data in a strucutred format to a machine learning model. 
Bag of words method constructs Vocabulary from the given corpus, and represents the text data as a vecotor of size of 
the constructed vocabulary, with a number indicating the count of occurence of a word, that appeared in the sentecne.

Example - 
1. "John likes to watch movies. Mary likes movies too."
2. "Mary also likes to watch football games."

Vocabulary - 
"John","likes","to","watch","movies","Mary", "too", "also","football","games"

Representation - 

1. "John likes to watch movies. Mary likes movies too." is represented as [1, 2, 1, 1, 2, 1, 1, 0, 0, 0]
2. "Mary also likes to watch football games." is represented as [0, 1, 1, 1, 0, 1, 0, 1, 1, 1]

Limitation - 
1. As the vocabulary size increases, the lenght of vecotr increases, leading to increase in computational cost.
2. Context of the sentence is not captured, by ignoreing the word order

Implementation - 


## TF-IDF

In bag of Words, we have seen that elements in the vecotr represents the number of times the word appeared in the sentence.
Instead of count, TF-IDF is alternative way to construct vectors that yields better results.

"A problem with scoring word frequency is that highly frequent words start to dominate in the document (e.g. larger score),
but may not contain as much “informational content” to the model as rarer but perhaps domain specific words."
(https://machinelearningmastery.com/gentle-introduction-bag-words-model/)

Definition - 

Term Frequency: is a scoring of the frequency of the word in the current document.
![image](https://user-images.githubusercontent.com/40142772/140699303-b3169b23-e220-42b3-9124-0ae096dab76f.png)
where ft,d is the raw count of a term in a document, i.e., the number of times that term t occurs in document d. 

Inverse Document Frequency: is a scoring of how rare the word is across documents.
![image](https://user-images.githubusercontent.com/40142772/140699413-32896b0a-26b4-41b4-a468-5cc87a84ff90.png)
N: total number of documents in the corpus $${\displaystyle N={|D|}}N = {|D|}
{\displaystyle |\{d\in D:t\in d\}|} |\{d \in D: t \in d\}| : number of documents where the term {\displaystyle t}t appears
(i.e., {\displaystyle \mathrm {tf} (t,d)\neq 0} \mathrm{tf}(t,d) \neq 0). If the term is not in the corpus, this will lead to a division-by-zero.
It is therefore common to adjust the denominator to {\displaystyle 1+|\{d\in D:t\in d\}|}1 + |\{d \in D: t \in d\}|.$$

Then tf–idf is calculated as
![image](https://user-images.githubusercontent.com/40142772/140699512-c34fb166-1bd4-47bc-9d4c-949596194216.png)

Example - 

References - 
 1. https://en.wikipedia.org/wiki/Bag-of-words_model
 2. https://machinelearningmastery.com/gentle-introduction-bag-words-model/




