[[_____thoughts]]
This talk will describe work in progress with using probability outputs of trained learner language models and word embeddings to investigate lexical competence. 

describe work in progress with using probability outputs of trained learner language models and word embeddings to investigate lexical competence

## slide 1

present myself as a research associate mostly working in NLP and doing a part time phd in Machine learnig focused in applying NLP in Education -> language learning 

add the title of the presentation -> something related to using LM outputs for lexical profiling

1. 





## slide 2

talk about the big picture of my phd work and briefly describe the bert personalization experiment. 

Highlighting that i want to embbed learner knowledgge representation to improve the quality of downstream tasks such as 

## slide 3

talk about the big picture of the. A4LL project








BERT has been fine-tuned with the EFCAMDAT according to levels and assumed mother tongues. We will discuss several strategies based on what language models do best : predicting the next token. 





## Slide Lexical Profiling Estimation 

-> virtual representation of a learner
-> masked language modelling task tells us how well a language model(or other models) can predict a language learner production behavior 
-> simulation over  sentences known to be challenging



how efficient are LLM at estimating a learner lexical profile ?
	-> a LLM alone is not enough 
		-> we need to evaluate LLM by simulate LLM in a set of sentences that are known 
		to lead to a certain type of errors 
		-> we need postprocessing statistics will be effective features for lexical estimation ?
	-> How Nationality LLM profile estimates correlate with CEFR profiles ?
