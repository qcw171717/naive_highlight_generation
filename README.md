# naive_highlight_generation
Uses a naive algorithm for text highlight generation. 

Intuition behind this algorithm: 
The highlight of an article should be the sentences that best relate to what is discussed in the entire article. Try thinking 
of a thesis, or a really strong point made: both are highlights of an article and both tie strongly to the entire article 
(taking the assumption that a "really strong point" is strong because it has been built up throughout the article).

How it works: 
It takes the pretrained Glove word vector representation and cast that into a python dictionary. Then for each sentence in 
the test file processed, it will add up the closeness of each word in that sentence to every other word in the article 
(by taking the cosine distance between word vectors of the two words), and calculate a average distance of the sentence to 
the entire article. Then, based on the score of each sentence, the algorithm would then decide which 10/20 sentences should
be chosen as the highlight of the article.

To implement:
First, install all the dependencies in your environment: I'm using scipy and pickle.
Download the pretrained GloVe word vectors from their GitHub page: https://github.com/stanfordnlp/GloVe
I'm using the 50d vectors.
I processed the vector file as a python dictionary and pickled the dictionary. If you are running with my code, you will need
to do that and call that file "word_2_vec_dict.pkl" and put it in the same directory where you cloned this repository.
You can always change whatever is in the txt file to something you would like to extract the highlight of.
You can adjust how many sentences you want to output and this naive algorithm would tune ouputs accordingly.


