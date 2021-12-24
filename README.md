# ABSA-NLP-project

This is my final attestation project for Data Science program at Innopolis University.

**The aim of the project is to perform aspect-based sentiment analysis of Amazon reviews.**

Aspects are product features (like "quiet keyboard" or "nice image quality") which are usually mentioned in a positive/negative way in customer reviews. Extracting such aspects and labeling them as positive or negative could be useful for summarizing customer opinions. This result can be used both by sellers to analyze customer feedback and by potential buyers to make purchasing decisions.

This project covers the following steps:
1. **01_extract_aspects.ipynb** - Extracting product aspects that meet chosen patterns (adj+noun and noun+be+adj) using spaCy POS-tagging and dependency parsing.

2. **02_bert_fine-tuning.ipynb** - Fine-tuning BERT for binary classification of aspect sentiment (positive/negative) using labeled datasets by [Bing Liu et al.](https://www.cs.uic.edu/~liub/FBS/sentiment-analysis.html)

3. **03_make_predictions.ipynb** - Predicting sentiment class of extracted aspects (from step 1) and generating summary of product reviews based on N most frequent aspects.

All jupyter notebooks are meant for Google Colab and might need some adjustments to be run locally.

Results of this project show high accuracy score in terms of utilizing BERT for sentiment analysis: 0.92 on test data from Bing Liu et al. dataset and 0.88 on extracted aspects from step 1. Small decrease in accuracy might be explained by the fact that 1) aspects were extracted based on slightly different logic comparing to Bing Liu et al. dataset used for BERT fine-tuning; 2) not all extracted aspects were relevant to the product. The latter point is important to note: 32% of extracted aspects were not truly product features or were related to other products or customer experience (see details in **/output/Analysis of Apex AD2600 Progressive-scan DVD player.xlsx**). Therefore the algorithm of extracting product aspects needs substantial improvements.

More details about the results of this project can be found in **Kireeva_DS_final_attestation_presentation.pdf** (available in Russian).
