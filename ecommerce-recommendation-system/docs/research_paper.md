# A Big Data framework for Clickstream Analysis: User Behavior Analysis and Product Recommendation System

Manju Venugopalan

G. Pandi Kumar

Sv. Pethaa

Department of Computer Science

Department of Computer Science

Department of Computer Science

and Engineering

and Engineering

and Engineering

Amrita School of Computing, Bengaluru Amrita Vishwa Vidyapeetham, India

Amrita School of Computing, Bengaluru Amrita Vishwa Vidyapeetham, India

Amrita School of Computing, Bengaluru Amrita Vishwa Vidyapeetham, India

v manju@blr.amrita.edu

pandikumarmech72@gmail.com

pethaa.sv@gmail.com

Abstract—The study of user behavior is important to develop interactive and user-centered digital platforms. Although conven- tional recommendation systems offer fundamental level insights, they are not always scalable, do not visualize, and do not offer personalized recommendations based on individual interactions of users with the system. The limitations were overcome in this work by employing clickstream data as an effective instrument for studying user navigation behavior and for improving decision- making. Apache Spark was used to process clickstream logs in order to guarantee the effective processing of massive data, and Elasticsearch and Kibana made it possible to provide querying and visualization with the help of interactive dashboards. The behavioral insights depicted in these visualizations include prod- uct interactions, demographic usage patterns, device preferences, and site access points. Besides, a collaborative filtering method with Singular Value Decomposition (SVD) algorithm applied to construct a personalized product recommendation system is also incorporated into this work. The system, unlike most conventional methods, provides the most popular 5 items to every user based on his/her activity with confidence values. The model achieved an RMSE of 0.2702 (6.76%) and MAE of 0.1937 (4.84%), indicating a strong ability to predict user preferences accurately. Combining big data frameworks and intelligent recommendation systems to perfection, leads to improved customer experience and retention. This work addresses major missing links in the available systems, where scalable processing is integrated with data analytics and personalized recommendations into an integrated solution to e- commerce systems.

Index Terms—Big Data Analytics, Apache Spark, Recommen- dation system, Kibana, Elastic Search, Collaborative filtering

## I. INTRODUCTION

Digital user behavior studies through clickstream data pro- vide strong capabilities that enable organizations to understand online user activities. User preferences together with their interests and pain points reveal themselves through every user action such as clicking and hovering between web pages. The systematic evaluation of this data shows businesses how customers interact with content and which gives them more clarity on the decision-making drivers in business. The es- sential insights from data help to enhance user experience as well as to the improve web design, which enables designers

to provide personalized recommendations to match individ- ual tastes. Recommendation systems get their effectiveness enhancement from clickstream analysis because users receive content tailored to match their interests. Developers together with marketers design site navigation structure for achieving better user flow. Clickstream data provides multiple benefits beyond usability since it helps business detect fraudulent activities. Question answering system [1] and recommendation system has been developed using various word embedding techniques [2]. The Product recommendation system gives firms the ability to achieve the customer necessities and customize their experiences and drive more sales [3] [4]. Organizations that use clickstream insights have access to essential information which enables them to improve business success while increasing customer satisfaction while remaining competitive in today’s evolving market. [URL 🔗](#page-0)

Through big data tools and Machine learning Models busi- nesses today obtain better performance from clickstream anal- ysis and product recommendation implementations because these tools extract valuable insights from tremendous user interaction data [5, 6, 7] and Apriori Algorithm has been used to develop product recommendation system [8]. The collection of every user interaction known as clickstream data produces essential knowledge about customer conduct alongside their personal choices. The processing of this large-volume quick- moving data depends on reliable big data frameworks for immediate information processing and analysis. Apache Spark functions as a distributed computing engine to process large volumes of clickstream data by efficiently handling both struc- tured and unstructured data elements which leads to identifi- cation of behavioral patterns for better decision-making. The rapid search functionality of Elasticsearch increases analysis performance by creating user interaction data indexes that permit businesses to acquire essential insights at high speed and modify their recommendation methods in real-time. [URL 🔗](#page-0)

Organizations use Kibana as a visualization platform to design user-friendly dashboards that analyze data patterns thereby discovering abnormal behaviors so they can improve


recommendation decision making for better customer interac- tion. These tools partner to enable companies for developing highly personalized recommendation systems which produces higher user retention rates while increasing customer satisfac- tion levels. [9] Organizations can categorize their customers through big data analysis according to their behaviors to an- ticipate their interests so they can create personalized product proposals. [URL 🔗](#page-0)

The primary objectives of the study are described below:

- 1) User Behavior Analysis: Employ big data solutions to evaluate click stream data which helps detect user activities and their purchase behaviors.

- 2) Personalized Recommendation System: Develop a recommendation engine to recommend personalized product based on how users interact with the site.

- 3) Efficient Data Processing Searchability: Uses Apache Spark together with Elasticsearch to process enormous data volumes efficiently.

