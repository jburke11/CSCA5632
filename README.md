# 🧬 Unsupervised Protein Similarity Search with ESM C

## Overview

This project implements a simple cosine similarity lookup tool as well as multiple unsupervised KMeans models to find related proteins quickly and efficiently without relying on traditional sequence alignments.

---

## Features
- Embed protein sequences using ESM C
- Search for similar proteins via cosine similarity
- Support for unsupervised clustering and dimensionality reduction
- Model evaluation using simplified GO terms and Pfam IDs
- Easily extendable to supervised learning tasks

---

## How It Works

**1. Data Collection**  
Protein sequences are collected from **UniProt** in FASTA format.

**2. Embedding Extraction**  
Each sequence is passed through the **ESM C model**, and embeddings are mean-pooled across residues to generate a single vector per protein.

**3. GO Slimming**  
The Gene Ontology terms for each protein are generalized using the general GO Slim dataset and the most frequent slimmed term is chosen as the representative term.

**4. Similarity Computation**  
A **cosine similarity matrix** is built across all embeddings, allowing quick retrieval of top-k similar proteins for any given query.

**5. Model Building**  
Clustering methods like **K-means** and dimensionality reduction methods like **Truncated SVD** are applied to the embeddings to group and visualize related proteins.

**6. Evaluation**  
GO term annotations are used to check how functionally similar the retrieved proteins are using **Jaccard similarity**.  Additionally, **cluster purity** is used to determine the quality of the KMeans clustering.

---

## Applications
- Functional prediction for unknown proteins
- Exploratory analysis of protein families
- Preprocessing for supervised learning tasks
- Large-scale similarity search without traditional alignment

---

## Future Directions
- Expand to larger protein datasets
- Add fast approximate search techniques
- Build a public-facing web app
- Integrate richer annotations beyond GO terms

---

