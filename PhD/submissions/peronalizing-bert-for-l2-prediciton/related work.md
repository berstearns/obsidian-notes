aspects of my research


One paragraph on how different your research is  
from other studies, or how it complements them
	1. we model linguist skill by modelling the language production of a learner
	2. we use learner related and specific data to personalize a LM to the learner
	3. we model the ability of the learner to generate L2 instead of translating
	4. 


Several paragraphs on works related to various as-  
pects of your research.  

Previous work put attention to mistakes.
	-> our work focuses in modelling linguistic skills with the intuition that if this can be done efficiently it can improve many downstream tasks such as lexical profilling, content generation, predicting text difficulty and including mistakes detection.
		-> related work doing modelling linguistic skills
			1. modelling vocabulary knowledge
	-> we use LM because of it's capabilities of encode language representations
		1. 



- modelling learner knowledge and linguistic skills
	- predicting learner knowledge of individual words using machine learning
	- 
- using the capability of Language Models to represent language
	- a1
	- Fine tuning LM with 
- Learner Modelling
	- SLA modelling
	- learner modelling in language learning
-  extract information from lexical data/cues



Our work use the success of transformers models in NLP  in encoding language representation such as in 1 2 3, combine with available 




examples of related works

The knowledge prediction task is closely related to other tasks that go by different names, e.g., complex word identification (Yimam et al., 2018), automatic text simplification (Shardlow, 2014), and vocabulary size estimation (Meara and Alcoy, 2010). The studies addressing these tasks differ in their focus on a) the type of the object to be predicted, i.e., vocabulary, single words or the whole text; b) the specific aspect of the object, i.e. size, knowledge, difficulty or complexity; and c) the process name, i.e. identification, prediction, estimation. Moreover, they differ in a) the target group, i.e., native vs. non-native speakers of different languages, and b) application, i.e., reading support, vocabulary testing, text simplification. Our study focuses on the prediction of knowledge (known/unknown) of single words similar to the following studies.

Tack et al. (2016) developed an expert model which predicts known and unknown words to a learner of a given Common European Framework of Reference (CEFR) level. They annotated words and multi-word expressions in 51 texts with their level of difficulty based on a French graded vocabulary list FLELex.

Alfter and Volodina (2018) is another recent study which used CEFR-annotated wordlists SVALex (Franc¸ois et al., 2016) and SweLLex (Volodina et al., 2016) to predict the lexical complexity



Analyzing Learner Understanding of Novel L2 Vocabulary

In this work, they explore how learners can infer second-language noun meanings in the context of their native language. 
they collect data on three word-guessing tasks, analyze their difficulty, and explore the types of errors that novice learners make.
They train a log-linear model for predicting  subjects’ guesses of word meanings in varying kinds of contexts.

we wish to present learners with interesting macaronic text that they are able to read with minimal assistance, but which still challenges them: text within the learner’s “zone of proximal development” (Vygotsky, 1978). In order to do this, we must be able to predict when learners will be able to understand a novel L2 vocabulary item. In a previous study (Renduchintala et al., 2016b), we used a small set of simple features to build user-specific models of lexical understanding in macaronic sentences. The present paper evaluates a larger set of features under a more tightly controlled experimental setup. In particular, in the present paper, our model does not have to predict which context words the learner understands, because there is only one L2 word per trial: any context words are always in L1.



gector tag not rewrite
In this paper, we present a simple and efficient GEC sequence tagger using a Transformer encoder. Our system is pre-trained on synthetic data and then fine-tuned in two stages: first on errorful corpora, and second on a combination of errorful and error-free parallel corpora. We design custom token-level transformations to map input tokens to target corrections.

modelling second language acquisition with pre-trained neural language models

Prediction of language mistakes is a task introduced by Duolingo as part of the Second Language Acquisition Modeling topic that aims to learn from the history of mistakes to improve the experience of [language learners](https://www.sciencedirect.com/topics/computer-science/language-learner "Learn more about language learners from ScienceDirect's AI-generated Topic Pages"). Using transfer learning by means of pre-trained language models, we propose a framework that can learn the actual mistakes distribution according to which faraway words of a sentence have a higher chance to produce errors

