# LM-plagiarism

Repository of the paper "Do Language Models Plagiarize?", Proceedings of the ACM Web Conference 2023

**Due to a large size of data, we uploaded everything in [Zenodo]().**

## Training Corpus
GPT-2's pre-training data is accessible via this [link](https://skylion007.github.io/OpenWebTextCorpus/). You can find all fine-tuning datasets in the ``finetuning_data`` folder.

## GPT-2 Generated Text
All GPT-2 generated texts can be found in the ``GPT_generated_text`` folder. Note that texts generated by pre-trained GPT-2 are originally from [OpenAI](https://github.com/openai/gpt-2-output-dataset). If the file includes '_v2', this means it is a secondary file to fulfill the document count. For example, in the PatentGPT folder, there are ``patentGPT_10000_temp.txt`` and ``PatentGPT_10000_temp_v2.txt``. They both are generated by PatentGPT with temperature a setting, and a total number of documents sums up to 10000.  We also uploaded fine-tuned models' checkpoints ``checkpoints.zip``.

## Automatic Plagiarism Detection
**STEP 1. Finding Top-𝑛′ Candidate Documents**

In our work, we levearge Elasticsearch to store a training corpus and retrieve candidate documents for plagiarism. A detailed description of Elasticsearch setup can be found here: <https://www.elastic.co/guide/en/elasticsearch/reference/current/setup.html>.

**STEP 2. Finding Plagiarized Text Pairs and Plagiarism Type**

To extract plagiarism types and locations, go to the ``plagiarism_detection_tool`` folder and run ``PAN2015_plagiarism_detection.py`` using this command:
```
python PAN2015_plagiarism_detection.py
```
Make sure to replace these values () with your own file destinations in the source code prior to running. Great thanks to the original creator of this tool which is available at <https://www.gelbukh.com/plagiarism-detection/PAN-2015/>.

## Analysis
You can refer to ``analysis.ipnyb`` to reproduce the reported plagiarism results. We uploaded all identified plagiarism cases in the ``plagiarism_cases`` folder.

---
Please cite our paper with the following Bibtex:
```

```
