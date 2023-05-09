% This must be in the first 5 lines to tell arXiv to use pdfLaTeX, which is strongly recommended.
\pdfoutput=1
% In particular, the hyperref package requires pdfLaTeX in order to break URLs across lines.

\documentclass[11pt]{article}

% Remove the "review" option to generate the final version.
\usepackage[]{acl}

% Standard package includes
\usepackage{times}
\usepackage{latexsym}

% For proper rendering and hyphenation of words containing Latin characters (including in bib files)
\usepackage[T1]{fontenc}

% This assumes your files are encoded as UTF8
\usepackage[utf8]{inputenc}

% This is not strictly necessary, and may be commented out,
% but it will improve the layout of the manuscript,
% and will typically save some space.
\usepackage{microtype}

% For including hyperlinks and urls using \href{} and \url{}
\usepackage{hyperref}

% For adding images in figures
\usepackage{graphicx}

\title{The Cardamom Workbench for Historical and Under-Resourced Languages}

\author{Adrian Doyle \and {\bf Theodorus Fransen} \and {\bf Bernardo Stearns} \and \\ {\bf John P. McCrae} \and {\bf Oksana Dereza} \and {\bf Priya Rani} \\
Data Science Institute\\ University of Galway \\ Galway, Ireland}

\title{Personalizing BERT to predict L2 learner  masked sentences}


\author{Bernardo Stearns \\
  Affiliation / Address line 1 \\
  Affiliation / Address line 2 \\
  Affiliation / Address line 3 \\
  {\tt email@domain} \\\And
  Second Author \\
  Affiliation / Address line 1 \\
  Affiliation / Address line 2 \\
  Affiliation / Address line 3 \\
  {\tt email@domain} \\
  }

% Alternative author styles
% 1. Authors with same affiliation:
%
% \author{First Author \and Second Author \\
% Affiliation / Address line 1 \\
%  Affiliation / Address line 2 \\
%  Affiliation / Address line 3 \\
%  {\tt email@domain}, {\tt email@domain}} 
%
% 2. Two rows of authors (set titlebox length to 7cm)
%
% \author{First Author \\
%  Affiliation / Address line 1 \\
%  Affiliation / Address line 2 \\
%  Affiliation / Address line 3 \\
%  {\tt email@domain} \\\And
%  Second Author \\
%  Affiliation / Address line 1 \\
%  Affiliation / Address line 2 \\
%  Affiliation / Address line 3 \\
%  {\tt email@domain} \\\AND
%  Third Author \\
%  Affiliation / Address line 1 \\
%  Affiliation / Address line 2 \\
%  Affiliation / Address line 3 \\
%  {\tt email@domain} \\\And
%  Fourth Author \\
%  Affiliation / Address line 1 \\
%  Affiliation / Address line 2 \\
%  Affiliation / Address line 3 \\
%  {\tt email@domain} \\}
%  \setlength\titlebox{7cm}
%
% 3. More than four authors (set titlebox length to 7cm or more)
%
%\author{First Author$^{1}$, Second Author$^{2}$, Third Author$^{3}$, Fourth Author$^{1,4}$,\\
%\textbf{Fifth Author$^{2}$, Sixth Author$^{5}$, Seventh Author$^{6}$, Eighth Author$^{7}$}\\
%[0.5cm] 
%$^{1}$Affiliation 1, Affiliation / Address line 2, Affiliation / Address line 3, {\tt email@domain} \\
%$^{2}$Affiliation 2, Affiliation / Address line 2, Affiliation / Address line 3, {\tt email@domain} \\
%$^{3}$Affiliation 3, Affiliation / Address line 2, Affiliation / Address line 3, {\tt email@domain} \\
%$^{4}$Affiliation 4, Affiliation / Address line 2, Affiliation / Address line 3, {\tt email@domain} \\
%$^{5}$Affiliation 5, Affiliation / Address line 2, Affiliation / Address line 3, {\tt email@domain} \\
%$^{6}$Affiliation 6, Affiliation / Address line 2, Affiliation / Address line 3, {\tt email@domain} \\
%$^{7}$Affiliation 7, Affiliation / Address line 2, Affiliation / Address line 3, {\tt email@domain} \\}
%
%\setlength\titlebox{7cm}

\date{}