This research paper follows a structure where Section 2 reviews existing literature, Section 3 describes datasets, Sec- tion 4 explains data processing alongside recommendation implementation. Section 5 discuss about results and discussion and Section 6 provides conclusion.

## II. RELATED WORKS

The analysis of clickstream data is now essential because of increasing popularity of web-based services and online learning platforms. According to the study of Hanamanthrao and Thejaswini [10], A streaming analysis solution based on Apache Kafka, Spark Streaming, ElasticSearch, Kibana shows its superiority over traditional batch processing for business intelligence applications. Vijaya Bharathi et al. [11] developed a complete framework to analyze e-commerce clickstreams which specifically addressed the issues in present-day recom- mendations and marketing methods. The authors examined dif- ferent pattern discovery techniques which included K-Nearest Neighbour (KNN) as well as Decision Trees, Markov Models, Na¨ıve Bayes, and Cognitive Models for investigating user navigation patterns and behavioral patterns. The combination of big data technologies with e-commerce marketing systems at an enterprise level was studied by Li and Zhang [12]. [URL 🔗](#page-0)

The development team employed the SSH framework to- gether with HBase database for backend actions which re- sulted in faster query times than MySQL and other relational databases. Guihe H [13] presented four autonomous credit systems that uphold social bonds in e-commerce deals through independent means. A dynamic Boben model was used in the research. Alrumiah and Hadwan [14] analyzed how Big Data Analytics drives e-commerce vendor success through improved competition and strengthened customer relations despite facing problems linked to data excess and expenditure on analytic tools. The e-commerce industry benefits from big data analytics and machine learning models according to study by Zineb et al. [15] for making decisions and understanding customers. As part of the research, Malhotra and Rishi [16] developed an e-commerce meta search system which applied [URL 🔗](#page-0)

RV algorithm combined with Hadoop-MapReduce technology to optimize search ranking and user interface. Big Data serves as an innovative force in e-commerce during emergencies [17] [URL 🔗](#page-0)

The research by Ros´ario and Raimundo [18] conducted an organized research to explore the development of e-commerce marketing approaches through data-driven personalization and social media activities and trust establishment. According to Sattiraju et al.[19] Apache Spark DataFrames enhance big data processing speed which leads to better e-commerce application analytics and decision-making. [URL 🔗](#page-0)

Thus, the reviewed literature collectively underscores the critical role of real-time click stream analytics, big data tech- nologies, predictive modeling, trust mechanisms, and machine learning in advancing the capabilities of modern e-commerce systems.

## III. DATA DESCRIPTION

The project relied on a dataset obtained from Kaggle [20] which included several different Table. The Customer Table comprises full user data with demographic details and device information together with spatial data. Details of each product were stored in the Product Table under categories such as gender, color, season, utility characteristics. The Transaction Table maintains a record of purchasing events which includes information about orders together with payment techniques and shipping destinations. The clickstream csv file contains details about the event name, session id, event id. [URL 🔗](#page-0)

## IV. METHODOLOGY

The section demonstrates how a complete large-scale click- stream data analysis system is build that integrates data pre- processing approaches with Spark and Elasticsearch indexing and Kibana dashboard visualization as well as SVD based Product Recommendation system. The Fig. 1 represents the architecture of proposed system. In Data Indexing and Visual- ization pipeline section, the data is indexed and searched using Elasticsearch and Kibana. It is employed to build dashboards that make it easy to view and study data interactions. In Product Recommendation System, the system collects user- product interaction data and then uses collaborative filtering (SVD). It suggests five products that fit a user’s needs best, based on their actions.

## A. Data Indexing and Visualization pipeline

1) Data Preprocessing: The first step is to clean and enrich the data present in the Clickstream, Customer, Product and Transaction raw datasets. Each source included vital informa- tion related to user actions as well as customer information and product details and transaction history records.

The main pre-processing obstacle concerned dealing with deeply interconnected data structures that use relationships between product IDs or session IDs. The data preprocess- ing step involved the reading and normalization of datasets through pandas and json programs which combined informa- tion through matched keys. Specifically:

- JSON columns were parsed and flattened.


- String values were stripped of whitespace and validated for nulls.

- Event timestamps were converted into uniform datetime formats.

- Categorical columns were kept as-is for later aggregation and filtering.

All four available datasets merged to form an enriched unified database. The updated DataFrame contained detailed information regarding user interactions along with device de- scriptions and demographic characteristics and specific prod- uct choices together with cost information and complete event records. The completed enriched dataset contained these columns as its final schema. All four datasets were joined into a unified enriched dataset. This enriched DataFrame included

high-granularity information on user behavior, device types, demographic metadata, product preferences, pricing, and event details. The final schema of the enriched dataset had the following columns: [customer id, session id, event name, event time, event id, traffic source, click product id, click quantity, click item price, created at, booking id,

payment method, promo code,

payment status, promo amount,

shipment fee,

shipment date limit,

shipment location lat, shipment location long, total amount,

trans product id,

trans quantity,

trans item price,

first name, last name, username, email, gender, birthdate, device type, device id, device version, home location lat, home location long, home location, home country, first join date, click product name, click masterCategory, click subCategory, click articleType, trans product name, trans masterCategory, trans subCategory, trans articleType].

The largest challenge in preprocessing occurred when we dealt with keeping data consistency across different record formats in a 500 MB dataset. To reduce memory consumption we used a process of breaking up data cleaning and merging in smaller sections. The enrichment process ended with export of the data as .parquet and .json files after complete validation was achieved.

2) Apache Spark Integration: The core engine to distribute data preprocessing and transformation tasks was Apache Spark version 3.5.0. The project employed Spark because it offers in- memory computing alongside scaleable performance and mul- tiple functionality including dataset filtering and joining ca- pabilities and aggregation operations. Through its DataFrame API Spark provided a way to apply schema definitions dur- ing execution and achieve lazy evaluation functionality. The pipeline’s stages based on Python had seamless operational integration because of choosing PySpark as a core engine. The system performed specific operations which included event name grouping followed by quantity summarization and timestamp parsing through high-parallelization methods. The execution time decreased substantially since(Method Name) was utilized rather than using pandas in its traditional form. Data skew and system failures did not affect processing because Spark’s fault-tolerant capabilities enabled the pipeline to recover from node failures and memory exceptions during trials. The processed data reached the driver and converted

into JSON Lines formats which were usable by Elasticsearch for ingestion.

3) Elasticsearch: The distributed RESTful search and an- alytics engine called Elasticsearch offers its functionality to users. The centralized system used Elasticsearch to create an indexed storage and rich database which supported both query processing and visualization capabilities. The local installation of Elasticsearch v8.11.1 operated in unauthenticated mode for better prototype development. The designed Python script through elasticsearch and jsonlines libraries performed batch- based document loading into Elasticsearch. A batch process of 500 records based on the helpers.bulk() API was used to upload the enriched JSON Lines data efficiently while avoiding memory problems. The custom index clickstream contained individual documents available for complete text search and field-based filtering of categories and time periods as well as device types and geographic regions. Through this data structure users could easily access multiple dimensional data segments using Kibana interface.

4) Kibana: Open-source visualization tool Kibana operates above Elasticsearch platform. Users created interactive dash- boards out of Kibana for the project which displayed user activities together with device data and product behavior and deal movement statistics. A set of visualizations was created through the use of Lens tools in combination with Maps and Pie Chart tools after data indexing. The Kibana interface made it easy for users to explore patterns and detect anomalies and construct insights through its query-free interface.

## B. Product Recommendation System

1) Data Preparation and Preprocessing: Several key columns form an aggregated data set which supports the creation of recommendation systems. From customer CSV file, the data pipeline retrieves customer id, gender, home location and home country since these fields function as demo- graphic markers. The aggregated dataset incorporates both customer id and session id with additional data inside the product metadata field from transaction csv file. A pars- ing function retrieves essential product information by ex- tracting product id from within product metadata. From the click stream csv file, The database records behavioral data primarily through session id, event name and event time data points. ProductDisplayName together with masterCategory and season data are fetched from the product csv file.

