# Cryptography \& Security Search Engine

A Jupyter Notebook information-retrieval project that searches a corpus of 400 research papers from the arXiv `cs.CR` (Cryptography and Security) category.

The Phase 1 notebook implements sparse keyword retrieval, dense semantic retrieval, Reciprocal Rank Fusion (RRF), query processing, and a Gradio interface.

## Features

* **BM25 retrieval** for keyword-based search.
* **Dense semantic retrieval** using `sentence-transformers/all-MiniLM-L6-v2`.
* **Hybrid ranking** using Reciprocal Rank Fusion (RRF).
* **Query processing:** spelling correction, abbreviation expansion, and case normalization.
* **Phrase matching** for quoted phrases.
* **Gradio GUI:** search box, retrieval-mode selector (`fused`, `bm25`, `dense`), up to 10 results, arXiv links, ranking scores, snippets, and highlighted query terms.

## Dataset

The project uses a corpus of 400 unique arXiv research papers from the Cryptography and Security (`cs.CR`) category.



The dataset contains four sub-topics, with 100 papers each:

\- Cryptographic Algorithms

\- Network and System Security

\- Post-Quantum Cryptography

\- Privacy-Preserving Cryptography



The public repository includes:

\- `dataset/papers.csv` — metadata for all 400 papers.

\- `dataset/collection\_config.json` — collection configuration.



\*\*Full-text files:\*\* The 400 extracted `.txt` files are kept locally and excluded from the public GitHub repository.



To run the search engine, the extracted files must be placed in `dataset/texts/`, matching the paths in `papers.csv`.Repository structure

```text
cryptography-security-search-engine/
├── IR\_PROJECT.ipynb
├── README.md
├── requirements.txt
├── .gitignore
├── dataset/
│   ├── papers.csv
│   ├── collection\_config.json
│   └── texts/
├── reports/
│   └── README.md
└── ai-logs/
    └── phase1/
        └── README.md
```

## Requirements

* Python 3.10 or newer
* Internet access on first run to install dependencies and download the sentence-transformer model

Install dependencies:

```bash
python -m pip install --upgrade pip
pip install -r requirements.txt
```

## Run the notebook

1. Clone or download this repository.
2. Open a terminal in the repository root (the folder containing `IR\_PROJECT.ipynb` and `dataset/`).
3. Install the requirements.
4. Start Jupyter:

```bash
jupyter notebook
```

5. Open `IR\_PROJECT.ipynb` and run the cells from top to bottom.

The first run may take longer because the embedding model is downloaded and embeddings are generated for the corpus. The final cell launches the Gradio interface locally (`share=False`).

## Search modes

|Mode|Description|
|-|-|
|`bm25`|Sparse keyword retrieval|
|`dense`|Embedding-based semantic retrieval|
|`fused`|Combines BM25 and dense rankings using RRF|

## Phase 1 report

Add the final, verified corpus-statistics PDF required by the course to `reports/`. It has not been included in this package.

## AI-use disclosure

AI assistance was used during Phase 1. The course specification requires the full relevant transcript(s), the tool name and version, and a short index under `ai-logs/phase1/`. Add the exported transcript(s) to that folder before submission. This README note is not a replacement for the required transcript.

## Scope

This repository packages the Phase 1 corpus and hybrid retrieval notebook. Phase 2 learned ranking, personalization, Docker packaging, evaluation, and demo-video deliverables are separate future work.

