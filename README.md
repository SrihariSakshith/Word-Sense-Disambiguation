# Word Sense Disambiguation

__Natural Language Processing (Dr. Seba Susan)__

[📘 Path Length Similarity](notebooks/path-similarity-metric.ipynb) |
[📘 Resnik Similarity](notebooks/resnik-similarity.ipynb) |
[📗 Naïve Disambiguation](notebooks/naive-disambiguation.ipynb) |
[📗 Simple LESK Algorithm](notebooks/simple-lesk-algorithm.ipynb) |
[✒ Report](assets/nlp-wsd.pdf)

![booster](assets/booster.png)

## Overview
- [Introduction](#introduction)
- [Setup](#setup)
- [Naïve Disambiguation](#naïve-disambiguation)
- [Simple LESK Algorithm Disambiguation](#simple-lesk-similarity-disambiguation)
- [Path Length Similarity Disambiguation](#path-length-similarity-disambiguation)
- [Resnik Similarity Disambiguation](#resnik-similarity-disambiguation)
- [Bibliography](#bibliography)

---

## Introduction
We explore 4 different metrics to compare similarity and disambiguate words.  
For the 4 different methods refer to the Jupyter notebooks below:

### Notebooks
1. [Naive Disambiguation](notebooks/naive-disambiguation.ipynb)
2. [Simple LESK Algorithm Disambiguation](notebooks/simple-lesk-algorithm.ipynb)
3. [Path Length Similarity Metric](notebooks/path-similarity-metric.ipynb)
4. [Resnik Similarity Metric](notebooks/resnik-similarity.ipynb)

---

## Setup

Clone the repository, create a virtual environment, activate it, and install dependencies:

```bash
git clone https://github.com/anishLearnsToCode/word-sense-disambiguation.git
cd word-sense-disambiguation

# Create a virtual environment
python -m venv myenv

# Activate virtual environment
# On Windows (PowerShell):
myenv\Scripts\Activate
# On macOS/Linux:
source myenv/bin/activate

# Install dependencies
pip install -r requirements.txt
````

---

## Naïve Disambiguation

Run the Naïve Disambiguation script:

```bash
python -m src.naive_method
```

Example output:

```
Enter word for disambiguation: bank
Definition: a large natural stream of water (larger than a creek)
Examples:
['they pulled the canoe up on the bank', 'he sat on the bank of the river and watched the currents']
```

See a running example with explanation in
[this notebook](notebooks/naive-disambiguation.ipynb).

---

## Simple LESK Similarity Disambiguation

Run the Simple LESK Algorithm script:

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

## Path Length Similarity Disambiguation

Run the Path Length Similarity script:

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

For resume similarity computation:

```bash
python -m src.path_similarity_resume
```

See results [here](assets/path_similarity_matrix.txt).

---

## Resnik Similarity Disambiguation

Run the Resnik Similarity script:

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

For resume similarity computation:

```bash
python -m src.resnik_similarity_resume
```

---

## Bibliography

1. [Speech & Language Processing \~Jurafsky](https://web.stanford.edu/~jurafsky/slp3/)
2. [nltk](https://www.nltk.org/)
3. [pickle](https://docs.python.org/3/library/pickle.html)
4. [pandas](https://pandas.pydata.org/)
5. [numpy](https://numpy.org/)
6. [wordnet interface](https://www.nltk.org/howto/wordnet.html)

---

### Acknowledgement

This project is based on [word-sense-disambiguation](https://github.com/anishLearnsToCode/word-sense-disambiguation)
by **anishLearnsToCode**, licensed under the [MIT License](LICENSE).