\begin{document}
\nocite{*}
\maketitle
\begin{abstract}
% supress this sentence, not informative
    Understanding learners' knowledge and modelling their use of linguistic skills is crucial for intelligent tutoring systems and digital learning platforms in second language teaching and learning. Motivated by the capability of language models to encode language representation, we investigate the performance of a standard BERT model in predicting masked tokens in learners' written sentences in the EFCAMDAT dataset and the effect of fine-tuning BERT with personalized data. Fine-tuned models, especially those pre-trained on nationality data, show significant improvements in recall values over the base model, while the standard BERT model also performs well. 
    % avoid sentences without verbs
    Our results support the idea that language models can encode ungrammatical language representations.



% We inject new tokens from ungrammatical resources to the BERT vocabulary and adapt it's embedding and output layer accordingly to be able to predict potentially ungrammatical tokens, mainly misspellings.

% Typically Intelligent Tutoring Systems (ITS) heavily depend on the way students are modelled.

% enable predictive feedback instead of corrective feedback in language learning, with this change sentence generation for teaching learners could be heavily personalised.

\end{abstract}

\section{Introduction}

% try to add a reference on how models in CALL systems improve the learning perfomance/experience
Modelling language learning is at the core of personalized and adaptive learning in computer-assisted language learning systems. Many aspects of the learning process can be modeled, and the generated models can be combined together in such systems. 

Those models combined offer a significant advantage in the learning experience by enabling or improving students' learning plans, scheduling, and customization, which creates an interest in developing models that are efficient but also that can be adapted for different learners, disciplines and systems.


Different approaches have been explored to model different aspects of language learning, from modelling learner language mistakes \cite{settles-etal-2018-second} and spaced repetition models \cite{settles2016trainable} to efficient grammatical error correction \cite{omelianchuk2020gector}. 
 Despite the success of such diverse tasks in tackling their specific modelling objectives, 
their machine learning solutions hardly encode learner features, typically using only features extracted from the text such as token semantics and context, linguistic information and L1-L2 cognates measures. 

With a gap in encoding a learner features in such tasks, our work aim at investigating an approach for modelling a second language learner linguistic skills that can be dynamically adapted and personalized over time using language models that can be reused to downstream tasks.
Modelling a learner's personalized linguistic skills can be utilized in many downstream tasks, such as predicting which exercises a learner will answer correctly or incorrectly, estimating which sentences learners are more likely to produce or even to create lexical profiles and vocabulary prediction. Such prior information could improve the learning experience of L2 learners. 

 
 %model a global behavior, which in the scenario of modelling learners' specific linguistic skills leads to a problem due to the dynamic nature of how students knowledge and behavior might change. With that gap in mind, we aim at investigating an approach for modelling a second language learner linguistic skills that can be dynamically adapted and personalized over time. % change skills for skill set
 
% Specifically, in language learning one's interest is to model linguistic skills of learners and investigate how those patterns could correlate to mistakes, recall and other aspects of learning. 

%Traditionally, modelling a learner linguistic skills was tackled via linguistic approaches. In the past decade however, computational and hybrid approaches have shown to be very beneficial for many Natural Language Processing (NLP) tasks focused on improving language learning demonstrated by \cite{knowles2016analyzing}, \cite{renduchintala-etal-2016-user} and \cite{avdiu-etal-2019-predicting}. 

Our approach for modelling a language learner linguistic skills uses two large learner corpora combined with language models motivated by the success of such models to efficiently adapt to different NLP tasks when applied to large datasets. Automatic proficiency assessment also benefited from the advances in modern NLP and availability of large datasets which enabled such assessments at scale and allowed individuals to assess their proficiency more regularly \cite{portnoff2021methods}. 

%It also allowed institutions to assess and group students based on proficiency. Such processes have always been a bottleneck for being labor-intensive and time-consuming and are actively being replaced with automatic computational proficiency assessments \cite{gaillat2022predicting}.
Another research area that has tremendously benefited from modern NLP and the increasing amount of corpora and computational resources is grammar error correction. Works such as \cite{sorokin-2022-improved} enabled systems such as grammarly for real-time corrective feedback in ungrammatical texts.

Similar to how these tasks benefited from the availability of large-scale resources, the increasing availability of large learner corpora as well as grammatical and ungrammatical resources such as the 
EFCAMDAT \cite{geertzen2013automatic} and the C4\_200m \cite{stahlberg-kumar-2021-synthetic} creates the possibility of efficiently scaling learners' modelling tasks and benefiting from deep learning methods.

