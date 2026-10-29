# CineDex
AI-powered movie recommendation system using Sentence Transformers and FAISS

# CineDex — AI Movie Recommendation System (English Version)

CineDex is an AI-powered movie recommendation system developed using Natural Language Processing (NLP) and machine learning techniques.

The system recommends movies based on semantic similarity using Sentence Transformers and FAISS (Facebook AI Similarity Search).

This project aims to explore how AI can understand relationships between movies and provide relevant recommendations beyond simple keyword matching.

**Project Notebook:**

[CineDex Phase A](https://github.com/HeinZyrOo/CineDex/blob/main/CineDex_Phase_A.ipynb)

---

## Features

- AI-based movie recommendations
- Semantic similarity search using Sentence Transformers
- Movie embedding generation
- Efficient vector search using FAISS
- Recommendation ranking based on similarity
- Movie dataset preprocessing
- Development and experimentation using Google Colab

---

## Tech Stack

### Programming Language

- Python

### Data Processing

- Pandas
- NumPy

### AI / Machine Learning

- Sentence Transformers
- all-MiniLM-L6-v2
- FAISS
- Scikit-learn (planned for Phase B)

### Development Environment

- Google Colab
- Jupyter Notebook
- Git / GitHub

---

## System Architecture

```text
Movie Dataset
      |
      v
Data Preprocessing
      |
      v
Movie Text Data
      |
      v
Sentence Transformers
(all-MiniLM-L6-v2)
      |
      v
Movie Embeddings
      |
      v
FAISS Vector Index
      |
      v
Similarity Search
      |
      v
Top Similar Movies
      |
      v
Movie Recommendations
```

---

## Project Structure

```text
CineDex/
│
├── CineDex_Phase_A.ipynb
│
└── README.md
```

The project is currently developed in Google Colab using Jupyter Notebook.

---

## Main Features

### Movie Data Processing

The system prepares movie information from the dataset for recommendation processing.

The preprocessing stage includes:

- Loading movie data
- Handling necessary text information
- Preparing movie features
- Creating text representations for AI processing

### Sentence Transformer Embeddings

The system uses the pre-trained Sentence Transformer model `all-MiniLM-L6-v2`.

This model converts movie text information into numerical vectors called embeddings.

Movies with similar semantic meanings are represented by vectors that are relatively close to each other.

This enables the system to identify relationships between movies beyond exact keyword matching.

### FAISS Similarity Search

FAISS is used to perform efficient similarity searches on movie embeddings.

The system:

- Generates embeddings for movies
- Stores vectors in a FAISS index
- Searches for nearest-neighbor vectors
- Retrieves movies with similar representations

FAISS provides an efficient method for searching large collections of high-dimensional vectors.

### Movie Recommendation

The recommendation process follows these steps:

1. A user selects a movie.
2. The system identifies the movie's embedding.
3. FAISS searches for similar vectors.
4. Similar movies are ranked.
5. The system returns recommended movies.

This approach is based on content similarity rather than user rating history.

---

## Development Phases

### Phase A — Sentence Transformers + FAISS

**Status: Initial implementation**

The first phase focuses on semantic movie recommendations.

Main technologies:

- Sentence Transformers
- Dense vector embeddings
- FAISS similarity search

### Phase B — TF-IDF + Cosine Similarity

**Status: Planned**

The second phase will implement a traditional content-based recommendation method.

Main technologies:

- TF-IDF Vectorization
- Cosine Similarity
- Movie genres and tags

The goal is to compare traditional text-based similarity with transformer-based semantic similarity.

### Model Comparison

| Feature | Phase A | Phase B |
|---|---|---|
| Method | Semantic Similarity | Content-Based Similarity |
| Model | Sentence Transformers | TF-IDF |
| Search | FAISS | Cosine Similarity |
| Representation | Dense Vectors | Sparse Vectors |
| Status | Initial implementation | Planned |


---

## Future Improvements

- Implement Phase B using TF-IDF and cosine similarity
- Compare recommendation methods
- Evaluate recommendation accuracy and relevance
- Optimize similarity search performance
- Develop a user-friendly web interface
- Explore hybrid recommendation techniques

---

## What I Learned

Through this project, I learned:

- Natural Language Processing fundamentals
- Sentence Transformer models
- Text embedding generation
- Vector similarity search using FAISS
- Content-based recommendation systems
- Data preprocessing using Pandas
- Integrating pre-trained AI models into Python applications
- Developing machine learning projects using Google Colab

---

## Author

**Hein Zayar Oo**

Nippon Engineering College of Hachioji (IT College, Information Processing Department)

Tokyo University of Technology (School of Computer Science, Department of Computer Science)

GitHub: [HeinZyrOo](https://github.com/HeinZyrOo)

---

# CineDex — AI映画推薦システム（日本語版）

CineDexは、自然言語処理（NLP）と機械学習技術を活用したAI映画推薦システムです。

Sentence TransformersとFAISSを使用し、映画情報の意味的な類似度に基づいて、ユーザーが選択した映画に似ている作品を推薦します。

本プロジェクトでは、単純なキーワード一致だけでなく、AIによる意味的な特徴表現を利用した映画推薦の実現を目指しています。

**プロジェクトNotebook：**

[CineDex Phase A](https://github.com/HeinZyrOo/CineDex/blob/main/CineDex_Phase_A.ipynb)

---

## 主な機能

- AIによる映画推薦
- Sentence Transformersを利用した意味的類似度検索
- 映画情報のEmbedding生成
- FAISSによる高速ベクトル検索
- 類似度に基づく推薦ランキング
- 映画データの前処理
- Google Colabを利用した開発・実験

---

## 使用技術

### プログラミング言語

- Python

### データ処理

- Pandas
- NumPy

### AI・機械学習

- Sentence Transformers
- all-MiniLM-L6-v2
- FAISS
- Scikit-learn（Phase Bで使用予定）

### 開発環境

- Google Colab
- Jupyter Notebook
- Git / GitHub

---

## システム構成

```text
映画データセット
      |
      v
データ前処理
      |
      v
映画テキストデータ
      |
      v
Sentence Transformers
(all-MiniLM-L6-v2)
      |
      v
映画Embedding生成
      |
      v
FAISSベクトルインデックス
      |
      v
類似度検索
      |
      v
類似映画の抽出
      |
      v
映画推薦結果
```

---

## プロジェクト構成

```text
CineDex/
│
├── CineDex_Phase_A.ipynb
│
└── README.md
```

現在はGoogle Colab上でJupyter Notebookを利用して開発しています。

---

## 主な機能詳細

### 映画データの前処理

映画データセットを読み込み、推薦処理に必要な情報を整理します。

主な処理内容：

- 映画データの読み込み
- テキスト情報の整理
- 推薦に使用する特徴量の準備
- AIモデルに入力するテキストデータの作成

### Sentence TransformersによるEmbedding生成

事前学習済みモデル `all-MiniLM-L6-v2` を使用し、映画のテキスト情報を数値ベクトルに変換します。

この数値ベクトルをEmbeddingと呼びます。

意味的に似ている映画は、ベクトル空間上でも近い位置に表現される傾向があります。

これにより、単純な単語の一致だけでは発見しにくい映画同士の関連性を捉えることができます。

### FAISSによる類似度検索

FAISSを利用して、映画Embeddingの高速な類似度検索を行います。

処理の流れ：

1. 映画情報からEmbeddingを生成
2. EmbeddingをFAISSに登録
3. 選択した映画のベクトルを検索
4. 類似するベクトルを持つ映画を抽出
5. 類似度に基づいて推薦結果を表示

FAISSを利用することで、高次元ベクトルに対する効率的な近傍検索を実現します。

### 映画推薦機能

ユーザーが映画を選択すると、システムはその映画のEmbeddingを取得します。

次に、FAISSを利用して類似した映画を検索し、関連性の高い映画を推薦します。

この方式では、ユーザーの評価履歴ではなく、映画の内容に基づいて推薦を行います。

---

## 開発フェーズ

### Phase A — Sentence Transformers + FAISS

**開発状況：初期実装**

Sentence TransformersとFAISSを利用した意味的類似度に基づく映画推薦システムです。

主な技術：

- Sentence Transformers
- Embedding
- FAISS

### Phase B — TF-IDF + Cosine Similarity

**開発状況：実装予定**

TF-IDFとコサイン類似度を利用した従来型のコンテンツベース推薦システムを実装する予定です。

主な技術：

- TF-IDF
- Cosine Similarity
- 映画ジャンル・タグ情報

### 手法の比較

| 項目 | Phase A | Phase B |
|---|---|---|
| 推薦方法 | 意味的類似度 | テキスト特徴量の類似度 |
| 使用モデル | Sentence Transformers | TF-IDF |
| 検索技術 | FAISS | Cosine Similarity |
| ベクトル表現 | Dense Vector | Sparse Vector |
| 開発状況 | 初期実装 | 実装予定 |


---

## 今後の改善予定

- TF-IDFとコサイン類似度を利用したPhase Bの実装
- 推薦手法の比較実験
- 推薦精度と関連性の評価
- 類似度検索の高速化
- Webアプリケーションの開発
- ハイブリッド推薦手法の検討

---

## このプロジェクトを通して学んだこと

本プロジェクトを通して、以下の技術について学びました。

- 自然言語処理の基礎
- Sentence Transformersの仕組み
- Embeddingによるテキストのベクトル化
- FAISSを利用したベクトル類似度検索
- コンテンツベース推薦システム
- Pandasによるデータ前処理
- 事前学習済みAIモデルの活用
- Google Colabを利用した機械学習システムの開発

---

## Author

**Hein Zayar Oo**

日本工学院八王子専門学校（ITカレッジ 情報処理科）

東京工科大学（コンピューターサイエンス学部 コンピューターサイエンス学科）

GitHub: [HeinZyrOo](https://github.com/HeinZyrOo)
