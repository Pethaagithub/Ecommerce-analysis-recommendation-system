## 24DS635 Big Data Framework for Data Science

## Clickstream Insights: User Behavior Analysis & Recommendation System

G. Pandi Kumar - [BL.SC.P2DSC24020]

Sv. Pethaa - [BL.SC.P2DSC24029]

Department ofComputer Science Engineering

Amrita School ofComputing , Bengaluru


## Introduction

- Clickstream Data refers to the digital trail left by users as they interact with websites or applications, including clicks, page views, scrolls, and navigation paths. It is generated in real time and typically recorded with timestamps, session IDs, and user identifiers.

- Analyzing clickstream data provides valuable insights into user preferences, behavior patterns, and intent. This enables businesses to enhance user experience, deliver personalized recommendations, and optimize digital strategies. Large-scale platforms generate terabytes of clickstream data every hour, reflecting its massive scale.

- The analysis of clickstream data involves handling high data volume and velocity, processing unstructured or semi-structured formats, ensuring real-time responsiveness, tracking user sessions accurately, and maintaining data privacy and compliance

- Clickstream analysis plays a crucial role across multiple domains such as e-commerce (product recommendations), digital marketing (targeted advertising), banking (fraud detection), healthcare (user journey monitoring), and media/streaming platforms (content personalization).

2


## Objective

- To understand and model user behavior by analyzing large volumes of clickstream data generated through interactions on digital platforms. This includes identifying how users navigate, what products they view, and which actions they frequently perform.

- To build an intelligent recommendation system that suggests relevant products to users by applying collaborative filtering techniques, specifically using Singular Value Decomposition (SVD), based on observed behavioral patterns.

- To detect recurring patterns and behavioral trends across different user segments, helping to uncover insights such as product interest clusters, browsing habits, and drop-off points in the user journey.

- To create dynamic and interactive dashboards using Kibana that allow stakeholders to visualize user activity, monitor engagement metrics, and make informed business decisions in real time.

3


## Literature Survey

| S.No | Research Paper Name | Authors | Observation |
| --- | --- | --- | --- |
|   |   |   | Proposed a real-time architecture using Kafka, Spark Streaming, |
|   |   | Ramanna Hanamanthrao, |   |
|   |   |   | and Elasticsearch to analyze clickstream data. Focused on |
| 1 Real-Time Clickstream Data Analytics and Visualization |   | Thejaswini S |   |
|   |   |   | enhancing user behavior insights and real-time decision-making |
|   |   | in online platforms. |   |
|   |   |   | Presented a framework combining machine learning and |
|   |   | A. Vijaya Bharathi, |   |
|   | Click Stream Analysis in e-Commerce Websites-a |   | cognitive models for e-commerce behavior analysis. Highlighted |
| 2 |   | Jyothi M. Rao, |   |
| Framework |   |   | challenges in recommendation systems and emphasized session- |
|   |   | Amiya K. Tripathy |   |
|   |   |   | based pattern discovery. |
|   |   |   | Integrated HBase and SSH framework to improve query |
|   | Research and Analysis of an Enterprise E-Commerce | Linze Li, |   |
| 3 |   |   | performance in e-commerce systems. Demonstrated how big data |
| Marketing System |   | Jun Zhang |   |
|   |   |   | technologies enhance marketing and operational efficiency. |
|   | Enterprise E-Commerce Marketing System |   |   |
|   |   |   | Focused on building trust using credit mechanisms to reduce |
|   | Based on Big Data Methods of Maintaining |   |   |
| 4 |   | Guihe He | fraud in online transactions. Used mathematical modeling to |
|   | Social Relations in the Process of |   |   |
|   |   |   | compare benefits of credit-based e-commerce environments. |
|   | E-Commerce Environmental Commodity |   |   |
|   |   |   | explores how big data analytics empowers both vendors and |
|   |   | SARAH S. ALRUMIAH, |   |
|   | Implementing Big Data Analytics in E-Commerce: |   | customers in e-commerce by enhancing personalization and |
| 5 |   | MOHAMMEDH |   |
| Vendor and Customer View |   |   | decision-making. It highlights the role of analytics in optimizing |
|   |   | ADWAN |   |
|   |   |   | marketing, operations, and customer engagement strategies. |

4


## Literature Survey