% state that predicting misspelling tokens is a strong aspect of the work
This paper focuses on the task of modelling language learners token production in the target second language. Our methodology tries to leverage available synthetic and authentic learner corpora to efficiently predict masked tokens in a sentence generated by a learner where the context is expected to be ungrammatical, either by misspelling errors or by sentences structured differently from those of a native speaker. We also expect students of different backgrounds to have different linguistic production and for that we try to create personalized models according to nationality, proficiency and a specific learner text. We evaluate which type of personalized model performs better across a group of selected learners.

%We pre-train different models for each student by following a top-down approach. We first pre-train on the largest common subsets of the data, 50 million sentences from 200 million synthetic ungrammatical sentences in the C4\_200m, we then pre-train on writings corresponding to the learner's nationality, followed by writings corresponding to proficiency, and finally the learner's specific writings.
%To include misspellings in the model's vocabulary we propose a simple heuristic based on vocabulary frequency and edit distance to add potential misspelled tokens to the BERT vocabulary and make it possible to predict ungrammatical tokens. 

\section{Related Work}

 % DRAFT
 %\cite{} predicts the knowledge of single words for individual learners of English, through machine learning models, including neural networks and random forest, using a single model with learner-specific and word-specific features to achieve state-of-the-art results for vocabulary prediction. The models were trained for all learners but the prediction was personalized for each learner.







Our work is motivated by the difficulty of incorporating a learner's linguistic knowledge and skills in traditional computer-assisted language learning methods and the success of neural language models such as BERT \cite{bertdevlin} to be easily adaptable to different tasks and to encode language properties. Our main research question is how well can language models encode a learner linguistic skills ? For that, we measure how efficiently do language models adapt to predict tokens in ungrammatical sentences produced by language learners and which sources of data improves the recall of such language models the most.


%\cite{whitehill2017approximately} that developed a new student model that accounts for how a learner infers and updates vocabulary knowledge on an Intelligent Tutoring System for foreign language learning,

Approaches to model the learner and predicting its knowledge have been explored but limited to extract handcrafted features. Typically extracting contextual features instead of personal features, such as in \cite{zylich2021linguistic}  where authors propose combining skill-based and memory-based models to improve student modelling and retrieval practice performance for second language acquisition (SLA) tutors. They develop methods to extract linguistic features from words and use them as skills in skill-based models. Their findings show that incorporating lexical, morphological, syntactic, and semantic features outperforms existing memory-based models. 

In \cite{avdiu-etal-2019-predicting} used learner-specific and word-specific features to personalize the predictions for each learner, aimed to predict the knowledge of language learners, specifically for English single words, using a machine learning approach. The models were trained for all the learners together and achieved state-of-the-art results for vocabulary prediction for English learners. The learner-specific features were only the proportions of known words in each keyword list created from COCA subcorpora. 





Even though we see a lack of use of language models in learner modelling tasks many other diverse areas successfully adapted language models to their tasks, often using masked language modelling as a self-supervised pre-training task.
\cite{Gururangan2020DontSP} examines the effectiveness of adapting pre-trained language models to specific domains and tasks, where overall multi-phase domain and task adaptive pre-training is shown to offer large gains in task performance. 

One very specific task that benefited from Languade Models is \cite{lazar-etal-2021-filling} where the authors developed models that can fill in missing text in ancient Mesopotamian documents using contextual cues. They used a masked language modelling task to achieve state-of-the-art performance on missing token prediction despite limited data by pretraining on data from other languages and time periods.

\cite{palenzuela2022modeling} also explored language models pre-trained on data from other languages applied to modelling Second Language Acquisition in the SLAM shared task \cite{settles-etal-2018-second}, a task to forecast language learners' future mistakes based on their past errors, providing evidence that transfer learning through the use of pre-trained language models such as BERT and DistilBERT is effective in encoding linguistic knowledge to predict learners' mistakes, reinforcing the motivation for using pre-trained language models for modelling linguistic skills.

