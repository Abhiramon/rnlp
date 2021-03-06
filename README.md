# NLP-Preprocessing

Processes text from a file (or set of files) into relational facts.

Pre-requisites:

- Python 2.7

- nltk version 3.2.1

Usage:

`$ python parseInputCorpus.py -blockSize [n]`

The code will prompt for a file or folder input of text files to convert to relational facts.

The Relations encoded are:

- between block's of size n (i.e. 'n' sentences) and sentences in the blocks.

- between sentences and words in the sentences.

---

The relationships currently encoded are:

1. earlySentenceInBlock - sentence occurs within a third of the block length

2. earlyWordInSentence - word occurs within a third of the sentence length

3. lateSentenceInBlock - sentence occurs after two-thirds of the block length

4. midWayWordInSentence - word occurs between a third and two-thirds of the block length

5. nextSentenceInBlock - sentence that follows a sentence in a block

6. nextWordInSentence - word that follows a word in a sentence in a block

7. sentenceInBlock - sentence occurs in a block

8. wordInSentence - word occurs in a sentence.

9. wordString - the string contained in the word.

10. partOfSpeech - the part of speech of the word.

---

Files contain a toy corpus (`files/`) and an image of a BoostSRL tree for predicting if a word in a sentence is the word "you"

![BoostSRL tree for predicting if a word in a sentence is the word "you."](https://raw.githubusercontent.com/boost-starai/Natural-Language-Processing/master/docs/img/output.png)

The tree says that if the word string contained in word 'b' is "you" then 'b' is the word "you". (This is of course true).
A more interesting inference is the False branch that says that if word 'b' is an early word in sentence 'a' and word 'anon12035' is also an early word in sentence 'a' and if the word string contained in word 'anon12035' is "Thank", then the word 'b' has decent change of being the word "you". (The model was able to learn that the word "you" often occurs with the word "Thank" in the same sentence when "Thank" appears early in that sentence).

Questions: contact kauroy (AT) indiana (DOT) edu