| S.No | Research Paper Name | Author | Observation |
| --- | --- | --- | --- |
|   |   |   | Applied machine learning for customer segmentation, prediction, |
|   | An Intelligent Approach for Data Analysis and | EL FALAH Zineb, |   |
|   |   |   | and marketing in big data environments. Emphasized how |
| 6 | Decision Making in Big Data: A Case Study on | RAFALIA Najat, |   |
|   |   |   | intelligent analytics drives personalized recommendations and |
| E-commerce Industry |   | ABOUCHABAKA Jaafar |   |
|   |   | business decisions. |   |
|   |   |   | Proposes a meta-search model that uses AI techniques to unify |
|   | An intelligent approach to design of E-Commerce |   |   |
|   |   | Dheeraj Malhotra, | product search across multiple e-commerce platforms. It |
| 7 | metasearch and ranking system using next-generation |   |   |
|   |   | Omprakash Rishi | emphasizes improved user satisfaction through enhanced |
| big data analytics |   |   |   |
|   |   |   | relevance and intelligent filtering of results |
|   |   | Ayman Abdalmajeed |   |
|   |   | Alsmadi,Ahmed | Study reviews current innovations in e-commerce driven by big |
|   | Big data analytics and innovation in e-commerce: |   |   |
|   |   | Shuhaiber,Manaf | data, focusing on customer experience, predictive analytics, and |
| 8 current insights |   |   |   |
|   |   | Al-Okaily,Anwar | personalization. It presents a framework for leveraging data to |
| and future directions |   |   |   |
|   |   | Al-Gasaymeh,Najed | sustain competitive advantage |
|   |   | Alrawashdeh |   |
|   |   |   | Analyzes how digital marketing strategies have evolved with the |
|   | Consumer Marketing Strategy and E-Commerce in the | Albérico Rosário , | rise of e-commerce, especially in targeting and engagement. It |
| 9 |   |   |   |
|   | LastDecade: A Literature Review | Ricardo Raimundo | underscores the importance of data-driven approaches in shaping |
|   |   |   | modern consumer behavior |
|   |   | Sivananda Reddy Julakanti, |   |
|   |   |   | Demonstrates the use of Apache Spark DataFrames for efficient |
|   |   | Implementing_Spark_Data_Frames_for_Advanced_Dat Naga Satya Kiranmayee, |   |
| 10 |   |   | big data analysis and real-time processing. It showcases Spark's |
| a_Analysis |   | Sattiraju, |   |
|   |   |   | capability to handle complex datasets with scalability and speed. |
|   |   | Rajeswari Julakanti |   |

5


## Architecture of User behaviour Analysis and Recommendation system

- Spark SQL through PySpark’s DataFrame API

ClickStream.csv

- Reads, Cleans, Parsing, Transforms raw data

Customer.csv

- Data Aggregation

Product.csv

Transaction.csv

Aggregated Data

## Big Data Analysis and Visualization Pipeline

- Big Data Loading in .json format

- Indexing data

- Dashboard creation

- Full-text search

- Visualization

- Powering Kibana

- Querying

## Product recommendation System

## Data Preparation

- Parse

- Explode

- Merge

- Outer join

## Models

- User-item interactions matrix

- Collaborative filtering based on SVD

## Recommendation System [Top Five]

6


## Methodology

## Big Data Pipeline for Clickstream Analysis

## Data Sources:

- Clickstream, Customer, Transaction, and Product datasets

- Represent user actions, demographics, payments, and product details

## Preprocessing with Apache Spark:

- Loaded data as Spark DataFrames

- Cleaned nulls, ensured schema consistency

- Performed joins on customer_id, product_id, session_id, and booking_id

## Enrichment and Feature Engineering:

- Created unified dataset with:

- Event metadata (event_name, time)

- Product info (category, article type)

- User attributes (gender, age)

- Device and location data

## Output Format:

- Saved enriched data as JSON Lines (.json)

- Optimized for Elasticsearch bulk ingestion


## Methodology

## Elasticsearch + Kibana Integration

## Elasticsearch Upload:

- Local deployment (v8.11.1)

- Created index: ‘clickstream’

- Used Python script (upload_clickstream.py) for batch upload [batch of 500]

## Kibana Dashboarding:

- Used Kibana Lens

- Built interactive visualizations

## Visualization Types:

- Bar/Pie Charts: Top product categories, payment insights

- Sunburst Chart: Category → Sub-category → Article

- Heatmap: Session time vs. conversion

