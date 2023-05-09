Hi Bernardo

  

Do submit for feedback

[https://docs.google.com/forms/d/e/1FAIpQLSd85EOw6bOInm_dwLtgdl49GwG2wt0-5ftXFmx5906vEGfpHg/viewform](https://docs.google.com/forms/d/e/1FAIpQLSd85EOw6bOInm_dwLtgdl49GwG2wt0-5ftXFmx5906vEGfpHg/viewform)


Best,

Nicolas

  
The other LLMs: using Learner language models for lexical profile  

This talk will describe work in progress with learner language models trained to investigate lexical competence with word embeddings. BERT (ref) has been fine-tuned with the EFCAMDAT according to levels and assumed mother tongues. We will discuss several strategies based on what language models do best : predicting the next token. 

The research questions are : 

- which tokens should be masked to simulate the next token according to the learned language models ?

- how does this offer a window unto learner lexical competence ? 

We have identified several strategies to use probes of the leaner language model to simulate lexical competence as instantiated in next token prediction tasks   

1. exploring the beam search

In Neural Machine Translation, the beam search is used to survey the alternative words that were eventually discarded by the model  (in decreasing probability). We will explore this virtual paradigm provided by alternative next tokens of decreasing probability and what it reveals of lexical knowledge. The set of alternative tokens can be analysed in terms of surprisal and of distance to the tokens predicted by BERT. 

(note:  we also need to filter out/ penalise the last masked tokens of the sentence: due to conditational probability, in our experiments on decoders, the last tokens of the sentence are much easier to predict than the first tokens of the sentence)/

Lexical profiles could be defined/ranked 

- using the standard metric for language models (language models of expert learners have the lowest perplexity values)

- using surprisal (the )

- using cosine distance to BERT (language models of expert learners have the lowest distance to BERT native equivalent)

  

2. masking hypernyms (things)  

Learners are more likely to use hypermyms (thing) used as metawords or teddy bears. Masking different types of synsets (thing, do, nice) could allow the lexical network of alternative token to be surveyed using Wordnet (Fellbaum, 2005) 

3. masking tokens marked as errors  

Investigate the error-annotated corpora to try to predict a given type of error.

  

References:

BERT

Fellbaum, Christiane (2005). WordNet and wordnets. In: Brown, Keith et al. (eds.), Encyclopedia of Language and Linguistics, Second Edition, Oxford: Elsevier, 665-670.

[http://wordnetweb.princeton.edu/perl/webwn](http://wordnetweb.princeton.edu/perl/webwn)

Van Heuven, W.J.B., Mandera, P., Keuleers, E., & Brysbaert, M. (2014). Subtlex-UK: A new and improved word frequency database for British English. Quarterly Journal of Experimental Psychology, 67, 1176-1190. 

[http://crr.ugent.be/archives/1352](http://crr.ugent.be/archives/1352)





######## 



The other LLMs: using Learner language models for lexical profile  

This talk will describe work in progress with using probability outputs of trained learner language models and word embeddings to investigate lexical competence. BERT has been fine-tuned with the EFCAMDAT according to levels and assumed mother tongues. We will discuss several strategies based on what language models do best : predicting the next token. 

The research questions are : 

- ~~which tokens should be masked to simulate the next token according to the learned language models ? 
-  how can masking error-prone sentences be used with learner language models to estimate lexical profiles ?

- how does this offer a window unto learner lexical competence ? 

We have identified several masking strategies to use probes of the leaner language model to simulate lexical competence as instantiated in next token prediction tasks   

1. exploring the beam search

In Neural Machine Translation, the beam search is used to survey the alternative words that were eventually discarded by the model  (in decreasing probability). We will explore this virtual paradigm provided by alternative next tokens of decreasing probability and what it reveals of lexical knowledge. The set of alternative tokens can be analysed in terms of surprisal and of distance to the tokens predicted by BERT. 

(note:  we also need to filter out/ penalise the last masked tokens of the sentence: due to conditational probability, in our experiments on decoders, the last tokens of the sentence are much easier to predict than the first tokens of the sentence)/

Lexical profiles could be defined/ranked 

- using the standard metric for language models (language models of expert learners have the lowest perplexity values)

- using surprisal (the )

- using cosine distance to BERT (language models of expert learners have the lowest distance to BERT native equivalent)

  

2. masking hypernyms (things)  

Learners are more likely to use hypermyms (thing) used as metawords or teddy bears. Masking different types of synsets (thing, do, nice) could allow the lexical network of alternative token to be surveyed using Wordnet (Fellbaum, 2005) 

3. masking tokens marked as errors  

Investigate the error-annotated corpora to try to predict a given type of error.


References:


Devlin, Jacob (2018). Bert: Pre-training of deep bidirectional transformers for language understanding.

https://arxiv.org/abs/1810.04805

Fellbaum, Christiane (2005). WordNet and wordnets. In: Brown, Keith et al. (eds.), Encyclopedia of Language and Linguistics, Second Edition, Oxford: Elsevier, 665-670.

[http://wordnetweb.princeton.edu/perl/webwn](http://wordnetweb.princeton.edu/perl/webwn)

Van Heuven, W.J.B., Mandera, P., Keuleers, E., & Brysbaert, M. (2014). Subtlex-UK: A new and improved word frequency database for British English. Quarterly Journal of Experimental Psychology, 67, 1176-1190. 

[http://crr.ugent.be/archives/1352](http://crr.ugent.be/archives/1352)
