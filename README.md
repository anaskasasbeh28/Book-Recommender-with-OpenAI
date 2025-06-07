# 📚 Book Recommendation System Using OpenAI Embeddings

This project demonstrates a content-based book recommendation system using OpenAI's `text-embedding-ada-002` model. It leverages book descriptions to compute semantic similarities between books, enabling users to get suggestions based on a selected title.

---

## 🚀 Features

- Load and clean a book dataset.
- Tokenize and compute OpenAI embedding vectors for book descriptions.
- Estimate token usage and cost for embedding generation.
- Save and load embedding vectors efficiently.
- Recommend similar books based on cosine similarity of description embeddings.

---

## 🧠 Technologies Used

- Python
- Pandas & NumPy
- OpenAI API (Embeddings)
- scikit-learn (cosine similarity)
- tiktoken (token counting)

---

## 📁 Dataset Columns

The dataset contains the following columns:

| Column Name        | Description                          |
|--------------------|--------------------------------------|
| `isbn13`           | Unique identifier for the book       |
| `title`            | Title of the book                    |
| `authors`          | Author(s) of the book                |
| `categories`       | Book categories or genres            |
| `description`      | Book description (used for embedding)|
| `published_year`   | Year the book was published          |
| `average_rating`   | Average user rating                  |

---

## 🧩 Project Workflow

### 1. **Data Loading & Cleaning**

- Load the dataset `books_dataset.csv`.
- Remove any rows with missing values.
- Sort the top 3000 books by `average_rating`.

### 2. **Token Counting and Cost Estimation**

- Use `tiktoken` to count tokens in the `description` column.
- Calculate total tokens and estimate OpenAI API cost.

### 3. **Embedding Generation**

- Use OpenAI's `text-embedding-ada-002` model to convert descriptions into embeddings.
- Save the enriched dataset (with embeddings) to `book_embeddings.csv`.

### 4. **Embedding Loading and Parsing**

- Load the saved CSV and parse the stringified embeddings into NumPy arrays.

### 5. **Book Recommendation**

- Input a book title.
- Compute cosine similarity between the selected book and all others.
- Return the top-k most similar books (excluding the selected one).

---

## 🧪 Example Usage

```python
get_recommendation_from_title(df_embeddings, 'Colossians and Philemon', 10)
```
Returns 10 books most similar in content to the given title.

---

## 💸 Cost Estimation Example

```text
Total tokens: 135400
Estimated cost in USD: 0.0135400000
```

*Note: Cost is based on \$0.0001 per 1,000 tokens (OpenAI embedding pricing).*

---

## 📦 File Structure

```
├── books_dataset.csv
├── book_recommender_openai_embeddings.ipynb
└── README.md
```
*Note: I could not upload the 'book_embeddings.csv' file due to its large size..*

---

## ✅ Prerequisites

* Python 3.8+
* OpenAI API key
* Installed packages:

  * openai
  * pandas
  * numpy
  * scikit-learn
  * tiktoken

Install all required libraries with:

```bash
pip install openai pandas numpy scikit-learn tiktoken
```

---

## 🔐 API Key Setup

Before running the notebook, make sure to set your OpenAI API key securely:

```python
import os
os.environ['OPENAI_API_KEY'] = 'your-key-here'
```

Or use `.env` file and `python-dotenv` for better security.

---

## 📚 Acknowledgments

* [OpenAI](https://platform.openai.com/docs/guides/embeddings) for the embeddings API.
* [tiktoken](https://github.com/openai/tiktoken) for accurate token estimation.

---

## 🧑‍💻 Author
```
Developed by Anas and ChatGPT – AI & Data Science Enthusiasts 👨‍💻
Feel free to reach out or contribute!

```
---
