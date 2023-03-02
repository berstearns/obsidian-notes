## thoughts
1. they mention two ways of operationalizing the "Proficiency" construct
	1. what are the two ways ?
		1. holistic measures factoring in several grammar constituents
			1. i.e. the number of constituents such as the raito between the number of dependent clauses and the total number of clauses in a text.
		2. Frequency counts of different grammatical patterns classified in terms of complexity
	2. the main drawback is, neither operationalises the variation between multiple forms mappend to one function
		1. previous work suggests that there are variations in mappings across proficiency levels 
			1. is there a similar work, suggesting that there are variations in mappings across nationalities ?
		2.  So capturing mapping variations could help identify factors of proficiency in L2 learners
		3
	
2. they mention mappings, what are some types of mappings ?
	1. Form-function mappings
		1. can be operationalised as probability indicators in the use of one form over other forms mapped to she same function
		2. i didn't get get the context those functions are used, sentence level ?
2. 
3. they present the design  of a new functional complexity measure operationalising the FOR, TO prepositions mapped to the communication function of "expressing purpose"
	1. design a masurea generated with a probabilistic model which is intended to be part of a proficiency predictor system

## abstract
this paper presents the initial stage in the design of an ICALL system. 
The Objective is to develop a system that automatically generates linguistic analytics of l2 learner writigns. 
student texts will  be processed with nlp tools producing differnte types of textual measure.
we present the design of a new funcitonal complexity metric aiminig to capture the paradigmantic competition betaween forms mapped to hthe same commnuicative function, i.e. microsystems.
More precisely, we analyze the variatonsof the for and to preposition in terms of frequency  and probablitity of ocurrence.
Relative frequency shows significant correlations with cefr levels suggesting its possible use in a ananlatyics report system.
more work is required to extend the apporach to other microsytems
## theoretical background
structure complexity is a construct that includes functional complexity as one of its sub-types. (bulte and housen 2012)
(functional complexity construct)this construct rellies on the mappings between forms and functions of linguistic forms.
It has been operationalised in various ways such as specific parts of speech or dependency relations (Settles et all., 2018) or syntatic constituents as in CTAP's feature selector module (Chen and Meurers, 2016).
The use of functional complexity features offers two advantages for studies in the field of second language acquistion. 
First, based on learner corpora, these features can be used to design metrics exploited for modellingn purpose in prediction tasks such as CEFR classification (Vajjala 2018; Kyle; 2016;Pilan et al.; 2016; Yannakoudakis et al., 2011).
Secondly, they can be exploited for the design of specific linguistic feedback which is meaningful for learners and teachers (Riemenscheneider et al., 2021)
Learners make confusions between forms of the same communicative function. 
They tend to hesitate between one form of the other when theywant to express a speficic function such as obligation, probability, purpose or reference. 
These hesistations illustrate one aspect of the competition model in which learners constantly resolve conflicts while choosing forms (MacWhinney et al, 1984), hence the notion of L2 microsystems.
These microsystems are unstable as learners unexpectedly group forms that do not necessarily fall in the same functional paradigm (Py, 1980).
Due to this instability in the mappings, the microsystems are transitional in  nature (Gentihomme, 1980).
They include erroneous mappings which later are removed, leading the learner to better proficiency.

The microsystem can be analysed according to their paradigmantic relatins.
the following examples show theh use of the FOR and TO prepsotions in contexts ecpressin g opurpose and more precsisely followed by verbs anda nominalised werbs with ING.
In all three casesa the learners present difficulties to choose the right prepostion whiting to-clause or prepostional phrase contexts.
In (1) a more acceptable hcoice might have been FOR.
There seems to be aconfusiin between the use of complement to-clause ocntroleled by write andf the use of a prepositional phrase (PP) introduced by FOR. 
In (2) and (3) the learner clearly misued FOR instead of TO.
In (2 the learner shows a confusion between hte use of a complement extraposed to-clauses and a PP.
In (3), the confusion seems to be between a PP and an adverbiial clause wrongly introdcued by FOR( instead of in order to for instance)
the underlying assuption in these ecamples is thata htere is an L2 spefici micrsosytem in which FOR and TO compete paradigmantaically to express purpose be it in to clasues or prepsotioinal phrases including ing noung phrases.
in the context of l2 auomatidc analysis, a challenge is to quatinfy the variations awhiting this micros;ystem and other whcihch leads us to the following reserach questions.
How can we capture variations between forms mapped to the same communicative functions ?
Which form variations cab be observed within a microsystem across CEFR levels ?
Answering these questions with computer models would provide the ground for the design of an NLP pipeline
## a learner language analytics system
the microsystem approach falls ewihtin a broader objective ie the design of an icaa; syistem for teachers.  
the objective is to develop a computer system; that automatically generates linguistic analytics of leaerners writings.
the stufents will input their texts which will processed with nlp tools producing didfferent types of textual measures sime if which micriosystem based
the system will provide viassualizations of the mesures for teachers to analpyse their studnets writing profiles

developing the system requirs the validation of the textual measures un terms of correlatuons. 
a method to identify correlations between linguistic features and metadata including proficiency, task types and learning habist will be applied.
this paper discusses the case of the statistical validaton of the FOR, TO mimcrosystem.


## method for hte validation of the mmeasures used in the system
we used the spanish subssrt of the efcamdat corpus (geertzen et al 2013).
it is made up of 8k texts written by englishtown studnets in spain.
### pre-processing and extraction
the textst were preprocessed with udpipe (straka et all 2016) using the stanford english-ewt-ud-2.5 english model in r.
The tool provides grammatical annotiation such as PoS, Lemma, dependency relations and morphological features lined to hte class of words (gender, number, case...).
The cefr levels were then append to the resulting dataset.
the objective of the extraction was then to identify TO and FOR prepositionos related to the function of "purpose"
To extract the forms we proceeded two fold.
	1. we only focused on actions ( nominalised with ING or not) and retrieved verbs of any tense or aspect following the two forms.
	2. following (biber et al 1999) on the identification of complement-to-clauses we applied queries that identified the forms according to a predetermined list of verbs and adjvectives controlling to-clauses
