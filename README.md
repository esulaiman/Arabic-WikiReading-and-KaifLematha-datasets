# Arabic WikiReading and KaifLematha Datasets
This repository contains Arabic reading comprehension datasets Arabic WikiReading (factoid dataset) and KaifLematha (non-factoid dataset)
 |               | train | development| test | validated dev.| validated test | total |
 | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
 | Arabic WikiReading  | 79,048  | 9806  | 9789  | 9485  | 7379  | 98,643 |
 | KaifLematha  | 5563  | 619  | 579  | -  | -  | 6761  |
## Arabic WikiReading dataset 
### Arabic WikiReading dataset collection
![Arabic WikiReading Sample.](Arabic_WikiReading_Sample.png)
The Arabic WikiReading dataset was constructed in four steps: Wikipedia paragraph curation, query–answer pair collection from the Wikidata knowledge base, consolidation of the query–answer pairs to the Wikipedia paragraphs, and construction of the validated develop- ment and test sets. The dataset was automatically constructed under a distant supervision strategy, adopting Wikidata as a source for query-answer pairs and Wikipedia for Arabic articles. Arabic articles were collected from [arwikiExtracts](https://github.com/motazsaad/arwikiExtracts), which contains documents’ extracts that were collected by parsing the Arabic _20190920_ version of Wikipedia dump.

We extracted an Arabic Wikidata dump (sized 10.5G) from the _20190909.JSON_ dump. For each statement we extracted the item label, property and the value to form (item, property, answer) triple, where the answer represents the value of this property given the item. To construct the Arabic WikiReading dataset, we replaced each Wikidata item in the (item, property, answer) triples with the appropriate Wikipedia curated paragraph, knowing the title of the Wikipedia article that matches the item in the collected triples, and discarding any item not linked to Wikipedia articles. 
### Dataset Format
The format for Arabic WikiReading follow
```
file.json
├── "data"
│   └── [i]
│                ├── “title”: “document title”
│                ├── "context": "paragraph text"
│                └── "qas"
│                   └── [k]
│                      ├── "answers"
│                      │   └── [l]
│                      │       ├── "answer_start": N
│                      │       └── "text": "answer"
│                      ├── "id": "<uuid>"
│                      └── "question": "paragraph question?"
└── "version": 1.1
```
