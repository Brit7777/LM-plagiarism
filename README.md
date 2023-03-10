# LM-plagiarism

Repository of the paper "Do Language Models Plagiarize?", Proceedings of the ACM Web Conference 2023

**Due to a large size of data, we uploaded everything in [Zenodo](https://zenodo.org/record/7634243#.Y-p9ES-B0dh).**

## Training Corpus
GPT-2's pre-training data is accessible via this [link](https://skylion007.github.io/OpenWebTextCorpus/). You can find all fine-tuning datasets we used for our experiments in the ``finetuning_data.zip`` file. Special thanks to original creators of fine-tuning datasets: [ArXiV](https://zenodo.org/record/2533436#.Y-p9iy-B0dg), [Cord-19](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7251955/), and [Patent Claims](https://arxiv.org/pdf/1907.02052.pdf).

## GPT-2 Generated Text
All GPT-2 generated texts can be found in the ``GPT_generated_text.zip`` file. Documents in the txt file can be seperated by '===================='. Note that texts generated by pre-trained GPT-2 are originally from [OpenAI](https://github.com/openai/gpt-2-output-dataset). If the file includes '_v2', this means it is a secondary file to fulfill the document count. For example, in the PatentGPT folder, there are ``patentGPT_10000_temp.txt`` and ``PatentGPT_10000_temp_v2.txt``. They both are generated by PatentGPT with temperature a setting, and a total number of documents sums up to 10000.  We also uploaded fine-tuned models' checkpoints ``checkpoints.zip``.

## Automatic Plagiarism Detection
**STEP 1. Finding Top-𝑛′ Candidate Documents**

In our work, we levearge Elasticsearch to store a training corpus and retrieve candidate documents for plagiarism. A detailed description of Elasticsearch setup can be found here: <https://www.elastic.co/guide/en/elasticsearch/reference/current/setup.html>.

**STEP 2. Finding Plagiarized Text Pairs and Plagiarism Type**

To extract plagiarism types and locations, go to the ``plagiarism_detection_tool.zip`` file and run ``PAN2015_plagiarism_detection.py`` using this command:
```
python PAN2015_plagiarism_detection.py
```
Make sure to replace these values ``OUTPUT_DIRECTORY, FILE, INDEX`` with your own configurations in the source code prior to running. Great thanks to the original creator of this tool which is available at <https://www.gelbukh.com/plagiarism-detection/PAN-2015/>.

## Analysis
You can refer to ``analysis.ipnyb`` to reproduce the reported plagiarism results. We uploaded all identified plagiarism cases in the ``plagiarism_cases.zip`` file. Please note that ``source_id`` represents the index of machine-generated texts and ``susp_id`` represents the index of training samples. These numbers may not be reproducible when you run your own experiments because it depends on how training samples are indexed in Elasticsearch. 

---
Please cite our paper with the following Bibtex:
```

```