All this information is merged to form a comprehensive aggregated dataset with the following columns: customer id, gender, home location, home country, session id, product id, event name, event time, productDisplayName, masterCate- gory, and season. To ensure no relevant information is lost during the merging process, outer joins are performed on the shared keys: customer id, session id, and product id. A solid groundwork for generating recommendations emerges from bringing together all required customer usage and behavioral data with product related information.

2) Collaborative filtering recommendation system: The Project builds a collaborative filtering recommendation system


*Fig. 1. System Architecture for clickstream Data Driven- Product Recommendation system and Dashboard Visualization*

through the Singular Value Decomposition (SVD) algorithm within the surprise library. The program reads the aggregated dataset then selects only ADD TO CART events before cre- ating a user-item interaction matrix that shows product/cart intersection frequency for customers. With this interactive matrix the system develops an SVD model that extracts hidden patterns between customer activities and product selections. After completion of the training process the model generates score predictions for items that users have not experienced be- fore. This score demonstrates the likelihood that the customer will show preference for the product through a numerical value where higher scores represent stronger identification of favor. The built ipywidgets interactive user interface enables users to choose a customer ID followed by the display of recommended products based on score predictions accompanied by product names and IDs.

## V. RESULTS AND DISCUSSIONS

## A. Data Indexing and Visualization pipeline

