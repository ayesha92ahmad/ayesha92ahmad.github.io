---
layout: post
comments: true
title:  "How to compare maturity of the blogs of a teenager and an adult"
excerpt: "Hint: NLTK!"
date:   2017-10-01 22:00:00
tags:
- NLTK
- Python
- Bigrams
- Trigrams
- Natural language processing
- Corpus Statistics
---

Hello there!

I'm back with another [assignment](https://github.com/ayesha92ahmad/blog-comparison-teen-middleaged).
The task at hand was to choose any two sufficiently different documents and perform comparisons on them. The problem statement was to be self selected and later answered after the analysis.


## Problem statement
Comparison of the maturity levels of teenagers and adults in their 40s by instrumenting their vocabulary and topics that they choose for writing.

## Data Collection
I chose the data from [Blog Authorship Corpus](http://u.cs.biu.ac.il/~koppel/BlogCorpus.htm).
Blog Authorship Corpus is gathered from Blogger.com in 2004. For my analysis, authors from two age groups (teens and adults in their 40’s) were chosen to be compared. The data on the website is present as XML files for each author. For data collection and extraction, I wrote a Python script to extract blog articles for 3 different authors from the XML for each age group and combined in the text file to create two documents.

The following is the code used for blog extraction:


```Python
import sys
import xmltodict
from bs4 import BeautifulSoup as Soup


def splitXML(infile, outfile):
    handler = open(infile).read()
    soup = Soup(handler,"lxml")
    file_object  = open(outfile, "w")
    for message in soup.findAll('post'):
        file_object.write(message.getText())
    file_object.close()

if len(sys.argv)!=3:
    if len(sys.argv)!=2:
        print("no input or output file")
    else:
        splitXML(sys.argv[1], "outfile.txt")
else:
    splitXML(sys.argv[1], sys.argv[2])
```

The script can be run on terminal by using the following command:
```
python createdoc.py <input xml file> <output txt file>
```
Later, I combined the contents from each txt file manually because there were only 3 files to be combined.


## Procedure

I performed the regular steps to first get the tokens, removed the stop words, and finally get the most common frequencies. The code is present with the output on my [github page](https://github.com/ayesha92ahmad/blog-comparison-teen-middleaged). Feel free to check it out.

## Procedure

1. Tokenization: It is the task of breaking a document into pieces called tokens by using space or other punctuation marks as delimiters.
2. Conversion to lower case: This is done to remove the case sensitivity. So that ‘A’ is not different from ‘a’.
3. Filtration of non-alphabets: This process helps in making sure that the words are made up of mostly alphabets.
4. Filtration of stop-words using the 'Smart.english.stop': This process helps in removing common English words that might cause a bias in the Natural language understanding. Eg. a, an, the, in, on, under are removed from the analysis as they are likely to occur in most documents and they do not help in understanding what is discussed in the document. Stop words list has been modified for the purpose of improving the quality of analysis.
5.	Word frequencies:
    1.	This shows the number of occurrences of words in the document, after arranging it in decreasing order of frequencies.
    1.	In NLTK, we obtain frequency by using FreqDist class from nltk library and feeding the preprocessed words into that.
    1.	We then pick out most common by using the method most common from the FreqDist class.
6.	Bigram frequencies:
    1.	This shows the percentage of time two words occur together in decreasing order
    1.	We use nltk.collocations.BigramAssocMeasures() to find this measure.
    And then use attribute raw_freq to get frequency
7.	Bigram PMI:
    1.	This shows the probability of the second word given the first.
    1.	We use nltk.collocations.BigramAssocMeasures() to find this measure.
    1.	And then can be displayed by using the pmi attribute of the object.
8. Bigram PMI:
    1.	This shows the probability of the second word given the first.
    1.	We use nltk.collocations.BigramAssocMeasures() to find this measure.
    1.	And then can be displayed by using the pmi attribute of the object.
9.	Trigram frequencies:
    1.	This shows the percentage of time three words occur together in decreasing order
    1.	We use nltk.collocations.TrigramAssocMeasures() to find this measure.
    1. And then use attribute raw_freq to get frequency
10.	Trigram PMI:
    1.	This shows the Joint probability of all 3 over individual probabilities of all 3.
    1.	We use nltk.collocations.BigramAssocMeasures() to find this measure.
    1.	And then can be displayed by using the pmi attribute of the object.



## Observation:

Since the blogs are written in colloquial language, some items in the list are not actual words in the dictionary. Eg. The following are bigrams with their frequency for two examples from the teen bigram frequencies
(('meow', 'meow'), 0.0002949147252640274)
(('heh', 'heh'), 0.00025053435398643105)

As you can see, these are high scores. But these aren’t real English words. Meow is the sound of the cat and heh heh is the sound of laughter. However, they are important in this analysis as they show how teenager is different from an adult whose frequency list contains more mature use of English language.

(From the class slides)
Bigram frequency is the percentage occurrence of the bigram in the corpus
Mutual Information computes probability of two words occurring in sequence

We get different list when we score the bigrams by frequency as opposed to PMI.

It is seen that the adults talk about mature topics such as politics, recipes, people etc. Whereas teenagers talk about their day to day activities, current artists, actors etc.
From the top frequency words under adults we see “people”, “Iraq”, “war”, “America” etc. whereas the top frequency words under teenagers we see “yeah”, “today”, “good”, “lol”, “meow”, “haha”.

There is a clear difference in the frequent usage of words. The teens show an immature writing style using haha and lol which can be shown by different word like “good” +” feel” as seen in the adult frequency list.
For teens, the top frequency bigrams-

'meow', 'meow'
'night', 'blog'
'ya', 'tomorrow'
'meow', 'moo'
'ate', 'dinner'
'eat', 'lunch'

Whereas from the top frequency bigrams in adults we see  
'united', 'states'
'abu', 'ghraib'
'saddam', 'hussein'
'middle', 'east'
'michael', 'moore'
'good', 'news'
'saudi', 'arabia'
'bush', 'administration'

Again, there is a sharp difference between the usage of words and words that frequently are used together.  While adults list shows a political presence, the teens list shows a record of activities such as eating or cat sounds.

From the top pmi bigrams for teens we see

'keanu', 'reeves'
'los', 'angeles'
'shifty', 'troublemaker'
'sledge', 'hammer'
'ferris', 'bueller'

Whereas from the top pmi bigrams for adults we see
'piano', 'bench'
'te', 'tiare'
'bryn', 'mawr'
'clam', 'chowder'
'rocket', 'propelled'
'kofi', 'annan'

There is a difference in the topics chosen by the teens and that chosen by adults. While the high PMI scored bigrams for teens shows Keanu reeves, who is a Canadian actor and Ferris Bueller who is an iconic “shifty troublemaker”, the high PMI scored bigrams for adults shows Bryn Mawr, a college for women and Kofi Annan, who served as the seventh Secretary-General of the United Nations from January 1997 to December 2006.

## Conclusion

From the examples above it is very clear that the adults write about mature topics as opposed to teens who write about their day to day activities or lighter topics. Not just that, the vocabulary and usage of English language of adults are far more superior to teens.

What do you think about my analysis? Do leave your feedback in the comments section!
