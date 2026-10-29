# CineDex — AI-Powered Movie Recommendation System

## English Version

CineDex is an AI-powered movie recommendation system that uses Natural Language Processing (NLP), Sentence Transformers, TF-IDF, and FAISS to recommend movies based on content and semantic similarity.

The project implements and compares two recommendation approaches: traditional TF-IDF with cosine similarity and transformer-based semantic embeddings with FAISS.

It also provides a Gradio web interface that allows users to search by movie title or natural-language description.

## Features

- Movie recommendations using TF-IDF and Cosine Similarity
- Semantic recommendations using Sentence Transformers and FAISS
- Natural-language movie search
- Comparison of two recommendation algorithms
- Interactive Gradio web interface
- Model and vector index saving/loading
- Processing of 4,800 movies from the TMDB dataset

## Tech Stack

| Category | Technologies |
|---|---|
| Language | Python |
| Data Processing | Pandas, NumPy |
| Traditional NLP | TF-IDF, Scikit-learn, Cosine Similarity |
| Semantic AI | Sentence Transformers, all-MiniLM-L6-v2 |
| Vector Search | FAISS |
| Web Interface | Gradio |
| Model Storage | Joblib, NumPy, FAISS |
| Development | Google Colab, Jupyter Notebook, GitHub |

## System Architecture

```text
TMDB 5000 Movie Dataset
          |
          v
    Data Preprocessing
          |
          v
 Overview + Genres + Keywords
          |
          v
     Movie Tags
          |
     +----+----------------+
     |                     |
     v                     v
   TF-IDF           Sentence Transformers
     |                all-MiniLM-L6-v2
     v                     |
 Sparse Vectors            v
     |               Dense Embeddings
     v                 (384 dimensions)
 Cosine Similarity          |
     |                     v
     |                FAISS Index
     |                     |
     v                     v
 TF-IDF Results      Semantic Results
     |                     |
     +----------+----------+
                |
                v
         Gradio Interface
                |
                v
       Movie Recommendations
```

## Dataset

The project uses the **TMDB 5000 Movie Dataset**.

- Original dataset: 4,803 movies
- Processed dataset: 4,800 movies
- Features: movie titles, overviews, genres, and keywords

The preprocessing pipeline removes missing or duplicate records, extracts genres and keywords from JSON-formatted fields, and combines the information into movie tags.

## Main Features

### 1. TF-IDF Movie Recommendation

The system uses `TfidfVectorizer` to convert movie tags into numerical vectors.

Configuration:

- Maximum features: 10,000
- English stop-word removal
- Unigrams and bigrams

Cosine similarity is calculated between movie vectors to identify similar movies.

The `recommend_tfidf()` function returns the top five recommendations and their similarity scores.

### 2. Semantic Movie Recommendation

The system uses the pre-trained `all-MiniLM-L6-v2` Sentence Transformer model to convert movie tags into 384-dimensional embeddings.

These embeddings represent semantic information, allowing the system to identify movies with related meanings even when their descriptions use different words.

FAISS `IndexFlatIP` performs nearest-neighbor searches over normalized embeddings.

The `recommend_semantic()` function returns similar movies and their similarity scores.

### 3. Natural-Language Movie Search

Users can search for movies by entering a description instead of a specific title.

Example:

```text
A science fiction movie about space exploration
```

The system converts the description into an embedding and searches the FAISS index for semantically similar movies.

The results include movie titles, similarity scores, and overviews.

### 4. Recommendation Method Comparison

The project compares TF-IDF and Sentence Transformers using the same movie dataset.

Example: **Interstellar**

| TF-IDF Recommendations | Semantic Recommendations |
|---|---|
| Silent Running | Mission to Mars |
| Mission to Mars | Prometheus |
| 2001: A Space Odyssey | Gattaca |
| Space Cowboys | The Inhabited Island |
| Armageddon | Star Trek Beyond |

Both methods produce relevant candidates, but their rankings differ because they represent text differently.

The current comparison is qualitative. A quantitative evaluation is planned for future development.

### 5. Gradio Web Interface

The project includes an interactive web interface built with Gradio.

Users can choose between three recommendation modes:

1. **TF-IDF** — Search by movie title using cosine similarity.
2. **Semantic (Movie Title)** — Search by movie title using Sentence Transformers and FAISS.
3. **Semantic (Description)** — Search using natural-language descriptions.

Results are displayed in a table.

### 6. Model Saving and Loading

The system supports saving and reloading:

- Processed movie metadata
- Sentence Transformer embeddings
- FAISS vector index
- TF-IDF vectorizer
- TF-IDF feature matrix

This allows previously generated data and indexes to be reused without repeating the entire preprocessing process.

## Project Structure

```text
CineDex/
├── CineDex_Phase_A.ipynb
├── README.md
│
├── data/
│   └── processed/
│       └── movies_processed.csv
│
└── models/
    ├── movie_embeddings.npy
    ├── movie_faiss.index
    ├── tfidf_vectorizer.joblib
    └── tfidf_matrix.joblib
```

The `data/` and `models/` directories are generated when the notebook saves its artifacts. They may not be included in the GitHub repository.

