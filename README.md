# Arabic-WikiReading-and-KaifLematha-datasets
This repository contains Arabic reading comprehension datasets Arabic WikiReading (factoid dataset) and KaifLematha (non-factoid dataset)
# Arabic WikiReading dataset 
The format foe Arabic WikiReading follow
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
