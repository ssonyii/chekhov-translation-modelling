## Translation as Modelling
### A Computational Comparison of Three English Translations of Chekhov's *The Lady with the Dog*

This notebook contains code the code developed for the final project of the course 'MODELLING AND VISUALIZING TEXTUAL DATA'.

### Research Question

> If a translation is a model of the original text, do different translations of the same story produce measurably different models?

This project applies a Natural Language Processing pipeline to three public-domain English translations of Anton Chekhov's short story *The Lady with the Dog* (1899), asking whether computational tools can make the translators' interpretive choices visible as quantitative differences.

---

### Theoretical framing

A model is always a model of something, by someone, for a purpose. In these terms, a translation can be defined as a model of the original text created by a translator to enable a broader audience to read and understand the work in their own language.

A translation is therefore neither the original nor a neutral copy of it — it is an interpretive act shaped by processes of perception, selection, and transformation.

Following Franco Moretti's concept of operationalization (*"Operationalizing": Or, the Function of Measurement in Modern Literary Theory*, 2013), this project asks: can NLP tools make the translators' interpretive choices visible as measurable textual differences?

To adress this question, I analyzed three English translations of "The Lady with the Dog", a short story written by Anton Chekhov in 1899. 

| Translator | Year | Source |
|---|---|---|
| Constance Garnett | 1917 | The Lady with the Dog and Other Stories, Project Gutenberg |
| S. S. Koteliansky & Gilbert Cannan | 1917 | The House with the Mezzanine and Other Stories, Project Gutenberg|
| Ivy Litvinov | 1973 | The Lady with the Dog , Wikisource |

All three are in the public domain.

---

### Methods

All analysis was performed in Python using the following libraries and tools:

| Tool | Purpose |
|---|---|
| `re, requests, pypdf` | Text cleaning, story extraction |
| `nltk.word_tokenize` | Tokenization |
| `nltk.corpus.stopwords` | Stopword removal |
| `nltk.stem.WordNetLemmatizer` | Lemmatization |
| `nltk.text.Text` | KWIC concordances |
| `nltk.sentiment.vader` | Sentiment analysis (sliding window) |
| `collections.Counter` | Frequency distributions |
| `pandas` | Frequency tables |
| `plotly.graph_objects` | Visualizations |


I used the following metrics:

1. Type-Token Ratio (TTR)
2. Frequency Analysis
3. Key Motif Frequencies
4. KWIC Concordances
5. Sentiment Trajectory
6. Pronoun Analysis
7. Hapax Legomena
8. Sentence Lengh and POS Density

---

### Repository Structure

```
translation-as-modelling/
│
├── README.md                        # this file
├── translation_as_modelling.ipynb   # main analysis notebook
│
└──  data/
   ├── garnett_lady_with_the_dog.txt       # full text of Garnett's translation
   ├── koteliansky_lady_with_toy_dog.txt   # full text of Koteliansky and Cannon's translation
   └── litvinov_lady_with_the_dog.txt      # full text of Litvinov's translation

```

---

### How to use

You don't need to rerun everything — please feel free to jump straight to the 'Discussion' and 'Conclusion' chapters. All cell outputs are visible and available for review.

To reproduce my workflow you can find the instructions below:

1. Clone this repository.
2. Open the folder in Google Colab or any other IDE.
3. Install the dependencies: `pip install nltk matplotlib pandas`
4. Run all cells from top to bottom. The notebook will automatically fetch the texts. No local files needed.