- Geo-Map: Delivery hotspots from lat/long

## Stakeholder Value:

- Enables insights on user behavior, device usage, promo patterns

- Empowers data-driven marketing and UI optimization


## Dashboard Results

## Goal of the Dashboard:

To deliver a unified, interactive view of user behavior across product interest, traffic source, device usage,

demographics, spend patterns, and location — enabling strategic decisions in marketing, product targeting, UI design,

and promotions.

[Dashboard: http://localhost:5601](http://localhost:5601/)

## Business Insight:

Support data-driven growth by identifying high-value customer segments, effective acquisition channels, and

regional demand trends to optimize sales, engagement, and operational efficiency.

9


## SVD Product Recommendation System

## Pre-processing steps:

- 1. Column Selection: Extracted specific columns from each CSV file:

- customer.csv: customer_id, gender, home_location, home_country

- transactions.csv: customer_id, session_id, product_metadata

- click_stream.csv: session_id, event_name, event_time

- product.csv: product_id, productDisplayName, masterCategory, season

- 2. Metadata Parsing: Parsed product_metadata (JSON-like string) from transactions.csv to extract product_id.

- 3. Data Cleaning: Filled missing values using mean (numeric) or mode (categorical); removed duplicate customer_id entries.

- 4. Data Integration: Combined all datasets using outer joins on customer_id, session_id, and product_id to build a final consolidated dataset.

10


## End-to-End Pipeline for Collaborative Filtering Recommendation System

## Step 1: Load Product Data

- File loaded: product.csv (Size: 4.26 MB)

- Columns read: product_id, productDisplayName

- Data shape: 44,446 rows × 2 columns

- Unique products: 44,446

## Step 2: Build Interaction Matrix

- File loaded: consolidated_ecommerce_data (Size: 3423.24 MB)

- All columns in dataset:

customer_id,

gender,

home_location,

home_country,

session_id,

product_id,

event_name,

event_time,

productDisplayName,

masterCategory,

season

## • Columns used for processing:

customer_id,

product_id,

event_name

## Step 3: Interaction Matrix Summary

- Total chunks processed: 424

- Matrix shape: (1,253,113 rows, 3 columns)

- Unique users: 50,704

- Unique products: 44,446

- Maximum rating value: 62

- Final output columns: customer_id, product_id, rating

## Step 4: SVD Model Training

- Model: Collaborative Filtering using SVD

- Input columns: customer_id, product_id, rating

- Training interactions: 1,002,490

- Test interactions: 250,623

- Status: Model training completed

## Step 5: UI Creation for Recommendations

Purpose: Building an interactive UI for product recommendations

## Columns used:

- customer_id (from interaction_df)

- product_id

- productDisplayName (from product_df)


## SVD Product Recommendation System

- Interaction Matrix: Filters only ADD_TO_CART events, groups by customer_id and product_id, and counts interactions as implicit ratings.

- Model Training: Uses the Surprise library's SVD algorithm to train a collaborative filtering model on the user-product rating data.

- Recommendation Logic: For a given customer, predicts preference scores for all products not yet added to cart and selects top 5 with highest scores.

- Score Meaning: The predicted score reflects how likely the customer is to prefer a product — higher scores indicate higher predicted interest based on past behavior.

| Product ID | Product Name | Score |
| --- | --- | --- |
| 5681 | Skechers Men's Compelling Dexterity Fudge Brown Shoe | 6.67 |
| 7257 | Rockport Men's Alfrew Dark Tan Shoe | 6.64 |
| 28851 | Proline Charcoal Grey Polo T-shirt | 6.61 |
| 15177 | Arrow Sport Men Solid Navy Blue Sweaters | 6.37 |
| 17577 | Mark Taylor Men Solid Grey Trouser | 6.3 |

12


## Conclusion

- The project demonstrated the potential of clickstream data analysis in understanding user behavior and preferences in a real-time digital environment.

- By implementing a collaborative filtering-based recommendation system using SVD, we were able to generate personalized product suggestions that align with user interests.

- The use of Apache Spark enabled scalable processing of high-volume data, while Elasticsearch and Kibana provided powerful tools for indexing, searching, and visualizing user activity.

- Interactive dashboards created during the project offer valuable business insights, helping stakeholders make data-driven decisions.

- Overall, the project highlights the importance of behavioral data in enhancing user experience and optimizing digital engagement strategies.

13
