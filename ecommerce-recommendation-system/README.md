# 🛍️ E-Commerce Product Recommendation System

A scalable big data pipeline that analyzes clickstream data to understand user behavior and power a personalized product recommendation engine — built with **Apache Spark**, **Elasticsearch**, **Kibana**, and **collaborative filtering (SVD)**.

> 📄 Based on our published research: *"A Big Data Framework for Clickstream Analysis: User Behavior Analysis and Product Recommendation System"*

---

## 📌 Overview

Large-scale digital platforms generate terabytes of clickstream data every hour — every click, scroll, and page view is a signal of user intent. This project builds an end-to-end pipeline to:

- Process and analyze massive volumes of clickstream, customer, product, and transaction data
- Visualize user behavior patterns through interactive dashboards
- Recommend personalized products to users using collaborative filtering

---

## 🎯 Objectives

- **Understand user behavior** — analyze how users navigate, what they view, and what actions they take
- **Build a recommendation engine** — suggest relevant products using SVD-based collaborative filtering
- **Uncover behavioral patterns** — identify product interest clusters, browsing habits, and drop-off points
- **Enable real-time insights** — create interactive Kibana dashboards for stakeholder decision-making

---

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                       Data Sources                           │
│   ClickStream.csv | Customer.csv | Product.csv | Transaction │
└────────────────────────────┬──────────────────────────────────┘
                              │
                 ┌────────────▼─────────────┐
                 │   Apache Spark (PySpark)  │
                 │  Read → Clean → Parse →   │
                 │   Transform → Aggregate   │
                 └────────────┬─────────────┘
                              │
              ┌───────────────┴────────────────┐
              ▼                                 ▼
┌───────────────────────────┐    ┌──────────────────────────────┐
│  Elasticsearch + Kibana   │    │   Recommendation Pipeline     │
│  • JSON indexing          │    │  • User-item interaction      │
│  • Full-text search       │    │    matrix                     │
│  • Interactive dashboards │    │  • SVD collaborative filtering │
│  • Bar/Pie/Sunburst/      │    │  • Top-5 recommendations      │
│    Heatmap/Geo-Map        │    │    per user                   │
└───────────────────────────┘    └──────────────────────────────┘
```

---

## ⚙️ Tech Stack

| Layer | Technology |
|---|---|
| Data Processing | Apache Spark (PySpark DataFrame API) |
| Search & Indexing | Elasticsearch v8.11.1 |
| Visualization | Kibana Lens |
| Recommendation Model | Surprise library — SVD (Collaborative Filtering) |
| UI for Recommendations | ipywidgets (interactive HTML output) |
| Language | Python |

---

## 🔄 Methodology

### 1. Data Preprocessing
- Loaded `ClickStream`, `Customer`, `Product`, and `Transaction` datasets as Spark DataFrames
- Cleaned nulls and ensured schema consistency
- Joined datasets on `customer_id`, `product_id`, `session_id`, and `booking_id`
- Parsed nested `product_metadata` (JSON-like strings) to extract product IDs

### 2. Feature Engineering
- Built a unified dataset combining event metadata, product info, user demographics, and device/location data
- Exported enriched data as JSON Lines, optimized for Elasticsearch bulk ingestion

### 3. Big Data Visualization
- Indexed data into Elasticsearch (`clickstream` index) via batch uploads (500 records/batch)
- Built interactive Kibana dashboards: Bar/Pie charts, Sunburst (Category → Sub-category → Article), Heatmaps (session time vs. conversion), and Geo-Maps (delivery hotspots)

### 4. Recommendation System (SVD)
- Filtered `ADD_TO_CART` events and built a **user-item interaction matrix** using implicit ratings (interaction counts)
- Trained a **collaborative filtering model** using the Surprise library's SVD algorithm
- Generated **top-5 personalized product recommendations** per user based on predicted preference scores

---

## 📊 Results

| Metric | Value |
|---|---|
| Unique users | 50,704 |
| Unique products | 44,446 |
| Total interactions | 1,253,113 |
| Training interactions | 1,002,490 |
| Test interactions | 250,623 |
| Consolidated dataset size | ~3.4 GB |
| **RMSE** | **0.2702** (6.76% of rating range) |
| **MAE** | **0.1937** (4.84% of rating range) |

The low RMSE and MAE indicate the model predicts user preferences with strong accuracy, enabling reliable top-5 product recommendations per user.

### Sample Recommendations

| Product ID | Product Name | Predicted Score |
|---|---|---|
| 5681 | Skechers Men's Compelling Dexterity Fudge Brown Shoe | 6.67 |
| 7257 | Rockport Men's Alfrew Dark Tan Shoe | 6.64 |
| 28851 | Proline Charcoal Grey Polo T-shirt | 6.61 |
| 15177 | Arrow Sport Men Solid Navy Blue Sweaters | 6.37 |
| 17577 | Mark Taylor Men Solid Grey Trouser | 6.30 |

---

## 📁 Repository Structure

```
ecommerce-recommendation-system/
│
├── data/                     # Raw datasets (ClickStream, Customer, Product, Transaction)
├── notebooks/                # Jupyter notebooks for preprocessing, SVD training, evaluation
├── scripts/
│   └── upload_clickstream.py # Batch upload script for Elasticsearch ingestion
├── dashboards/                # Kibana dashboard exports/screenshots
├── docs/
│   ├── research_paper.pdf     # Published research paper
│   └── presentation.pdf       # Project presentation slides
└── README.md
```

---

## 🚀 Key Highlights

- Processed a **3.4 GB** consolidated dataset spanning **50K+ users** and **44K+ products**
- Built a **scalable Spark pipeline** to clean, join, and transform multi-source clickstream data
- Achieved **RMSE of 0.27** on a collaborative filtering recommendation model
- Delivered **real-time interactive dashboards** for user behavior and business insights via Kibana

---

## 🔮 Future Work

- Real-time stream processing using Apache Kafka
- Hybrid recommendation approach combining content-based and collaborative filtering
- Enhanced customer feedback loop integration
- Deep learning–based sequence models for session-based recommendations

---

## 👥 Authors

- **G. Pandi Kumar** — Department of Computer Science Engineering, Amrita School of Computing, Bengaluru
- **Sv. Pethaa** — Department of Computer Science Engineering, Amrita School of Computing, Bengaluru

*Course: 24DS635 — Big Data Framework for Data Science*

---

## 📄 Citation

If you reference this work, please cite:

> G. Pandi Kumar, Sv. Pethaa, M. Venugopalan, "A Big Data Framework for Clickstream Analysis: User Behavior Analysis and Product Recommendation System."

---

## 📜 License

This project is for academic and educational purposes. Dataset sourced from [Kaggle — E-Commerce User Behavior Dataset](https://www.kaggle.com/datasets/bytadit/transactional-ecommerce).
