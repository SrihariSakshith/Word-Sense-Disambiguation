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
2. [Algorithm Comparison](#-algorithm-comparison)
3. [WSD Pipeline](#-wsd-pipeline)
4. [Environment Setup](#-environment-setup)
5. [Run Naïve Disambiguation](#-run-naïve-disambiguation)
6. [Run Simple LESK Algorithm](#-run-simple-lesk-algorithm)
7. [Run Path Length Similarity](#-run-path-length-similarity)
8. [Run Resnik Similarity](#-run-resnik-similarity)
9. [References](#-references)
10. [Acknowledgements](#-acknowledgements)

---

## 📜 Introduction

This project demonstrates **four different methods** for word sense disambiguation using the NLTK WordNet interface:

1. **Naïve Disambiguation** — Selects the first sense from WordNet.  
2. **Simple LESK Algorithm** — Uses overlap between gloss words and context.  
3. **Path Length Similarity** — Computes semantic similarity using hypernym path length.  
4. **Resnik Similarity** — Measures similarity using information content from a corpus.  

---

## 📊 Algorithm Comparison

| Algorithm                  | Approach                            | Strengths                               | Limitations                                | Complexity |
|----------------------------|------------------------------------|----------------------------------------|--------------------------------------------|------------|
| **Naïve Disambiguation**   | Returns the first sense in WordNet | Fast, simple baseline                  | Not context-aware, often inaccurate       | O(1)       |
| **Simple LESK Algorithm**  | Overlap of gloss & context words   | Lightweight, context-aware             | Limited by WordNet gloss quality          | O(n·m)     |
| **Path Length Similarity** | Shortest path between synsets      | Intuitive, easy to interpret           | Ignores corpus frequency information      | O(V+E)     |
| **Resnik Similarity**      | Information content from corpus    | Statistically grounded, accurate       | Needs a large, tagged corpus              | O(n)       |

---

## 🛠️ WSD Pipeline

Here’s how the disambiguation process works:

![Word Sense Disambiguation Flowchart](diagram.png)

This pipeline helps visualize how context and similarity measures lead to the **most accurate sense** of a word.

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
```

---

## 🔍 Run Naïve Disambiguation

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

📓 Notebook: [Naïve Disambiguation](notebooks/naive-disambiguation.ipynb)

---

## 🧩 Run Simple LESK Algorithm

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

```bash
python -m src.path_length_similarity
```

Example:

```
Enter first word: dog
Enter second word: wolf
similarity: -0.6931471805599453
```

For resume similarity:

```bash
python -m src.path_similarity_resume
```

📄 Results: [Path Similarity Matrix](assets/path_similarity_matrix.txt)

---

## 📊 Run Resnik Similarity

```bash
python -m src.resnik_similarity
```

Example:

```
Enter the first word: java
Enter the second word: language
similarity: 5.792086967391197
```

For resume similarity:

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