Combined with the capability of adapting well to different domains, BERT also showed capability to encode properties such as syntax, as surveyed in \cite{Miaschi2020LinguisticPO} which summarizes research on the evaluation of syntactic information in word representations across various neural network architectures and \cite{vulic2020probing} which examines how large pretrained language models extract lexical type-level knowledge from words in context across six languages and five lexical tasks.  \cite{aoyama2022comparing} show preliminary results of a study that aims to measure the depth of L2 speakers' vocabulary knowledge using contextualized word embeddings obtained from a large pre-trained language model. The study proposes a new approach to measure vocabulary depth by comparing L1 and L2 speakers' use of the same words.

% Our work explore related work in two directions.
% in one direction our work is related to approaches trying to adapt language models/transformers architectures to their specific tasks.  

% Previous tasks in modelling language learning focused on mistakes. Areas such as Grammatical Error Correction Research pursued the goal of efficiently correcting ungrammatical texts to grammatical texts by adapting modern NLP models to the task and using a variety of generated resources (authentic and synthetic).
%A second area was detecting mistakes with the Second Language Acquisition Modelling (SLAM) task, a task in computational language learning research \cite{ferreira2019text}. The task was popularized by a Shared Task created by Duolingo \cite{settles-etal-2018-second} where several teams submitted papers on how to forecast language learners' mistakes based on their learning history and demographics.
% previous 
% Second Language Acquisition Modelling (SLAM) is a task in computational language learning research \cite{ferreira2019text}. The challenge is to forecast language learners' future mistakes based on their past errors. Duolingo created a shared task in this new study field \cite{settles-etal-2018-second}. Several teams submitted papers on how to forecast language learners' mistakes based on their learning history and demographics. Learning history is a user's sequence of sentences, with each word classified as correct or incorrect.  
%The competition results are presented along with a comprehensive assessment and meta-analysis of all of the papers that were entered into the Duolingo competition. 


\begin{table*}[h!]
\centering
\begin{tabular}{llllll}
\hline
nationality          & total writings & selected students       & proficiency level & total writings\\ \hline
Brazil               & 476817         & \multicolumn{1}{l|}{20} &     1       & 352106 \\
China                & 165162         & \multicolumn{1}{l|}{1}  &     4       & 169291\\
Mexico               & 87259          & \multicolumn{1}{l|}{4}  &     2       & 164130\\
Germany              & 54597          & \multicolumn{1}{l|}{2}  &     3       & 109749\\
United States        & 33442          & \multicolumn{1}{l|}{1}  &     7       & 97882\\
Taiwan               & 29569          & \multicolumn{1}{l|}{1}  &     5       & 85746\\
United Kingdom       & 9000           & \multicolumn{1}{l|}{2}  &     6       & 52959\\
United Arab Emirates & 3562           & \multicolumn{1}{l|}{1}  &     8       & 41926 \\
Bulgaria             & 820            & \multicolumn{1}{l|}{1}  &     10      & 36485 \\
Puerto Rico          & 645            & \multicolumn{1}{l|}{1}  &     9       & 28553\\ \hline
\end{tabular}
\caption{Number of writings per nationality and proficiency levels used for pre-training}
\label{nationalities}
\end{table*}


Direct related to our goal of modelling learners' linguistic skills "modelling user language learning with Macaronic texts" \cite{renduchintala-etal-2016-user} train a model to simulate a human subject's comprehension of foreign words, investigating the possibility to leverage incidental learning using mixed L1 and L2 language.
Our work aims to train a model to simulate the capability of a human subject's of producing L2 in an L2 context, to investigate the efficiency of language models to adapt to ungrammatical sentences produced by language learners and which resources are more efficient into personalizing a language model to a specific learner and will potentially better encode its linguistic skills patterns.

%Our research questions are how efficiently do language models adapt to predict tokens in ungrammatical sentences produced by language learners ? 
%Can language models encode a leaner linguistc skills ?

Where the authors resort to a graph model with engineered features based on cognate and context clues to model a learner linguistic skills we rely on BERT combined with fine-tuning strategies that can efficiently adapt BERT to a specific resource where their approach can not. 
Lastly, they emphasize modeling the capabilities of a learner of translating from their native language to the target language. On the contrary, in our work we focus on modelling the learner's capability of producing L2 in an L2 context. As a result, we do not depend on collecting pairwise data between both languages but only writings from the target L2 language.


\section{Data}

In this section, we will introduce the EFCAMDAT dataset \cite{geertzen2013automatic} and the C4200m dataset \cite{stahlberg-kumar-2021-synthetic} as the main resources for the proposed task. They are two of the largest available resources as learner's corpora and synthetic ungrammatical data in English.
%\includegraphics[scale=0.55]{images/recallcomparison.png}