The clickstream analysis project established a complete big data pipeline to process unprocessed user log information into business-ready insights for decision support. Apache Spark handled the large-scale preprocessing tasks then Elasticsearch stored the enriched dataset before Kibana visualized the data for behavioral and transactional pattern identification.

The dashboard results show critical interaction patterns between users. The visualization of ”Top Clicked Product Categories” reveals strong user preference patterns by demon- strating specific categories that attract significantly higher click rates. By using the sunburst chart shown in Fig 2 we obtained detailed analysis of user navigation paths that disclosed the necessity of better categorization structures throughout the user interface. The data demonstrated organic traffic and referrals delivered the highest number of clicks within fashion- related categories yet paid advertisements spread their reach across the entire audience. The data shows organic engagement

*Fig. 2. Visualization of Category-Wise Product Composition*

rates tend to remain high in scenarios featuring brand or visual affinity with users. Results from the device usage analysis demonstrated female users chose mobile devices most often so application designers need to prioritize mobile first for better engagement with this audience. The data demonstrated that users between 18 and 25 years old spend less on multiple items yet spend more per individual purchase than users with greater age. The obtained information proves essential for creating targeted marketing campaigns based on age groups. The payment method analysis showed UPI-based transactions hold dominance in addition to linking to greater average spending possibilities that could guide potential partnerships with digital wallet providers.

A promotional usage map shown in Fig.3, displayed spatial hot-spots centered in urban areas because users from these regions prefer to use discount codes. The payment method


*Fig. 3. Comparison of Promotional Channel Adoption by Region*

analysis paired with this information assists businesses in designing location-based marketing promotions that target specific methods. The last geospatial map showed that most delivery addresses are located within large urban areas. The ge- ographic information enables productive warehouse operations and supply chain logistics management. Through a unified interface the dashboard combines user data with browsing activities and product interactions and purchasing events. Stakeholders in the organization gain evidence-based powers to optimize their decision-making about UI design and product scheduling as well as marketing plans. The pipeline proves how big data tools enable e-commerce applications to handle scalable real-time behavioral analytics.

