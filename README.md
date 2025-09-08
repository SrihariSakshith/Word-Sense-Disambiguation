# 🌐 Word Sense Disambiguation (WSD)

Welcome to **Word Sense Disambiguation (WSD)** — a project exploring multiple NLP algorithms to determine the correct meaning (sense) of a word based on its context.  

📚 Built as part of **Natural Language Processing (NLP)** coursework (Dr. Seba Susan).  

---

## 🔗 Quick Links
- [📘 Path Length Similarity Notebook](notebooks/path-similarity-metric.ipynb)
- [📘 Resnik Similarity Notebook](notebooks/resnik-similarity.ipynb)
- [📗 Naïve Disambiguation Notebook](notebooks/naive-disambiguation.ipynb)
- [📗 Simple LESK Algorithm Notebook](notebooks/simple-lesk-algorithm.ipynb)
- [📄 Report](assets/nlp-wsd.pdf)

![WSD](assets/booster.png)

---

## 📖 Table of Contents
1. [Introduction](#-introduction)
2. [Environment Setup](#-environment-setup)
3. [Run Naïve Disambiguation](#-run-naïve-disambiguation)
4. [Run Simple LESK Algorithm](#-run-simple-lesk-algorithm)
5. [Run Path Length Similarity](#-run-path-length-similarity)
6. [Run Resnik Similarity](#-run-resnik-similarity)
7. [References](#-references)
8. [Acknowledgements](#-acknowledgements)

---

## 📜 Introduction

This project demonstrates **four different methods** for word sense disambiguation using the NLTK WordNet interface:

1. Naïve Disambiguation (returns first sense in WordNet)
2. Simple LESK Algorithm (overlap-based)
3. Path Length Similarity (hypernym path length metric)
4. Resnik Similarity (information-theoretic metric)

The algorithms are implemented in Python, and detailed explanations are available in Jupyter notebooks.  

---

## ⚙️ Environment Setup

Clone this repository and set up a virtual environment to get started:

```bash
# Clone the repo
git clone https://github.com/SrihariSakshith/Word-Sense-Disambiguation.git
cd Word-Sense-Disambiguation

# Create a virtual environment
python -m venv myenv

# Activate the environment
# Windows (PowerShell)
myenv\Scripts\Activate
# macOS/Linux
source myenv/bin/activate

# Install dependencies
pip install -r requirements.txt
````

---

## 🔍 Run Naïve Disambiguation

This method selects the **first sense** returned by WordNet.

```bash
python -m src.naive_method
```

Example:

```
Enter word for disambiguation: bank
Definition: a large natural stream of water (larger than a creek)
Examples:
['they pulled the canoe up on the bank', 'he sat on the bank of the river and watched the currents']
```

📓 See the notebook: [Naïve Disambiguation](notebooks/naive-disambiguation.ipynb)

---

## 🧩 Run Simple LESK Algorithm

This approach uses the **overlap of gloss words** (context words) with definitions and examples.

```bash
python -m src.simple_lesk_algorithm
```

Example:

```
Enter the Gloss (document): i like a hot cup of java in the morning
Enter word for disambiguation: java
The disambiguated meaning is: a beverage consisting of an infusion of ground coffee beans
The weight vector is: [0, 0.28768207245178085, 0]
```

---

## 🔗 Run Path Length Similarity

This computes similarity based on the **shortest path** between synsets in WordNet.

```bash
python -m src.path_length_similarity
```

Example:

```
Enter first word: dog
Enter second word: wolf
Dog Definition: a member of the genus Canis...
Wolf Definition: any of various predatory carnivorous canine mammals...
similarity: -0.6931471805599453
```

Compare resume keywords:

```bash
python -m src.path_similarity_resume
```

🔍 Results: [Path Similarity Matrix](assets/path_similarity_matrix.txt)

---

## 📊 Run Resnik Similarity

This method uses **information content** from WordNet to measure similarity.

```bash
python -m src.resnik_similarity
```

Example:

```
Enter the first word: java
Enter the second word: language
Java Definition: a platform-independent object-oriented programming language
Language Definition: a systematic means of communicating by the use of sounds or conventional symbols
similarity: 5.792086967391197
```

Compare resume keywords:

```bash
python -m src.resnik_similarity_resume
```

📓 Notebook: [Resnik Similarity](notebooks/resnik-similarity.ipynb)

---

## 📚 References

1. [Speech & Language Processing \~Jurafsky](https://web.stanford.edu/~jurafsky/slp3/)
2. [NLTK Documentation](https://www.nltk.org/)
3. [pickle](https://docs.python.org/3/library/pickle.html)
4. [pandas](https://pandas.pydata.org/)
5. [numpy](https://numpy.org/)
6. [WordNet Interface](https://www.nltk.org/howto/wordnet.html)

---

## 🙌 Acknowledgements

This project was inspired by the open-source repository [word-sense-disambiguation](https://github.com/anishLearnsToCode/word-sense-disambiguation) by **anishLearnsToCode** and is distributed under the [MIT License](LICENSE).
