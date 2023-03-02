

1. Introduction
	1. Computer-Assisted Language Learning
	2. Exercise Difficulty
	3. Outline
	4. Contributions
	5. Publications
2. Exercises for language learning
	3. Educational Criteria for Language Learning
	4. NLP for Language Learning Exercises
	5. Text-Completion Exercises
3. The Concept of difficulty 
	1. Readability measures
	2. Readability and Reduced Redundancy Exercises
	3. L2 Readability
4. Word Difficulty Prediction
	1. Classical Word Features
	2. Cognates
	3. Spelling difficulty
5. The Influence of the exercise format
	1. The candidate space
	2. Candidate Ambiguity 
	3. Item dependencies
6. Exercise Difficulty prediction
	1. Human difficulty prediction
	2. Predicting C-Test difficulty
	3. Predicting X-test difficulty
	4. Predicting Cloze test difficulty
	5. Learning Curve
	6. The influence of the exercise test
7. Difficulty Manipulation
	1. Manipulating Exercise Content
	2. Manipulating exercise format
8. Concluison



# Intro
	In a labor market that is increased globalized, knowledge of a foreign language is more relevant than ever before.
		Multilingual skills are also required for private communication as friendships stretch across geographical and linguistics borders.
		In addition, almost a million refugees have been crossing the Mediterran sea to seek asylum in euroope in 2015 and are looking for cheap and fast solutions to acquaint themselves with a new language.

	The static time frame of convetional language courses is often not compatible with learners unstable working conditions andl ifestyles.
	As an alternative, many learners turn to online portals for langauge learning.
	These portals are becoming increasingly popular alathoguh the provided contents are often rather inflecaible and limtied.
	
	According to vygotsky zone of proximal development, the range of suitable exercises for alerner is very narrow.
	Exercises that do not challenge the learner easily lead to boredom and stagnation, whereas overly complex exercises might rsult in frustration.
 
	For optimal support of language laerning, it is thus important to adapt the exercise difficulty according to the specific needs of the learner.
	In order to properly manipulate difficulty, it is necassary to measure difficulty.

	So far, difficulty has mainly been been a subjective estimate based on the experience of teachers. 
	However, the teachers already know the solutions and cannot always anticipate the confusion an exercise might cause for learners.
	This results in a subjective difficulty estimation that often lacks co;nsistency and can olny be evaluated based on posterior perfornance measures.
	As a consequence, the exercises that are used in high-stakes languag testing usually follow a athorogh and expensive pre-test protocol for quality assurance. 
	In less professional testing enviroments, the exercise selection depends on the subjective and uncontrolled judgement of individual persons.

	Computationak Methods can provide support for ecercise selection.
	In this theiss, we focus on text-completion exercises and the goal is two-fold:
		1. develop automatic methods for difficulty prediction based on objective measurable properties
		2. to evaluate how difficulty prediction can contribute to automated manipulation of exercise difficulty


# 1.1 Computer-assisted language learning
In the last years, numerous kanguage learning portals and apps have been developed for multiple langugages and some of them reach  a huge range of users worldwide.
Popular commercial examples are rosetta stone, busuu and babbel. 
Rosetta Stone promotes association tasks. 
busuu follows the idea of social networks and supports thei nteraction between language laerners and native speakers.
Babbel aims at reaching communicative goals and claims that their exercises provide intersactive contextualized content.
All three companies offer free demo versions of their systems, but the full product can only be accessed through paid accounts.
The most established free platform is Duolingo which was founded after a research iniative at Carnegie Mellon University. 
The business model behind Duolingo is based on the idea that language learners translate content and evaluate translations of their peer learners for free while learning the language.

the fast success of language learning technology in commercial applications is astonishing.
However, all applications still mainly provide pre-fabricated exercises that are manually designed by humans. 
This static approach can quickly lead to boredom of advanced leaerners and is lagging behind the recent developments in natural language processing.
Ideal language learning  exercises should be adapted to the learners abiliteis and preferences and make use of authentic material matching the learenrs interests. [[i prefer not text - developing communicative competence]] 

