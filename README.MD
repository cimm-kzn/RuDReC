The Russian Drug Reaction Corpus and Neural Models for Drug Reactions and Effectiveness Detection in User Reviews
---

<p style="text-align: center;">
Overview: This repository contains additional materials of the paper "The Russian Drug Reaction Corpus and Neural Models for Drug Reactions and Effectiveness Detection in User Reviews" [1]
</p>
Abstract: The Russian Drug Reaction Corpus (RuDReC) is a new partially annotated corpus of consumer reviews in Russian about pharmaceutical products for the detection of health-related named entities and the effectiveness of pharmaceutical products. The corpus itself consists of two parts, the raw one and the labelled one. The raw part includes 1.4 million health-related user-generated texts collected from various Internet sources, including social media. The labelled part contains 500 consumer reviews about drug therapy with drug- and disease-related information. Labels for sentences include health-related issues or their absence. The sentences with one are additionally labelled at the expression level for identification of fine-grained subtypes such as drug classes and drug forms, drug indications, and drug reactions. Further, we present a baseline model for named entity recognition (NER) and multi-label sentence classification tasks on this corpus. The macro F1 score of 74.85% in the NER task was achieved by our RuDR-BERT model. For the sentence classification task, our model achieves the macro F1 score of 68.82% gaining 7.47% over the score of BERT model trained on Russian data. 

We make the RuDReC corpus and pretrained weights of domain-specific BERT models freely available:
1. Annotated part of the RuDReC corpus (500 reviews with sentence-level and entity-level annotations). \
   link: https://yadi.sk/d/gSeGdF6coO_brQ
2. Raw part of the RuDReC corpus (1.4M reviews). \
   link: https://yadi.sk/d/kCsAhkoLZUuTrQ
3. RuDR-BERT - Multilingual, Cased, which pretrained on the raw part of the RuDReC corpus (1.4M reviews). Multi-BERT was for used for initialization; vocabulary of Russian subtokens and parameters are the same as in Multi-BERT. \
   link: https://yadi.sk/d/-PTn0xhk1PqvgQ


Please refer to our paper for the detailed description of our corpus 
[1]
```
@misc{tutubalina2020russian,
    title={The Russian Drug Reaction Corpus and Neural Models for Drug Reactions and Effectiveness Detection in User Reviews},
    author={Elena Tutubalina and Ilseyar Alimova and Zulfat Miftahutdinov and Andrey Sakhovskiy and Valentin Malykh and Sergey Nikolenko},
    year={2020},
    eprint={2004.03659},
    archivePrefix={arXiv},
    primaryClass={cs.CL}
}
```
