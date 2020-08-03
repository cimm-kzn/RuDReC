The Russian Drug Reaction Corpus and Neural Models for Drug Reactions and Effectiveness Detection in User Reviews
---

<p style="text-align: center;">
Overview: This repository contains additional materials of the paper "The Russian Drug Reaction Corpus and Neural Models for Drug Reactions and Effectiveness Detection in User Reviews" [1]
</p>
Abstract: The Russian Drug Reaction Corpus (RuDReC) is a new partially annotated corpus of consumer reviews in Russian about pharmaceutical products for the detection of health-related named entities and the effectiveness of pharmaceutical products. The corpus itself consists of two parts, the raw one and the labelled one. The raw part includes 1.4 million health-related user-generated texts collected from various Internet sources, including social media. The labelled part contains 500 consumer reviews about drug therapy with drug- and disease-related information. Labels for sentences include health-related issues or their absence. The sentences with one are additionally labelled at the expression level for identification of fine-grained subtypes such as drug classes and drug forms, drug indications, and drug reactions. Further, we present a baseline model for named entity recognition (NER) and multi-label sentence classification tasks on this corpus. The macro F1 score of 74.85% in the NER task was achieved by our RuDR-BERT model. For the sentence classification task, our model achieves the macro F1 score of 68.82% gaining 7.47% over the score of BERT model trained on Russian data. 

\
We make the RuDReC corpus and pretrained weights of domain-specific BERT models freely available:

1. Annotated part of the RuDReC corpus (500 reviews with sentence-level and entity-level annotations). \
   link: https://yadi.sk/d/PzrYMx02lhjSDg
2. Raw part of the RuDReC corpus (1.4M reviews). \
   link: https://yadi.sk/d/kCsAhkoLZUuTrQ
3. RuDR-BERT - Multilingual, Cased, which pretrained on the raw part of the RuDReC corpus (1.4M reviews). Pre-training was based on the [original BERT code](https://github.com/google-research/bert) provided by Google. In particular, Multi-BERT was for used for initialization; vocabulary of Russian subtokens and parameters are the same as in Multi-BERT. Training details are described in our paper. \
   link: https://yadi.sk/d/-PTn0xhk1PqvgQ
4. EnRuDR-BERT - Multilingual, Cased, which pretrained on the raw part of the RuDReC corpus [1] and the English corpus of health-related comments from [2]. We note that this model is currently under development. \
   link: https://yadi.sk/d/H5ed7IkOELrezQ
5. EnDR-BERT - Multilingual, Cased, which pretrained on the English corpus of health-related comments from [2]. \
   link: https://drive.google.com/file/d/1OxOGbZJo5ZuCQkeEhTraHrxNh81gZFze/view?usp=sharing

Examples
---

[This example](https://github.com/cimm-kzn/RuDReC/blob/master/examples/Raw_preprocessing.ipynb) shows you how to use the raw part of this corpus for training **fastText** embeddings.  The trained Russian [embeddings](https://drive.google.com/file/d/1su3IYY1avcj95tez69JI8f5qsTng72-I/view?usp=sharing) are freely available. \
[This example](https://github.com/cimm-kzn/RuDReC/blob/master/examples/Tweets_classification_CNN.ipynb) shows you how to train CNN-based classifier on SMM4H 2020 Task 2 Russian data. For English, see also [word embeddings](https://github.com/dartrevan/ChemTextMining/blob/master/word2vec/Health_2.5mreviews.s200.w10.n5.v15.cbow.bin) trained on 2.5M health-related English comments [2]. \
[This example](https://github.com/cimm-kzn/RuDReC/blob/master/examples/multilabel_text_classification_RuDReC_bert.ipynb) (also available via [Colab](https://colab.research.google.com/drive/1g_2W__vi6fuEn8pSma0NXNHbNuebptHF?usp=sharing)) shows how to train a multi-label classifier on our data and use this model for prediction.  \
This example (available via [Colab](https://colab.research.google.com/drive/12QVJ9ApygShdEyjkwddB380QzbYuQB9D?usp=sharing)) shows how to use NER models for detection of named entities such as drugs and adverse drug reactions.



Citing & Authors
---
If you find this repository helpful, feel free to cite our publication:

[1] https://arxiv.org/abs/2004.03659
```
 @article{10.1093/bioinformatics/btaa675,
    author = {Tutubalina, Elena and Alimova, Ilseyar and Miftahutdinov, Zulfat and Sakhovskiy, Andrey and Malykh, Valentin and Nikolenko, Sergey},
    title = {The Russian Drug Reaction Corpus and Neural Models for Drug Reactions and Effectiveness Detection in User Reviews},
    journal = {Bioinformatics},
    year = {2020},
    month = {07},
    issn = {1367-4803},
    doi = {10.1093/bioinformatics/btaa675},
    url = {https://doi.org/10.1093/bioinformatics/btaa675},
    note = {btaa675},
    eprint = {https://academic.oup.com/bioinformatics/article-pdf/doi/10.1093/bioinformatics/btaa675/33539752/btaa675.pdf},
}
```
[2] Tutubalina, EV and Miftahutdinov, Z Sh and Nugmanov, RI and Madzhidov, TI and Nikolenko, SI and Alimova, IS and Tropsha, AE Using semantic analysis of texts for the identification of drugs with similar therapeutic effects.
   [link to paper](https://www.researchgate.net/profile/Elena_Tutubalina/publication/323751823_Using_semantic_analysis_of_texts_for_the_identification_of_drugs_with_similar_therapeutic_effects/links/5bf7cfc3299bf1a0202cbc1f/Using-semantic-analysis-of-texts-for-the-identification-of-drugs-with-similar-therapeutic-effects.pdf)
```
@article{tutubalina2017using,
    title={Using semantic analysis of texts for the identification of drugs with similar therapeutic effects},
    author={Tutubalina, EV and Miftahutdinov, Z Sh and Nugmanov, RI and Madzhidov, TI and Nikolenko, SI and Alimova, IS and Tropsha, AE},
    journal={Russian Chemical Bulletin},
    volume={66},
    number={11},
    pages={2180--2189},
    year={2017},
    publisher={Springer}
}
```
