The only relevant papers that are using the term personalization are related to federated learning 
[Survey of Personalization Techniques for Federated Learning](https://ieeexplore.ieee.org/abstract/document/9210355)

but idea is mostly balancing privacy with distributed learning , which involves local training with shared gradients
![[kulkarni2020.pd]]


# meta learning for nlp a survey
[link](https://arxiv.org/pdf/2205.01500.pdf)

aims to create models that can learn new skills or adapt to new tasks rapidly from few training examples.

## [Multilingual and cross-lingual document classification: A meta-learning approach](https://arxiv.org/pdf/2101.11302.pdf)
	1. Prototypical Networks
		1. Typically they consist of an embedding network and a distance function. The embedding network is used to encode all samples in a support set and compute prototypes per class by computing the mean of the sample encodings of that respective class
	2. Model Agnostic Meta Learning 
		1. optimization-based method
	3. Reptile 
		1. first-order optimization-based meta-learning algorithm which is designed to move the weights towards a manifold of the weighted averages of task-specific parameters

they propose -> ProtoMAMLn



# [NAS-BERT: Task-Agnostic and Adaptive-Size BERT Compression with Neural Architecture Search](https://dl.acm.org/doi/abs/10.1145/3447548.3467262?casa_token=lEwIL7JUL0MAAAAA:Ly4WetO12vG-GCeC7CCRJDn21BeSBdE6_Wauhd4KbvPg0rtw0n11Q_pjOHs41LG1gJfPLQZge-038A)

# param optim in a compression task , only 2x param size reduction (110m to 60m)
MNLI QQP QNLI CoLA SST-2 STS-B RTE MRPC




# [Meta Fine-Tuning Neural Language Models for Multi-Domain Text Mining](https://arxiv.org/pdf/2003.13003v2.pdf)
------------------------------------------------

# [meta learning benchmarks](https://paperswithcode.com/task/meta-learning#benchmarks)

1. https://github.com/learnables/learn2learn
2. https://github.com/facebookresearch/higher



# [FLEX: Unifying Evaluation for Few-Shot NLP](https://paperswithcode.com/paper/flex-unifying-evaluation-for-few-shot-nlp)