\subsection{EFCAMDAT learner corpus} 

The EFCAMDAT dataset is a Second Language Acquisition corpus collected and made available by the online school of EF (Education First) and contains 1180309 writings with 5897793 sentences written by 174743 learners. 
The corpus is composed of writings produced by learners in English and manually graded. Every piece of writing has metadata such as grade, topic, and proficiency level. Every learner has their nationality annotated. 
As the target of our work is modelling the production of specific learners, we are interested in learners with a reasonable amount of essays. We selected 34 students with more than 100 essays from 10 different nationalities, as shown in Table \ref{nationalities}.

\begin{figure}[ht] %!tbp
  \centering
 {\includegraphics[width=0.45\textwidth,     height=5cm]{images/students_selection.png}}
 \caption{Count of students per number of essays on the EFCAMDAT dataset}
 \label{countofstudents}
\end{figure}

As we achieve better performance results with our proposed models, this modelling approach could easily be extended to more learners as shown in Figure \ref{countofstudents}.



\subsection{C4\_200m dataset}

Performance in Neural Grammatical Error Correction has been improving with new proposed neural architectures and synthetic data generation. The C4\_200m compares several models that can produce an ungrammatical sentence given a clean sentence and an error type tag following automatic annotation tools such as \cite{bryant2017automatic}. 
The generated ungrammatical sentences follow the distribution of error tags of the BEA-dev dataset. They validate the generated ungrammatical data by using it for fine-tuning and outperforming genuine parallel data on the CONLL-2014 and JFLEG-test. The dataset is generated by applying the proposed method to 200M randomly sampled sentences from the Colossal Clean Crawled Corpus. \cite{raffel2020exploring}.

\section{Methodology}
\subsection{Masked Language Modelling}

% 
% report number of tokens
% explicitly specify what writings are




%\subsection{language models}
%language modelling is a task that given a text outputs the next token that would follow it. As a self-supervised task it can be trained on massive quantities of text that typically are easily available in high resource languages. As a consequence of this setup models have shown to learn a meaninful representation of the language.

Masked Language Modelling (MLM) is a task where, given a text with masked parts, a model is prompted to predict the missing tokens through their surrounding context.
As a self-supervised task, it can be trained on massive quantities of text, which are typically easily available in high resource languages.
As a consequence, models have shown that they can learn meaningful representations of the language. Different from typical language modelling tasks that predict the next token given an input text, the MLM task trains a bidirectional representation that gives relevance to both directions of the sentence. With a wide variety of tasks in NLP research benefiting from token representations learned during MLM, a natural interest is whether such tasks would generate meaningful representations of ungrammatical structures (e.g., misspellings). In this work, we identify that the MLM objective directly corresponds to the task of filling in the gaps in EFCAMDAT texts and use different ungrammatical resources in pre-training for encoding possible representations of ungrammatical structures. Typically, the MLM task simply randomly masks some percentage of the tokens in the sentence, and the trained model outputs a probability vector over the vocabulary. For our scenario, we only mask one token per sentence, as predicting one single token is the simplest cloze task to understand the effects of the changes we propose in the models.
% move this to discussion session
With a good performance in this simpler task, other more elaborated MLM strategies that are known to yield better linguistic representations could be explored.

\begin{figure}
  \includegraphics[width=7cm,height=7cm]{images/mlm.png}
  \caption{The language modelling task in ungrammatical sentences}
  \label{models}
\end{figure}
\begin{figure*}[t!]
  \includegraphics[width=\textwidth,height=10cm]{images/training_phase.jpeg}
  \caption{sequential pre-training steps described in section 3.5}
  \label{models}
\end{figure*}
\subsection{User Modelling in Language Learning} 
User modelling generically deals with modelling how a user would respond in a task given context clues. In the specific case where we are interested in what token a learner would produce, it can be seen as a masked language modelling task. An instance of this in language learning is L1-L2 mixed text used to model the capability of incidental learning where, using the L1 words as context, the learner can guess the L2 translations \cite{renduchintala-etal-2016-user}. Our work explores user modelling as a masked language modelling task in two different aspects. First guessing an "L2 word" using "L2 words" as context. Second, the "L2 words" include ungrammatical L2 tokens generated by the learner instead of only correct native L2 vocabulary. In this way, we expect to implicitly encode the language production patterns of a learner in the second language. 

