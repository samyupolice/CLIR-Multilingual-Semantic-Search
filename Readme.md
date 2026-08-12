# Cross-Language Information Retrieval for Global E-Commerce

## Overview

This project develops a multilingual semantic search system for Cross-Language Information Retrieval (CLIR) in an e-commerce environment.

The system allows users to search for products using queries written in different languages while retrieving relevant products from an English product catalogue.

Instead of translating user queries into English before searching, the project uses multilingual sentence embeddings to map both the product catalogue and multilingual queries into a shared semantic embedding space.

Semantic relevance is then measured using cosine similarity, and products are ranked according to their similarity to the user's query.

---

## Problem Statement

Traditional keyword-based search systems depend heavily on lexical matching.

When users search in a language different from the language of the product catalogue, direct keyword matching can fail even when the query and product have the same meaning.

For example, an English product catalogue may contain:

"Leather Shoes"

while a user may search in another language.

This language mismatch can lead to poor retrieval results.

The project addresses this problem using Cross-Language Information Retrieval and multilingual semantic embeddings.

---

## Project Objective

The primary objective is to design and implement a multilingual semantic retrieval system that can retrieve relevant English product titles from user queries written in different languages.

The project demonstrates how transformer-based multilingual embeddings can overcome language barriers without requiring an explicit machine-translation layer.

---

## Specific Objectives

- Develop a Cross-Language Information Retrieval pipeline.
- Use multilingual sentence embeddings for semantic representation.
- Encode English product titles into dense vectors.
- Encode multilingual user queries into the same embedding space.
- Calculate cosine similarity between queries and products.
- Rank products according to semantic similarity.
- Evaluate multilingual retrieval behaviour.
- Visualize semantic relationships using similarity heatmaps.

---

## Dataset

The project uses an English product catalogue as the retrieval corpus.

The catalogue contains representative product titles from multiple e-commerce categories.

Multilingual test queries were prepared in:

- English
- German
- Spanish
- Italian

The product catalogue remains in English while the user queries can be written in different languages.

---

## Core Concept: Cross-Language Information Retrieval

Cross-Language Information Retrieval enables a user to submit a search query in one language and retrieve relevant documents written in another language.

In this project:

**User Query → Multilingual Embedding → Shared Semantic Space → Similarity Ranking → Product Results**

This approach focuses on semantic meaning rather than exact word matching.

---

## Model

The project uses:

`paraphrase-multilingual-MiniLM-L12-v2`

This is a multilingual Sentence Transformer model designed to generate sentence-level embeddings.

The same model is used to encode:

- English product titles
- English queries
- German queries
- Spanish queries
- Italian queries

Because both products and queries are represented in the same semantic embedding space, they can be compared directly.

---

## Why This Model?

The selected model provides:

- Multilingual semantic representations
- Support for multiple languages
- Efficient sentence embedding generation
- Semantic similarity capabilities
- A lightweight transformer architecture
- Integration with the Sentence Transformers ecosystem

The model allows the project to perform multilingual retrieval without an explicit translation pipeline.

---

## Methodology

The retrieval pipeline consists of the following stages:

1. Dataset loading
2. Text preprocessing
3. Model initialization
4. Product embedding generation
5. Multilingual query encoding
6. Cosine similarity computation
7. Product ranking
8. Retrieval result analysis
9. Similarity visualization

---

## Retrieval Pipeline

### Step 1 — Dataset Loading

The English product catalogue is loaded using Pandas.

Product titles are extracted to form the retrieval corpus.

### Step 2 — Text Preprocessing

Basic preprocessing is performed to normalize the product titles and prepare the text for embedding generation.

### Step 3 — Model Initialization

The `paraphrase-multilingual-MiniLM-L12-v2` Sentence Transformer model is loaded.

### Step 4 — Product Embedding Generation

Each English product title is converted into a dense numerical vector.

These embeddings can be generated once and reused for multiple queries.

### Step 5 — Multilingual Query Encoding

User queries written in English, German, Spanish, or Italian are encoded using the same multilingual model.

### Step 6 — Similarity Computation

Cosine similarity is calculated between the query embedding and product embeddings.

Higher similarity values indicate stronger semantic relationships.

### Step 7 — Ranking

Products are ranked according to their cosine similarity scores.

The highest-ranked products are returned as the retrieval results.

---

## Semantic Representation

The key idea behind the system is that semantically similar texts should be positioned close together in the embedding space.

Therefore, a multilingual query can be compared directly with an English product title even when the words are different and the languages do not match.

This enables language-independent semantic retrieval.

---

## Evaluation

The system is evaluated using multilingual product-search queries.

Queries are written in:

- English
- German
- Spanish
- Italian

The evaluation examines whether semantically relevant English product titles appear among the highest-ranked results.

The project also uses cosine-similarity matrices and heatmaps to visualize semantic relationships between multilingual queries and English product titles.

---

