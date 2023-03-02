 1. Understanding learners' knowledge and linguistic patterns is crucial for intelligent tutoring systems and digital learning platforms in Second Language Teaching and Learning, which are becoming increasingly common.
	Understanding learners' knowledge and linguistic patterns is crucial for intelligent tutoring systems and digital learning platforms in Second Language Teaching and Learning, which are becoming increasingly common.
2. Motivated by the capability of Language Models to encode language representation we investigate the perfomance of a std bert model in predicting masked tokens in learners' written sentences in the EFCAMDAT dataset and the effect of fine-tuning BERT with personalized data.
	
	Aiming at modelling a learners' token production we use the EFCAMDAT and C4\_200m datasets to investigate the performance of a standard BERT model in predicting missing tokens in learners' masked sentences and the effect of fine-tuning with personalized data
	
	Motivated by the capability of Language Models to encode language representation we investigate the perfomance of a std bert model in predicting masked tokens in learners' written sentences in the EFCAMDAT dataset and the effect of fine-tuning BERT with personalized data
3. Fine-tuned models, especially pre-trained on nationality data, show significant recall values improvement over the base model, while the standard BERT model also performs reasonably well.
	Fine-tuned models, especially pre-trained on nationality data, show significant recall values improvement over the base model, while the standard BERT model also performs reasonably well.

	Those results encourages further exploration of how BERT can encode learners linguistic patterns


## INTRODUCTION
## mention Knowledge tracing ... where a machine models the knowledge of a student as they interact with coursework

## show other aspects of learners that have been modelled


1. Modelling language learning is at the core of personalized and adaptive learning in Computer Assisted Language Learning Systems
	1. so it is of interest to develop models that can trace and be easily updated due to the dynamic nature of language learning and learners. 
	2. The benefit of such models is is that students’ learning plans can be better organised and adjusted, and interventions can be made when necessary.
	3. Such models offer a significant advantage by enabling the improvement of students' learning plan organization and customization, and facilitating the timely implementation of interventions as required.
2. Different approaches have been explored to model different aspects of language learning, from modelling learner language mistakes \cite{settles-etal-2018-second} and spaced repetition models \cite{settles2016trainable} to efficient grammatical error correction \cite{omelianchuk2020gector}.
3. --Even with the success in such diverse tasks, encoding learners linguistic patterns at scale is still a challenge.
	1. Even with the success in such diverse tasks in tackling their specific modelling objectives, typically they are modelled as a global behavior which in the scenario of modelling learners' specific linguistic patterns leads to a problem due to the dynamic nature of how students knowledge might change.

4. % Specifically, in language learning one's interest is to model linguistic patterns of learners and investigate how those patterns could correlate to mistakes, recall and other aspects of learning.  %
	1. 

6. With that gap in mind, we aim at investigate approaches for modelling a second language learner linguistic patterns that can be dynamically adapted and personalized over time.
7. 

9. Traditionally, those topics were tackled via linguistic approaches. In the past decade however, computational and hybrid approaches have shown to be very beneficial for many Natural Language Processing (NLP) tasks focused on improving language learning demonstrated by \cite{knowles2016analyzing}, \cite{renduchintala-etal-2016-user} and \cite{avdiu-etal-2019-predicting}.
	1. 
	Analyzing learner understanding of novel l2 vocabulary.
	prediciting learner knowledge of individual words using machine learning
	user modelling in language learning with macaronic texts



Similar to how these tasks benefited from the availability of large scale resources, an increasing availability of large learners corpora as welll as grammatical and ungrammatical resources such as the EFCAMDAT and the C4_200m creates the possibility efficiently scaling learners' modelling tasks.

	integrating different 

investigating and efficiently scaling tasks that are predictive in nature (e.g, scheduling, generating content and tracing knowledge) becomes more plausible but revolves around on the ability of simulating the behavior of a learner ahead of time. 

\item The domain and its interest leading up to the focus of this paper. 
\item What's the need for the research? Why the need to explore such area.
\item One main problem of the domain leading to a missing element in the current research situation
\item Your proposal to solve the problem.