## B. Product Recommendation System

Using collaborative filtering the product recommendation system transforms customer interaction data into personalized product suggestions. The process starts by mounting the aggre- gated dataset then it loads customer activity logs and product information. The system uses ADD TO CART activity logs to build a user-item interaction matrix that shows product to user cart addition frequencies. Using Surprise library the SVD model receives training data from this matrix. The table 1 given below shows the top 5 recommended Product for customer ID 20.

| Product ID Product Name |   | Predicted Score |
| --- | --- | --- |
| 4100 | Puma Women Pink Grey | 4.50 |
|   | Sandal |   |
| 45231 | Casio Youth Series | 4.49 |
|   | Women Digital Watch |   |
| 7492 | Nike Women Squad | 4.47 |
|   | Black Capri |   |
| 49163 | Deborah Kajal 112 | 4.47 |
| 43844 | Royal Diadem Golden | 4.47 |
|   | Earrings |   |

*Table 1: Top-5 Product Recommendations with Predicted*

*Scores*

All products currently unknown to a customer receive prediction scores from the trained model enabling recom- mendations of the top 5 products with highest scores. The ipywidgets enables a seamless interface letting users choose a customer ID while delivering recommendations through an interactive HTML table view. The prediction score reflects a customer’s preference probability for products by analyzing their logged past actions. The model assessment produces the RMSE 0.2702, covering 6.76 percent of the rating range, and the MAE 0.1937 that is 4.84 percent of the rating range. These measures denote how well the model infers on the test data.

## VI. CONCLUSION

The work achieves successful implementation of scalable big data pipelines together with personal recommendation systems that bring new insights and better e-commerce user experiences to customers. Through the integrated solution of Apache Spark with Elasticsearch and Kibana, raw clickstream logs were processed to generate operative dashboards that track user behavior patterns across product interactions and demographic groups along with device preferences and site en- try points and geographic locations. Through these discovered insights stakeholders can decide on strategic marketing choices including user interface development alongside supply chain operational decisions. The Surprise library enabled creation of a recommendation engine through collaborative filtering and SVD to recommend products based on user activity records. the model exhibits good performance through RMSE of 0.2702 (6.76% of the rating range) and MAE 0.1937 (4.84% of the rating range). These findings indicate that the model is effective at getting the user preferences right.Through Product recommendations, this system boosts customer involvement which results in increased revenue from relevant product promotion.

The work has the potential for future development using real-time stream processing through Apache Kafka as well as advanced machine learning and enhanced customer feedback integration. Additional features may add content-driven recom- mendation engines while combining different recommendation methods into hybrid approaches. Behavioral analytics com- bined with personalized recommendations demonstrate why data-driven solutions have become essential in e-commerce while representing a solid base for developing future customer intelligence and personalization innovations.

## REFERENCES

- [1] P. Aich, M. Venugopalan, and D. Gupta, “Enhancing per- sonalized response to product queries using product re- views incorporating semantic information,” in Advances in Data and Information Sciences: Proceedings ofICDIS 2019. Springer, 2020, pp. 497–509.

- [2] P. D. Reddy, K. S. S. Reddy, P. Gnaneswarachary, P. L. Reddy, M. Venugopalan, S. Vekkot, and P. C. Nair, “En- hancing content based collaborative filtering recommen- dations using weighted word embeddings,” in 2024 15th International Conference on Computing Communication


- and Networking Technologies (ICCCNT). IEEE, 2024, pp. 1–7.

- [3] M. R. Kumar, S. Vishnu, G. Roshen, D. N. Kumar, P. Revathi, and D. R. L. Baster, “Product recommenda- tion using collaborative filtering and k-means clustering,” in 2024 IEEE International Conference on Comput- ing, Power and Communication Technologies (IC2PCT), vol. 5. IEEE, 2024, pp. 1722–1728.

- [4] M. V. K. Kiran, R. Vinodhini, R. Archanaa, and K. Vi- malkumar, “User specific product recommendation and rating system by performing sentiment analysis on product reviews,” in 2017 4th international conference on advanced computing and communication systems (ICACCS). IEEE, 2017, pp. 1–5.