## Results

The experimental results demonstrate that the multilingual Sentence Transformer successfully retrieves semantically relevant English product titles for queries written in different languages.

The similarity heatmaps provide a visual representation of semantic alignment between queries and catalogue products.

Higher cosine similarity values indicate stronger semantic relationships.

The project demonstrates that multilingual semantic embeddings can support cross-language product retrieval without requiring explicit machine translation.

---

## Key Findings

- Multilingual sentence embeddings can bridge language differences between users and product catalogues.
- English product titles can be retrieved using queries written in other languages.
- Cosine similarity provides an effective mechanism for semantic ranking.
- Shared embedding spaces allow direct query-product comparison across languages.
- Heatmaps provide an intuitive way to inspect multilingual semantic alignment.
- Transformer-based semantic retrieval is a practical alternative to purely keyword-based multilingual search.

---

## Limitations

- The evaluation uses a relatively small English product catalogue.
- The number of multilingual test queries is limited.
- The project focuses primarily on qualitative retrieval analysis.
- Standard retrieval metrics such as Precision@K, Recall@K, MAP, and MRR were not comprehensively evaluated.
- Only product titles are used for generating embeddings.
- Product descriptions, specifications, reviews, popularity indicators, and user interaction history are not incorporated.
- Only one multilingual Sentence Transformer model is evaluated.

---

## Technologies Used

- Python
- Pandas
- NumPy
- Sentence Transformers
- Hugging Face Transformers
- Scikit-learn
- Matplotlib
- Cosine Similarity
- Jupyter Notebook
- Google Colab
- Natural Language Processing
- Information Retrieval
- Transformer Models

---

## Project Workflow

English Product Catalogue  
↓  
Text Preprocessing  
↓  
Multilingual Sentence Transformer  
↓  
Product Embeddings  
↓  
Multilingual User Query  
↓  
Query Embedding  
↓  
Cosine Similarity  
↓  
Similarity Ranking  
↓  
Top-K Product Results  
↓  
Heatmap Visualization

---

## Project Structure

CLIR-Multilingual-Semantic-Search/

├── Dataset/  
├── Images/  
├── Models/  
├── Notebooks/  
│   └── CLIR_Project_Sam.ipynb  
├── Reports/  
│   └── Multi-lingual_information_Term_Paper.pdf  
├── .gitignore  
├── LICENSE  
├── README.md  
└── requirements.txt

---

## How to Run

### Step 1: Clone the Repository

git clone https://github.com/samyupolice/CLIR-Multilingual-Semantic-Search.git

### Step 2: Navigate to the Project

cd CLIR-Multilingual-Semantic-Search

### Step 3: Install Dependencies

pip install -r requirements.txt

### Step 4: Open the Notebook

Open:

Notebooks/CLIR_Project_Sam.ipynb

The notebook can be executed in Jupyter Notebook or Google Colab.

---

## Future Improvements

Future work could include:

- Using larger multilingual e-commerce datasets.
- Adding product descriptions and specifications.
- Incorporating customer reviews and product metadata.
- Comparing multilingual BERT and XLM-RoBERTa.
- Comparing multiple Sentence Transformer models.
- Evaluating Precision@K.
- Evaluating Recall@K.
- Evaluating Mean Average Precision (MAP).
- Evaluating Mean Reciprocal Rank (MRR).
- Testing retrieval performance across more languages.
- Developing a real-time semantic search interface.
- Using vector databases for large-scale product retrieval.

---

## Business Applications

The proposed approach can support:

- International e-commerce search
- Multilingual product discovery
- Global online marketplaces
- Multilingual digital libraries
- Cross-language information systems
- International customer-facing search platforms

For e-commerce, the system can help users discover relevant products even when their search language differs from the catalogue language.

---

## Academic Report

A detailed academic report is available in the `Reports/` folder.

The report covers:

- Cross-Language Information Retrieval
- Multilingual semantic search
- Transformer-based embeddings
- Dataset preparation
- Retrieval methodology
- Cosine similarity
- Experimental analysis
- Limitations
- Future work
- Conclusion

---

## Conclusion

This project demonstrates a Cross-Language Information Retrieval system for multilingual e-commerce search.

By representing English product titles and multilingual user queries in a shared semantic embedding space, the system can retrieve semantically relevant products without relying on explicit machine translation.

The use of `paraphrase-multilingual-MiniLM-L12-v2` together with cosine similarity provides a practical foundation for multilingual semantic search.

The project demonstrates the transition from traditional lexical keyword matching toward meaning-driven retrieval using modern transformer-based NLP techniques.

---

## Disclaimer

This project was developed for academic and research purposes.

The evaluation was conducted on a limited product catalogue and a limited set of multilingual queries. The results should therefore not be interpreted as evidence of production-scale retrieval performance.

---

## Author

**Samyupolice**

Data Science | NLP | Information Retrieval | Machine Learning