\subsection{Model Architecture}
% specify downstream tasks or move to discussion 
%
We introduce BERT-based models aiming to solve the task of predicting masked tokens in the EFCAMDAT texts. BERT fits well for our scenario since its masked language modelling task is very similar to our downstream task. We use BERT as described in \cite{bertdevlin} and made available through huggingface\footnote{\url{https://huggingface.co/}}.

\subsubsection{Embedding layer}
The first layer in the BERT architecture is an embedding layer, which maps tokens recognized by the BERT tokenizer to a vector representation. Apart from word tokens, the BERT tokenizer uses word-piece embeddings, which, in the case of unknown words, try to split them into smaller pieces and compound an embedding based on them. In our scenario, we expect to have many ungrammatical tokens that are not considered in BERT. For this, we need to use strategies to represent those ungrammatical tokens. Manually curating which tokens should be added to the word embeddings is not feasible due to the massive amount of data. Thus, we try to automatically add tokens that are not in the BERT vocabulary or in a list of frequent English tokens but are reasonably close to at least one token in those vocabularies. A simple approach for this is to sort the tokens on our ungrammatical text based on the minimum edit distance to a token in the vocabularies and choose a threshold to filter the new vocabulary size.
Similarly, the embedding representation of those new tokens will be the embedding of the closest token in the vocabulary.


\subsubsection{Output layer}
The Masked Language Model Output layer of BERT is a softmax over the language modelling head, which outputs prediction scores for each vocabulary token. Again, we have a similar problem of predicting out of vocabulary tokens since they will simply not have a prediction score. To overcome this problem, we use a similar approach by extending the dimensions of the prediction scores vector to the size of the new vocabulary with the new tokens from our ungrammatical datasets and assigning an initial weight to those new tokens based on the closest token in the vocabulary based on edit distance.

\subsection{Vocabulary Modification}
% add citation of BERT vocab modification



% report frequency by nationality
% not whole EFCAMDAT
% can bert caputre density of mispellings
\begin{table}[b!]
\begin{tabular}{ll}
\hline
\textbf{token} & \textbf{frequency (EFCAMDAT)} \\ \hline
beatiful      & 5321                          \\
programing     & 1540                          \\
diferent       & 1456                          \\
recomend       & 1454                          \\
shoping        & 1306                          \\
peaple         & 1284                          \\
contry         & 1246                          \\
planing        & 1161                          \\
responsable    & 912                           \\ \hline
               &    

\end{tabular}
\caption{Examples of frequent misspellings}
\end{table}

With the goal of mitigating the negative effects of out-of-vocabulary tokens, we searched for tokens in the EFCAMDAT and C4\_200m that were not present in the BERT vocabulary and not present in the Google trillion word corpus. We show in table 2 some examples of out of the vocabulary tokens that were found. They correspond to approximately 3\% (2 million out of 72 million) of the tokens on the EFCAMDAT dataset, which is not negligible but would have a marginal effect on our task. For datasets with more spelling errors, this modification would be more critical. Given a lower priority for this issue, we perform a simple solution by ordering the missing tokens by frequency and with an edit distance to a word in the vocabulary of at most 2. The intuition is to automatically add to the vocabulary any misspellings that are relatively close to the correct language. After making this selection, we add those tokens to the embeddings and output layer by simply copying the embeddings and output layer weight from any of the closest tokens.

\subsection{Training steps}
The main stages of developing our proposed models are injecting new vocabulary into the model and pre-training it on each source of data we want to investigate. An important aspect of the training steps is that we generate more than one model that is specific to each selected learner, as depicted in Figure \ref{models}. In the first step, we trained our modified vocabulary BERT over the C4\_200m dataset, and as it is an ungrammatical unpersonalized dataset, it outputs only one single model used for all learners. The second training step creates one nationality-specific model for each of the 10 nationalities of the 34 selected students. Doing the same in the third step for the proficiency of the same students. Lastly, we pre-train using specific learner data and output a learner specific model.



\section{Evaluation}
\begin{table*} [h!]
\begin{center}
\begin{tabular}{ || c c c c c c c c || }
\hline
  &  &  &  & recall at k &  & &  \\ [0.5ex]
 Model &  MRR & 1 & 5 & 10 & 25 & 50 & 100 \\ [0.5ex]
 \hline
unmodified bert(baseline) & 0.564 & 0.466 & 0.677 & 0.743 & 0.814 & 0.851 & 0.881 \\
\multicolumn{1}{||l}{\textbf{+} c4200m} & 0.552 & 0.460 & 0.666 & 0.712 & 0.777 & 0.803 & 0.830 \\
\multicolumn{1}{||l}{\textbf{+} nationality} & \textbf{0.667} & \textbf{0.575} & \textbf{0.780} & \textbf{0.822} & \textbf{0.871} & \textbf{0.893} & \textbf{0.908} \\
\multicolumn{1}{||l}{\textbf{+} proficiency} & 0.582 & 0.480 & 0.681 & 0.749 & 0.831 & 0.873 & 0.884\\
\multicolumn{1}{||l}{\textbf{+} learner}& 0.587 & 0.483 & 0.681 & 0.749 & 0.831 & 0.873 & 0.884\\ [2.5ex]
\hline
\end{tabular}
\caption{Results of each group of pre-trained models on the EFCAMDAT test set }
\end{center}
\end{table*}
% Our experiment aims to evaluate two questions:

%1) How much do the different data sources increase top k  measures of a language model? and

%2) How does injecting the vocabulary with potential ungrammatical tokens improve the capability of such models of recalling the masked token as a candidate prediction?
In this section, we present the preparation of our experiments and the selected evaluation metrics for the performance of our proposed approach. We conducted experiments on 34 selected students with more than 100 writings in the EFCAMDAT dataset.

