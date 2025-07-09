The values by the CountVectorizer are:
My implementation: [[1. 1. 1. 1. 1. 0. 0. 0. 0. 0. 0.], [1. 0. 1. 1. 0. 1. 1. 0. 0. 0. 0.], [1. 1. 0. 0. 0. 1. 0. 1. 1. 1. 1.]]
CountVectorizer by ScikitLearn: [[0 0 0 0 1 0 0 1 1 1], [0 0 0 0 1 1 1 0 0 1], [1 1 1 1 0 1 0 0 1 1]]
The main difference is that CountVectorizer is ignoring single letter words like 'a' and also arranging the words by alphabetical order.
The values by the TfIdfVectorizer are:
My implementation: [[0.34957775 0.45014501 0.45014501 0.34957775 0.59188659 0. 0. 0. 0. 0. 0.], [0.34957775 0. 0.45014501 0.34957775 0. 0.45014501 0.59188659 0. 0. 0. 0.], [0.25171084 0.32412354 0. 0. 0. 0.32412354 0. 0.4261835 0.4261835 0.4261835 0.4261835 ]]
TfIdfVectorizer by ScikitLearn: [[0. 0. 0. 0. 0.4804584 0. 0. 0.63174505 0.4804584 0.37311881], [0. 0. 0. 0. 0.4804584 0.4804584 0.63174505 0. 0. 0.37311881], [0.4261835 0.4261835 0.4261835 0.4261835 0. 0.32412354 0. 0. 0.32412354 0.25171084]]
Again, the main difference is that TfIdfVectorizer is ignnoring single letter words like 'a' and also arranging the words by alphabetical order.
Also, ScikitLearn does not use the conventional TfIdf approach, it first multiplies the raw count of a word in a document with 1 + the logarithm (base e) of the number of documents divided by the number of documents in which the term appears and then uses l2 normalisation (basically dividing all values in the document by the square root of the sum of square of all values in the document) to get the numbers between 0 and 1. (I have implemented the same method and not the conventional method).