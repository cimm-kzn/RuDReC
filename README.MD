The Russian Drug Reaction Corpus and Neural Models for Drug Reactions and Effectiveness Detection in User Reviews (RuDReC)
---
The Russian Drug Reaction Corpus (RuDReC) [1] is a new partially annotated corpus of consumer reviews in Russian about pharmaceutical products for the detection of health-related named entities and the effectiveness of pharmaceutical products. 

The corpus itself consists of two parts, the raw one and the labelled one. The raw part includes 1.4 million health-related user-generated texts collected from various Internet sources, including social media. The labelled part contains 500 consumer reviews about drug therapy with drug- and disease-related information. Labels for sentences include health-related issues or their absence. The sentences with one are additionally labelled at the expression level for identification of fine-grained subtypes such as drug classes and drug forms, drug indications, and drug reactions. Further, we present a baseline model for named entity recognition (NER) and multi-label sentence classification tasks on this corpus. The macro F1 score of 74.85% in the NER task was achieved by our RuDR-BERT model. For the sentence classification task, our model achieves the macro F1 score of 68.82% gaining 7.47% over the score of BERT model trained on Russian data. 

We make the RuDReC corpus and pretrained weights of domain-specific BERT models freely available:

1. Annotated part of the RuDReC corpus (500 reviews with sentence-level and entity-level annotations). \
   link: https://yadi.sk/d/PzrYMx02lhjSDg
2. Annotated part of the RuDReC corpus with concept ids in json format (500 reviews with sentence-level and entity-level annotations). You can find the 'rudrec_annotated.json' file in data directory or download by \
    link: https://yadi.sk/d/-enD7Gesf7sMRA
3. Raw part of the RuDReC corpus (1.4M reviews). \
   link: https://yadi.sk/d/kCsAhkoLZUuTrQ
   
The Russian Adverse Drug Reaction Corpus of Tweets (RuADReCT)
---

This dataset consists of 9515 tweets describing health issues. Each tweet is labeled for whether it contains information about an adverse side effect that occurred when taking a drug. The files contain the tweet ID, class number, and a script for collecting the source text. The dataset was created as part of The Social Media Mining for Health Applications (#SMM4H) Shared Tasks in a competition for automatically extracting information about the side effects of drugs from tweets. The dataset was a joint effort with the UPenn HLP Center (https://healthlanguageprocessing.org/) and the Yandex.Toloka (https://toloka.ai/datasets?turbo=true).

You can find the corpus in data directory or download from Yandex.Toloka (https://tlk.s3.yandex.net/dataset/RuADReCT.zip).

BERT-based models
---
1. RuDR-BERT - Multilingual, Cased, which pretrained on the raw part of the RuDReC corpus (1.4M reviews). Pre-training was based on the [original BERT code](https://github.com/google-research/bert) provided by Google. In particular, Multi-BERT was for used for initialization; vocabulary of Russian subtokens and parameters are the same as in Multi-BERT. Training details are described in our paper. \
   link: https://yadi.sk/d/-PTn0xhk1PqvgQ
2. EnRuDR-BERT - Multilingual, Cased, which pretrained on the raw part of the RuDReC corpus [1] and the English corpus of health-related comments from [2]. \
   link: https://yadi.sk/d/H5ed7IkOELrezQ
3. EnDR-BERT - Multilingual, Cased, which pretrained on the English corpus of health-related comments from [2]. \
   link: https://drive.google.com/file/d/1OxOGbZJo5ZuCQkeEhTraHrxNh81gZFze/view?usp=sharing

We release our pre-trained models at https://huggingface.co/cimm-kzn 🤗 
 
Examples
---
* [Training **fastText** embeddings on the raw part of our corpus](https://github.com/cimm-kzn/RuDReC/blob/master/examples/Raw_preprocessing.ipynb) 
* [CNN-based classifier on SMM4H Task 2 data (ADR classification)](https://github.com/cimm-kzn/RuDReC/blob/master/examples/Tweets_classification_CNN.ipynb) 
* [BERT-based classifier on SMM4H Task 2 data](https://github.com/Andoree/smm4h_classification/blob/master/SMM4H_2020_ADR_classification.ipynb)
* [Code](https://github.com/cimm-kzn/RuDReC/blob/master/examples/multilabel_text_classification_RuDReC_bert.ipynb) and [colab notebook](https://colab.research.google.com/drive/1g_2W__vi6fuEn8pSma0NXNHbNuebptHF?usp=sharing) on how to train a multi-label classifier on the RuDReC data and use this model for prediction. 
* [Colab notebook](https://colab.research.google.com/drive/12QVJ9ApygShdEyjkwddB380QzbYuQB9D?usp=sharing) on how to use **NER** models for detection of named entities such as drugs and adverse drug reactions.

The trained Russian **fastText** [embeddings](https://drive.google.com/file/d/1su3IYY1avcj95tez69JI8f5qsTng72-I/view?usp=sharing) are freely available. See also [English word embeddings](https://github.com/dartrevan/ChemTextMining/blob/master/word2vec/Health_2.5mreviews.s200.w10.n5.v15.cbow.bin) trained on 2.5M health-related English comments [2].


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
[2] Tutubalina, E. V., Miftahutdinov, Z. S., Nugmanov, R. I., Madzhidov, T. I., Nikolenko, S. I., Alimova, I. S., & Tropsha, A. E. (2017). Using semantic analysis of texts for the identification of drugs with similar therapeutic effects. Russian Chemical Bulletin, 66(11), 2180-2189.
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