As a step to calculate our results, we created a test set by randomly selecting 90\% of the writings of the selected learners for training the learner specific model and 10\% for testing all pre-trained models. This becomes roughly 90 writings for training and 10 writings for testing per learner. So in total, our test set contains 340 writings, from which we have 1380 sentences.
For each sentence, we mask a random token that contains only alphanumeric characters to avoid numbers and punctuation. One inconvenient aspect of the dataset is having entities such as people's, cities', and other names, which are relatively hard to filter automatically and could potentially reduce the performance of the models since our models are not trained to predict such names.

For each of the 34 students we load their respective nationality, proficiency and own learner model and generate one token prediction per model for each masked sentence of that learner in the test set. We then group the predictions by type of model and report an average recall and MRR measures per student per sentence. Our metrics are described below.

We use mean reciprocal ranking and average recall at k metrics as reference metrics for our work.
The statistical metric known as the mean reciprocal rank (MRR) is evaluate systems that generate lists of potential responses to a given set of queries, ranked by their likelihood of being correct. Specifically, the MRR is computed by taking the reciprocal of the rank of the first correct answer for each query, and then taking the average of these reciprocal ranks. This measure provides a useful means of assessing the effectiveness of various query processing methods and can be applied to a wide range of applications in fields such as information retrieval and natural language processing.



\[ MRR = \frac{1}{N}\sum_{i=1}^{N}\frac{1}{rank(\hat{y_i})} \]

\[ Avg Recall at K = \frac{1}{N}\sum_{i=1}^{N} 1[rank(\hat{y_i}) \leq k]
\]

In both equations, the average is calculated over each sentence used for prediction in the test set. The rank function corresponds to the index where the correct label is positioned in the prediction.

%As a support metric for the average recall we use the median top k for each model to have a grasp what is that typically the prediction of one model is in a higher rank than the other.

%\[ Median = \frac{1}{N}\sum_{i=1}^{N} 1[rank(\hat{y_i}) \leq k]
%\]


\section{Results}

Our improvements in relation to the initial base BERT model were very promising in terms of improvement in recall. One small component is related to including tokens that were not in the base BERT vocabulary, but the significant improvement in all ranges of k for recall values gives evidence that by pre-training on the ungrammatical sources, we are adapting well for every specific data source. Specially for the nationality data, we notice very positive results, showing how having a large scale human generated resource can bring drastic improvements. 

%A non-intuitive result is that although most pre-trained models achieve superior recall results for $ k = 1, 5, 10 $ the base BERT models have better results for higher values of k, and this is reflected in a higher mrr. This shows the tail effect of such metrics.

One other important aspect is that the ordering of the pre-training can influence the results of the later models, such as the learners being affected by the lower performance of the pre-training on the proficiency data source. This result gives evidence that training in different combinations might yield better results but requires a combinatorial  


