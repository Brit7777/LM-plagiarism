# LM-plagiarism

Repository of the paper "Do Language Models Plagiarize?", Proceedings of the ACM Web Conference 2023


## Training Corpus
GPT-2's pre-training data is accessible via this [link](https://skylion007.github.io/OpenWebTextCorpus/). You can find all fine-tuning datasets in the ``finetuning_data`` folder in Zenodo.

## Automatic Plagiarism Detection
**STEP 1. Finding Top-𝑛′ Candidate Documents**

In our work, we levearge Elasticsearch to store a training corpus and retrieve candidate documents for plagiarism. A detailed description of Elasticsearch setup can be found here: (https://www.elastic.co/guide/en/elasticsearch/reference/current/setup.html).

**STEP 2. Finding Plagiarized Text Pairs and Plagiarism Type**