In order to enable such a fine-grained matching, exercies should be automatically generated on the fly so that tahe difficulty can be adjusted.
Research in Natural Language Processing for learners in currenlt developing very fast (see section 2.2).
Autoatic methods for content selection, exercise generation and feedback generation have improved significantly.
However, most existing approaches for exercise genration exhibit two main shortcomings.
They failt to exert approriate quality control on the genreated exercises and they cannot anticipate the difficulty level. [[Predicting Cloze Task Quality for Vocabulary Training]]
These two aspects are closely related: exercises that are rated to be of insufficient quality are almost always eother too difficult or too easy. ( there's no reference to this statement ).
In order to overcome these weaknesses, this thesis present a new model for prediciting the difficulty of exercises. 
In a second step, the automatic difficulty estimate serves as a selection filter for generated exercises and guides difficulty manipulation.

As a general scenario for this thesis, we focus on fast language proficiency tests. 
At the beginning of a language learning phase, it is important to analyze the proficiency level of the learner.
for this purpose, the exercises should be in a range of appropiate difficulty.
Exercises that are too easy or too difficult are not discriminative for the proficiency level.
The difficulty datasets that we examine in the thesis have all been created  for this scenario.
However, text-completion exercises are used for a wide range of scenarios and our findings for difficulty predictiion can easily be extended to other use cases. 
The ultimate goal is the generation of adaptive exercises for self-directed learning.
As a first step towards this goal, wee evaluate how difficulty prediction estimates can be used for manipulating the diffculty of exercises.



# 1.2  Exercises difficulty

Natural Languages are complex and continually developing constructs that icnlude many excepitons to the rules. 
Hence, the potential problems for foreign language learners are manifold and hard to anticipate. 
This theiss presents a new difficulty model that capatures many aspects of language learning and is applicable to a range of text-based exercises. 
The thesis outline follows the structure of the model.

The developed difficulty model that constitutes the theoritical basiss for this theiss is displayed in figure 1.1.
In general, the difficulty of an exercise is determined by the exercises content and the exercise format [[How fluid is the C-Test construct?]]]
The Exercises content is often referred to as the prompt or the input in other related work.
For The exercise types doscussed in this thesis the eercise content consists of short text or sentence from a genral domain.
This text is transformed into an exercise according to the exercise format.
The upper part of the model in figure 1.1 represents the foramt factos and the lower part the content factrs.
The model is further categorized into four dimensions:
	1. the text difficulty 
	2. the word difficulty 
	3. the candidate ambiguity
	4. item dependency 
the dimensions are exempliefied here  following an example for a cloze exercise displayed in the figure 1.2. 
other exercise types will be introduced in section 2.3

Exercise Content:
	The exercise content in the example is the sentence "his characteristicc talk, with its keen observance of detail and subtle power of inference held me amused and enthralled."
	The difficulty of the content can be divided into the overall text difficulty and the paraticular word difficulty of the solution observance.
	The model needs to caputre the readabiltity of the text and the familiarity of the solution word ofr the learner.

Exercise Format: 
	The difficulty of the format for this exercise depends on the candidate ambiguity of the answer options instincts, presumption, observance, expiationm and implements.
	The model needs to capture the difficulty of identifying the correct solution from the candidates.
	The item dependency is only relevant for exercises that contain more than one itema usch as c-tests and x0tets which will be introduced in esction 2.3. 
	Imainge the word detailin the  example would also be replaced by a gap. 
	selecting the correct soluton fo the first gap would then be considerably more difficult.
	In this scenario, the model needs to caputre wheteher the diffiulty of the current item is influenced by the diffulty of the surroounding items.

contente and format factors can both be further categorized intro micr-kevek and macrO level processing.\
	This term has been introduced to describe the solving strategies  of language learners [[the c-test a valid operationalization of reduced redudancy principle]]


# 1.3 thesis outline
# 1.4 Contributions
	