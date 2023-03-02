

 1- The domain and its interest leading up to the focus of this paper. 
 ITS 

 
 2- What's the need for the research? Why the need to explore such area.
 
 3- One main problem of the domain leading to a missing element in the current research situation
 
 4- Your proposal to solve the problem.

## current  abstract


1- Intelligent tutoring systems and digital learning platforms are becoming increasingly common in Foreign Language Teaching and Learning, so the capability of understanding its learners knowledge and linguistic patterns is crucial for a sucessful application.
An increasing amount of available learner's corpora and Grammar Error Correction resources enabled the possibility of modelling a language learner's L2 production based  the learner own previous writings, similar learners writings, synthetic ungrammatical text and the current textual context.
We investigate how well a standard BERT model can predict the missing token in a masked sentence produced by a learner in the EFCAMDAT dataset and if fine-tuning it with personalized data improves its performance.
The standard BERT model performs well  and the Fine-tuned models, particularly pre-trained on nationality data, show significant increase in recall values compared to base model.

2- An increasing amount of available learner's corpora and Grammar Error Correction resources enabled the possibility of modelling a language learner's L2 production based on a different array of resources  such as the learner own previous writings, similar learners writings, synthetic ungrammatical text and the current textual context.
			--> this is what enables my approach, not what motivates it


3- We investigate how well a standard BERT model can predict the missing token in a masked sentence produced by a learner in the EFCAMDAT dataset and if personalizing it improves performance. 
	-> what we do
	-> (personalizing = ) we pre-training BERT over ungrammatical resources and adapting its embeddings and output layer for predicting misspellings


we highlight that even in a dataset where most of the writings are from beginners and intermediate learners a default BERT model performs reasonably well and our fine-tuned models have a significant increase in recall values compared to the base model, specially models pre-trained on nationality data.

The standard BERT model performs well  and the Fine-tuned models, particularly pre-trained on nationality data, show significant increase in recall values compared to base model.
	-> the current findings of the work

** In a dataset dominated by beginner and intermediate level writings, our fine-tuned models show a notable increase in recall values compared to the default BERT model, particularly for models pre-trained on nationality data.
## current intro

Modelling  a language learners linguistic patterns is at the core of personalized and adaptive learning in Computer Assisted Language Learning Systems.



## 
With digital learning contexts becoming increas- ingly common in Foreign Language Teaching and Learning, automatic exercise generation arguably will become a crucial tool for making individual- ized practice materials available that are adapted to the learner’s individual needs and competencies

with digital learning contexts becoming increasingly common in foreign language teaching and learning, personalized generation of content/exercises will be crucial for optimizing learning in a setting like this. 
	-> One of the key components to make this work is modelling a learners language production to simulate how a learner would behave.
	-> Modelling a learners language production can sign


## 
In an increasingly digital context, an important need for automati- cally generated exercises is arising in the context of adaptive language tutoring systems Such systems thus need to either manipulate exercise difficulty in real-time (Beinborn, 2016) or to maintain large pools of exercises of varying complexity levels. 


## 
Foreign language teaching achieves best learning outcomes when individual differences of learners are taken into account. While it is difficult for teachers to support internal differentiation in the classroom, digital tools can adaptively propose individual learning paths through activities so that students can practice with appropriately challenging exercises.


##
 Artificial Intelligence methods employed in Intelligent Computer Assisted Language Learning (ICALL) in principle makes it possible to individually support language learners. Second Language Acquisition (SLA) research and language teaching practitioners agree on the relevance of target language input adapted to the learner level. However, little systematic research has explored individually adapting input and how it impacts learners
