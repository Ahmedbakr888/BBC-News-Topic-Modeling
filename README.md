# BBC News Topic Modeling: LDA vs NMF

Discover hidden topics in BBC News articles using **unsupervised NLP** techniques and compare **Latent Dirichlet Allocation (LDA)** with **Non-negative Matrix Factorization (NMF)**.

---

## 📰 Dataset

**BBC News RSS Feeds Dataset**

* Source: [Kaggle BBC News RSS Feeds](https://www.kaggle.com/gpreda/bbc-news-rss-feeds)
* Columns: title, pubDate, guid, link, description
* Combined text used: title + description

Description: Self-updating dataset that collects RSS feeds from BBC News using a scheduled Kaggle notebook. Ideal for unsupervised topic modeling and text analysis.

---

## 🛠 Tools & Libraries

* Python 3.12
* NLP: nltk, spacy
* Topic Modeling: gensim, scikit-learn
* Visualization: pyLDAvis, wordcloud, matplotlib
* Data Handling: pandas, numpy

---

## 🧹 Preprocessing

* Lowercased all text
* Removed URLs & non-alphabetic characters
* Removed stopwords
* Lemmatized words using spaCy
* Combined title + description for better context

Example cleaned text:
"government plan election minister parliament policy vote …"

---

## 🔎 Topic Modeling

### 1️⃣ LDA (Gensim)

* Uses CountVectorizer (Bag-of-Words)
* 5 topics extracted
* Example topics:
  Topic 0: government election minister parliament party vote policy …
  Topic 1: match team win coach player league game …

### 2️⃣ NMF (Scikit-learn)

* Uses TF-IDF vectorization
* 5 topics extracted
* Example topics:
  Topic 0: company market shares economy investment stock business …
  Topic 1: football match team player coach league …

---

## 📊 Visualization

* WordClouds for NMF topics:
  ![WordCloud Example](images/wordcloud_topic0.png)

* Interactive pyLDAvis for LDA topics:

  * Topic distance map
  * Word relevance per topic
  * Inter-topic similarity

---

## 📈 Evaluation

| Model | Coherence Score |
| ----- | --------------- |
| LDA   | 0.4081          |
| NMF   | 0.7167          |

Conclusion:

* NMF produced clearer, more distinct topics.
* LDA is useful for probabilistic interpretation but topics overlapped more.
* Coherence score confirms NMF outperformed LDA on this dataset.

---

## 💻 How to Run

1. Clone the repository:
   `git clone https://github.com/YOUR_USERNAME/bbc-news-topic-modeling.git`

2. Install dependencies:
   `pip install -r requirements.txt`

3. Run the notebook `BBC_News_Topic_Modeling.ipynb` on Kaggle or locally.

---

## 🔗 Dataset

[Download BBC News RSS Feeds Dataset](https://www.kaggle.com/gpreda/bbc-news-rss-feeds)

---

## 📌 References

* [Gensim LDA Documentation](https://radimrehurek.com/gensim/models/ldamodel.html)
* [Scikit-learn NMF Documentation](https://scikit-learn.org/stable/modules/generated/sklearn.decomposition.NMF.html)
* [pyLDAvis Documentation](https://pyldavis.readthedocs.io/)

---

## ⚡ Next Steps

* Experiment with different numbers of topics (5–10)
* Compare topic stability over time (using pubDate)
* Integrate sentiment analysis for richer insights
* Deploy a simple dashboard with WordClouds and pyLDAvis visualization