\begin{figure}[ht!] %!tbp
  \centering
 {\includegraphics[width=0.55\textwidth,     height=8cm]{images/bestmodel.png}}\label{fig:Images/f1}}
 \caption{Difference in recall between base model and the average of the nationality models}
\end{figure}

\section{Conclusion}
% we notice a tradeoff of keeping the results in the "correct grammatical tokens" versus being able to predict ungrammatical tokens
% Naturally those personalized models should perform better in ungrammatical sentences. fuuture work could analyze sentences tagged by error types and investigate thhe perfomance of personalzied models in ungrammaticall scenarios vs correct scenarios
Our work explored combining resources from learner corpora research and grammatical error correction to evaluate the feasibility of a BERT model being personalized to specific language learners in a masked token prediction task. To investigate the amount of misspelled tokens, we analyzed the frequency of misspellings in the EFCAMDAT Dataset. We concluded that out of vocabulary tokens were way below what was expected in an ungrammatical dataset, so we considered it a marginal issue for the EFCAMDAT dataset since only about 3\% of the tokens were not in the BERT vocabulary. We augment the model with a simple heuristic by adding the most frequent and closest ungrammatical tokens to some tokens in the vocabulary to the BERT embeddings and output layer.
To investigate the capability of personalization, we pre-train different models in sequence, each according to one source of data. Overall, pre-training a BERT model in those specific ungrammatical sources yielded positive results, especially for the nationality data, which had the biggest impact in terms of increase in all top-k recall. Our intuition is that because almost half of the writings are from Brazilians, it is a bias towards typical mistakes made by such students, but at the same time, there is evidence that BERT was able to encode those linguistic patterns.
We see many directions for future work, two of which are evident: direct exploring improvements in the models for the tasks such as experimenting different transformers models such as MBERT and exBERT, different training tuning and strategies. We are interested at evaluating the performance of such models in specific types of sentences where using error-annotated sentences we could investigate types of ungrammatical structures our models perform well against and which types they can have poorer performance against. Lastly, there are possibilities of using the trained models to downstream tasks such as lexical profiling using probability outputs of trained learner language models and word embeddings to investigate lexical competence.
%We  slight decrease in the recall at \( k=1 \) and mrr for the trained models but an increase in recall at \( k \geq 5 \) which we infer is probably due the fact default BERT is bounded to its vocabulary and can't predict the new out of vocabulary tokens while our adapted models can. This gives us an estimation that about 34\% of the tokens are not recognizable by default BERT in our test set. On the counter side, we notice that the trained models with new vocabulary suffer in performance due to the increase in the vocabulary and it becomes a challenge to efficiently automatically prune good L2 ungrammatical tokens candidates from noisy data.

%We see many directions for future work, two of which are evident: direct exploring improvements in the models for the tasks such as experimenting different transformers models such as MBERT and exBERT, different training tuning and strategies. We are interested at evaluating the performance of such models in specific types of sentences where using error-annotated sentences we could investigate types of ungrammatical structures our models perform well against and which types they can have poorer performance against. Lastly, there are possibilities of using the trained models to downstream tasks such as lexical profiling using probability outputs of trained learner language models and word embeddings to investigate lexical competence.

%We see many directions for future work, two of which are evident: direct exploring improvements in the models for the tasks such as experimenting different transformers models such as MBERT and exBERT, different training tuning and strategies. We are interested at evaluating the performance of such models in specific types of sentences where using error-annotated sentences we could investigate types of ungrammatical structures our models perform well against and which types they can have poorer performance against. Lastly, there are possibilities of using the trained models to downstream tasks such as lexical profiling using probability outputs of trained learner language models and word embeddings to investigate lexical competence.

%We see many directions for future work, two of which are evident: direct exploring improvements in the models for the tasks such as experimenting different transformers models such as MBERT and exBERT, different training tuning and strategies. We are interested at evaluating the performance of such models in specific types of sentences where using error-annotated sentences we could investigate types of ungrammatical structures our models perform well against and which types they can have poorer performance against. Lastly, there are possibilities of using the trained models to downstream tasks such as lexical profiling using probability outputs of trained learner language models and word embeddings to investigate lexical competence.


\bibliographystyle{acl_natbib}
\bibliography{ldk}
\end{document}