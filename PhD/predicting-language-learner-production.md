user modelling in language learning using macaronic texts 

the goal of the work is two fold 
	-> explore scenarios for predicting user language production and exploring its predicability 
	-> encoding learner linguistic information efficiently with expectations to use this encoding to represent learners in some related tasks such as the duolingo shared task

->0-=
-> this would facilitate the automatic construction of comprehensible text for personalized foreigh language learning 

i'm not really confident about the approach of modelling user language production as it is a hard task.

 instead on focusing on predictability trying to focus a little bit more on the pontetial of exploration of many generated sentences calibrated for some sense of difficulty.


so the idea is how to model the zone of proximal development of a learner by exposing him to different scenarios/sentences


so the most likely scenario so far is that it's hard to predict languague learner production so how could one still try to map a zone of proximal development ?

-> modelling language learning with specialized elo ratings
	- automatic assesment of the proficiency levels of a learner
	- We simultaneously obtain ratings for the pro   ficiency of the learners and for the difficulty of the linguistic concepts that the learners are trying to master




When we analyze the tail of the top K we see that the models with extra vocab have a higher recall than the default bert model, this is because default bert is bounded by its vocabulary so it will never recall a token that is not in the vocabulary


adding vocabulary  to bert tokenizer/vocab and output layer

 1. we choose tokens that are not in the bert tokenizer and not in frequency table list of tokens
2. we sort the token candidates based on edit distance to any token in the vocab or word freq list
3. we select the tokens with a edit distance less than  X

the intuittion here is selecting tokens that are possible mistakes that are close enough to the expected native tokens. Other tokens with higher edit distances are hard to evaluate computationally if they're grammatical mistakes or some kind of noise text.



# Introduction 
GEC give 


# 

# Evaluation
We have three complementary scenarios to  strengthen our results.
\first as a benchmark we evaluate the default BERT in the whole EFCAMDAT dataset to have some evidence that we are not overfitting in the specific selected essays. We then evaluate the default bert, the c4_200m , nationality, proficeincy and learner specific models with modified word embbedings and output lyaer in the selected learners test essays.

# Results

# conclusion
there are an array of possible directions tto be explored
First, there are mulitple engineering aspects that can be used to improve results such as experimenting different models such as roberta, MBERT, EXBERT. 
Improving the vocabulary of "wrong" tokens for example classifying tokens by type of error


exploring the accuracy/perfomance of the models in sentences with specific tag errors to identify the capbility of such models of reproducing erroroneus behavior

explore ways to automaitcally label tokens a grammatical/ungramamtical





the success n the task is probaably due to the complexity of the senteces , being very simple. 