- [5] D. Koehn, S. Lessmann, and M. Schaal, “Predicting online shopping behaviour from clickstream data using deep learning,” Expert Systems with Applications, vol. 150, p. 113342, 2020.

- [6] A. Ajesh, J. Nair, and P. Jijin, “A random forest approach for rating-based recommender system,” in 2016 Inter- national conference on advances in computing, commu- nications and informatics (ICACCI). IEEE, 2016, pp. 1293–1297.

- [7] E. Shaikh, I. Mohiuddin, Y. Alufaisan, and I. Nahvi, “Apache spark: A big data processing engine,” in 2019 2nd IEEE Middle East and North Africa COMMunica- tions Conference (MENACOMM). IEEE, 2019, pp. 1–6.

- [8] S. S. Baby and S. L. Reddy, “End to end product recommendation system with improvements in apriori algorithm,” in 2021 Third International Conference on Inventive Research in Computing Applications (ICIRCA). IEEE, 2021, pp. 1357–1361.

- [9] A. Baumann, J. Haupt, F. Gebert, and S. Lessmann, “The price of privacy: An evaluation of the economic value of collecting clickstream data,” Business & Information Systems Engineering, vol. 61, pp. 413–431, 2019.

- [10] R. Hanamanthrao and S. Thejaswini, “Real-time click- stream data analytics and visualization,” in 2017 2nd IEEE International Conference on Recent Trends in Electronics, Information & Communication Technology (RTEICT). IEEE, 2017, pp. 2139–2144.

- [11] A. V. Bharathi, J. M. Rao, and A. K. Tripathy, “Click stream analysis in e-commerce websites-a framework,” in 2018 Fourth International Conference on Computing Communication Control and Automation (ICCUBEA). IEEE, 2018, pp. 1–5.

- [12] L. Li and J. Zhang, “Research and analysis of an enter- prise e-commerce marketing system under the big data environment,” Journal of Organizational and End User Computing (JOEUC), vol. 33, no. 6, pp. 1–19, 2021.

- [13] G. He, “Enterprise e-commerce marketing system based on big data methods of maintaining social relations in the process of e-commerce environmental commodity,” Journal of Organizational and End User Computing (JOEUC), vol. 33, no. 6, pp. 1–16, 2021.

- [14] S. S. Alrumiah and M. Hadwan, “Implementing big data

- analytics in e-commerce: Vendor and customer view,” Ieee Access, vol. 9, pp. 37 281–37 286, 2021.

- [15] E. F. Zineb, R. Najat, and A. Jaafar, “An intelligent approach for data analysis and decision making in big data: a case study on e-commerce industry,” International Journal of Advanced Computer Science and Applica- tions, vol. 12, no. 7, 2021.

- [16] D. Malhotra and O. Rishi, “An intelligent approach to de- sign of e-commerce metasearch and ranking system using next-generation big data analytics,” Journal ofKing Saud University-Computer and Information Sciences, vol. 33, no. 2, pp. 183–194, 2021.

- [17] S. Kodadi, “Big data analytics and innovation in e- commerce: Current insights, future directions, and a bottom-up approach to product mapping using tf-idf,” International Journal of Information Technology and Computer Engineering, vol. 10, no. 2, pp. 110–123, 2022.

- [18] A. Ros´ario and R. Raimundo, “Consumer marketing strategy and e-commerce in the last decade: a literature review,” Journal of theoretical and applied electronic commerce research, vol. 16, no. 7, pp. 3003–3024, 2021.

- [19] S. R. Julakanti, N. S. K. Sattiraju, and R. Julakanti, “Implementing spark data frames for advanced data anal- ysis,” International Journal of Intelligent Systems and Applications in Engineering, vol. 9, no. 1, pp. 62–66, 2021.

- [20] A. B. Pratama, “E-commerce user behavior dataset,” Online, 2025, accessed: Apr. 28, 2025. [Online]. Available: transactional-ecommerce?select=click stream.csv https://www.kaggle.com/datasets/bytadit/
