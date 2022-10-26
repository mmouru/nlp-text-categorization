# About the project

Project report in: 

***Step1***
```
Creating database from RSNA journal of Radiology articles https://pubs.rsna.org/journal/radiology.
Everything considering database and step1 can be viewed in [journal-database](journal_database).
First 100 links to each topic were gathered with script in [links-to-journals.ipynb](journal_database/links_to_journals_ipynb). All links were saved in journal_links_db.xlsx excel file.

All articles were scraped with script to collect title, authors and abstracts, keywords were not present in the journal.
All data was saved in database100.xlsx file. The database was further pre-processed removing stop-words, lowercasing and removing whitespace in [preprocessing.ipynb](journal_database/preprocessing.ipynb) and saved in database100_preprocessed.xlsx file.
```

***Step2***
```
Overlapping of abstracts and titles and topics is calculated using Levenshtein Distance in [step2.ipynb](step2.ipynb).
```


***Step3***
```
Similarities of topic and abstract are calculated using TF-IDF vectorizing in [step3_and_4.ipynb](step3_and_4.ipynb)
```



***Step4***
```
Step 3 is repeated but title vector is used instead. [step3_and_4.ipynb](step3_and_4.ipynb)
```


***Step5***
```
FastText word embedding for abstracts, titles and topics is done in [step5-6-7.ipynb](step5-6-7.ipynb). Pre-trained model for English vocabulary was used to construct these vectors. Model contains 300 dimensions and the number can be reduced. Its public and made by fastText ('cc.en.300.bin')[https://fasttext.cc/docs/en/crawl-vectors.html].
```

***Step6***
```
Word embedding vectors constructed for titles [step5-6-7.ipynb](step5-6-7.ipynb).
```

***Step7**
```
Article titles and abstract were appended together to create extended abstracts and embedding vectors from those were constructed [step5-6-7.ipynb](step5-6-7.ipynb).

```

***Step8***
```
Pre-trained word2vec models were tested but none covered fully the vocabulary in Radiology. Models were trained using datasets [found online](https://github.com/RaRe-Technologies/gensim-data) and these models were further trained with our own vocabulary found in RSNA articles. The training processes are available in [word2vec_models](word2vec_models).

These models were used in [step8.ipynb](step8.ipynb) to build embedding vectors from title, abstract and topics by tokenizing the sentences and calculating mean embedding vector from all words to build sentence vectors.
```

***Step9***
```
Pre-trained BERT model [bert_24_1024_16](https://bert-embedding.readthedocs.io/en/latest/bert_models/bert_models.html) was used in training of the model. Word embedding vectros from abstract and topics was build using these models in [step9.ipynb](step9.ipynb).
```

***Step10***
```
Literature covering the topic of Text categorization/classification was searched to support the findings of this study.
```