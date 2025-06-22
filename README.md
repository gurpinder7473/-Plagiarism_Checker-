# -Plagiarism_Checker-


# 📄 Plagiarism Checker (Cosine Similarity Based)

This Python project checks the **similarity between two text files** (`.txt`) using **cosine similarity**. It converts raw text into numerical vectors and then computes how closely the documents relate.

---

## ✅ Features

- Compare any two `.txt` files
- Uses cosine similarity to measure closeness
- Helpful for detecting content overlap or plagiarism
- Simple and easy-to-understand implementation

---

## 🧰 Requirements

- Python 3.x
- `sklearn`
- `numpy`

Install dependencies with:

```bash
pip install numpy scikit-learn
```

---

## 🚀 How It Works

1. **Text Preprocessing**: Reads both `.txt` files and extracts the text content.
2. **Vectorization**: Converts text into vector format using **TF-IDF (Term Frequency-Inverse Document Frequency)**.
3. **Cosine Similarity**: Computes similarity score (between 0 and 1) using the angle between the two vectors.

---

## 🧪 Sample Code Snippet

```python
from sklearn.feature_extraction.text import TfidfVectorizer
from sklearn.metrics.pairwise import cosine_similarity

def calculate_similarity(file1, file2):
    with open(file1, 'r') as f1, open(file2, 'r') as f2:
        documents = [f1.read(), f2.read()]

    tfidf = TfidfVectorizer()
    vector_matrix = tfidf.fit_transform(documents)
    similarity = cosine_similarity(vector_matrix[0:1], vector_matrix[1:2])
    return similarity[0][0]

# Example usage
score = calculate_similarity("doc1.txt", "doc2.txt")
print(f"Similarity Score: {score:.2f}")
```

---

## 📌 Example Output

```
Similarity Score: 0.89
```

- `1.00` means exactly the same
- `0.00` means completely different

---