```



## Future Improvements

- Develop Phase B: Personalized Movie Recommendation System using Collaborative Filtering and Matrix Factorization based on users'      rating histories and preferences
- Develop Phase C: Hybrid Recommendation System combining content-based and collaborative filtering approaches
- More advanced Gradio interface
- Permanent web application deployment

## What I Learned

Through this project, I gained practical experience in:

- Natural Language Processing and text preprocessing
- TF-IDF vectorization and cosine similarity
- Transformer-based sentence embeddings
- Vector similarity search using FAISS
- Building content-based recommendation systems
- Comparing machine learning approaches
- Integrating AI models into interactive applications
- Saving and loading trained model artifacts

---

# CineDex — AI映画推薦システム

## 日本語版

CineDexは、自然言語処理（NLP）と機械学習技術を活用したAI映画推薦システムです。

TF-IDFとコサイン類似度を利用した従来型の推薦手法と、Sentence TransformersおよびFAISSを利用した意味的類似度検索の2つの手法を実装し、推薦結果を比較しています。

また、Gradioを利用したWebインターフェースを開発し、映画タイトルや自然言語による説明文から映画を検索できるようにしました。

## 主な機能

- TF-IDFとコサイン類似度による映画推薦
- Sentence TransformersとFAISSによる意味的類似度検索
- 自然言語による映画検索
- 2種類の推薦アルゴリズムの比較
- GradioによるWebインターフェース
- モデルとベクトルインデックスの保存・読み込み
- TMDBデータセットの4,800作品を対象とした推薦

## 使用技術

| 分類 | 使用技術 |
|---|---|
| プログラミング言語 | Python |
| データ処理 | Pandas, NumPy |
| 自然言語処理 | TF-IDF, Scikit-learn |
| AIモデル | Sentence Transformers, all-MiniLM-L6-v2 |
| 類似度検索 | Cosine Similarity, FAISS |
| Webインターフェース | Gradio |
| データ保存 | Joblib, NumPy, FAISS |
| 開発環境 | Google Colab, Jupyter Notebook |

## システム構成

```text
TMDB映画データセット
        |
        v
    データ前処理
        |
        v
概要 + ジャンル + キーワード
        |
        v
     映画タグ
        |
   +----+------------------+
   |                       |
   v                       v
 TF-IDF              Sentence Transformers
   |                       |
   v                       v
特徴ベクトル          384次元Embedding
   |                       |
   v                       v
コサイン類似度            FAISS
   |                       |
   v                       v
推薦結果A               推薦結果B
   |                       |
   +-----------+-----------+
               |
               v
        Gradio画面
               |
               v
          映画推薦
```

## データセット

TMDB 5000 Movie Datasetを使用しています。

- 元データ：4,803作品
- 前処理後：4,800作品
- 使用情報：映画タイトル、概要、ジャンル、キーワード

欠損値や重複データを処理し、映画の概要・ジャンル・キーワードを組み合わせて推薦用のテキストデータを作成しています。

## 主な機能詳細

### 1. TF-IDFによる映画推薦

TF-IDFを使用し、映画のテキスト情報を特徴ベクトルに変換します。

最大10,000特徴量を使用し、英語のストップワードを除去するとともに、単語単位と2単語の組み合わせを考慮しています。

その後、コサイン類似度を計算し、類似度の高い映画を上位5件推薦します。

### 2. Sentence Transformersによる意味的推薦

事前学習済みモデル `all-MiniLM-L6-v2` を使用し、映画情報を384次元のEmbeddingに変換します。

EmbeddingをFAISSに登録することで、意味的に近い映画を効率的に検索します。

単語の一致だけでなく、文章の意味的な関係性を考慮した推薦を実現しています。

### 3. 自然言語による映画検索

ユーザーが映画の特徴を文章で入力すると、その内容に近い映画を推薦します。

入力例：

```text
A science fiction movie about space exploration
```

入力文をSentence TransformersでEmbeddingに変換し、FAISSによって類似した映画を検索します。

### 4. 推薦手法の比較

TF-IDFとSentence Transformersの推薦結果を比較する機能を実装しました。

「Interstellar」「The Dark Knight」「Avatar」などの映画を対象に、両手法が推薦する映画の違いを確認しています。

今後は、定量的な評価指標を導入して、推薦精度や検索性能を比較する予定です。

### 5. GradioによるWebインターフェース

Gradioを使用し、以下の3つの検索モードを選択できるWeb画面を実装しました。

- TF-IDF：映画タイトルによる推薦
- Semantic (Movie Title)：意味的類似度に基づく映画タイトル検索
- Semantic (Description)：自然言語による映画検索

推薦結果はテーブル形式で表示されます。

### 6. モデルの保存と読み込み

学習済みの特徴表現や検索インデックスを保存し、再利用できるようにしています。

保存対象：

- 前処理済み映画データ
- Sentence TransformerのEmbedding
- FAISSインデックス
- TF-IDFベクトライザー
- TF-IDF行列


## 今後の改善予定

- Phase B：ユーザーの評価履歴や好みに基づき、協調フィルタリングと行列分解を利用したパーソナライズ映画推薦システムの開発
- Phase C：コンテンツベース推薦と協調フィルタリングを組み合わせたハイブリッド推薦システムの開発
- Webインターフェースの改良
- Webアプリケーションの常時公開

## このプロジェクトを通して学んだこと

- 自然言語処理とテキスト前処理
- TF-IDFによる特徴量抽出
- コサイン類似度の計算
- Sentence TransformersによるEmbedding生成
- FAISSを利用したベクトル検索
- コンテンツベース推薦システムの開発
- 異なる推薦手法の比較
- Gradioを利用したAIアプリケーションの開発
- モデルと検索インデックスの保存・再利用

---

## Author

**Hein Zayar Oo**

Tokyo University of Technology — School of Computer Science

GitHub: [HeinZyrOo](https://github.com/HeinZyrOo)
