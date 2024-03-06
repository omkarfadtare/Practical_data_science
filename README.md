# Practical data science on AWS cloud:
In this project, you'll learn how to turn your data science project ideas into real-world solutions. Then, you'll learn to analyze and clean datasets, extract relevant features, train models, and construct automated pipelines to orchestrate and scale your data science projects, serving thousands of models to millions of end-users using AutoML. Following that, you'll learn to create and deploy ML pipelines that manage the flow of data and models, especially using a powerful tool called BERT. Additionally, you'll learn how to deploy human-in-the-loop pipelines, processes that involve humans in decision-making, to make your models work even better.

__Prerequisites for this project:__
- Proficiency in Python and SQL programming.
- Familiarity with building neural networks using deep learning Python frameworks like TensorFlow or PyTorch.
- Understanding of the concept of building, training, and evaluating machine learning models.

__Brief introduction to Artificial intelligence and Machine learning:__
- ___`Artificial intelligence`___, is generally described as a technique that lets machines mimic human behavior.
- ___`Machine learning`___, is a subset of AI, that uses statistical methods and algorithms that are able to learn from data, without being explicitly programmed.
- ___`Deep learning`___ is yet another subset of ML, that uses artificial neural networks to learn from data.
- ___`Data science`___ is an interdisciplinary field that combines business and domain knowledge with mathematics, statistics, data visualization, and programming skills.

![image](https://github.com/omkarfadtare/Practical_data_science/assets/154773580/54ea4e85-d127-4fc2-9f1c-4eadd5c6b69b)

- Popular ML tasks are classification and regression problems, which are examples of supervised learning.
- In ___`Supervised learning`___, you learn by providing the algorithm with labeled data.
- In ___`Classification`___, the goal is to assign the input sample a defined class. For example, is this email I received spam or not spam?
- In contrast, ___`Regression`___ applies statistical methods to predict a continuous value, such as a house price, given a set of related and non-related input variables.
- Another popular task is clustering, it is an example of ___`Unsupervised learning`___ where the data is not labelled. The ___`Clustering`___ algorithm tries to find patterns in the data and starts grouping the data points into distinct clusters.
- Image processing is a major task of ___`Computer vision`___ where you need to classify images into pictures of dogs and cats, distinguish between speed signs and trees.
- The field of ___`Natural Language Processing`___ (NLP), or ___`Natural Language Understanding`___ (NLU) includes machine translations, sentiment analysis, question answering, etc.

![image](https://github.com/omkarfadtare/Practical_data_science/assets/154773580/7ae4c166-5944-4539-aeac-ba763619bf55)

__Benifits of performing data science project on cloud:__
- Data science project on cloud is geared towards handling massive datasets, that could originate from social media channels, mobile and web applications, public or company internal data sources, and much more, depending on the use case you're working on. This data is often messy, potentially error-ridden, or even poorly documented.
- Data science project on cloud tackles these issues by providing tools to analyze and clean the data and to extract relevant features and leads to knowledge distillation and gaining insight from those large datasets.
- Developing and running data science projects on cloud offers the agility and elasticity. If you develop data science projects in a local notebook or IDE environment, for example, hosted on your laptop or a company-owned server pool, you are limited by the existing hardware resources.You have to carefully monitor how much data you process and how much CPU processing power you have available to train and tune your model. If you need more resources, you must purchase additional computing resources. This process doesn't allow for quick development and movement. Perhaps your model training takes too long because it consumes all of the CPU resources of the compute instance you have chosen.
- Using the cloud, you can switch to a compute instance that has more CPU resources, or even switch to a GPU-based compute instance.
- The cloud allows you to train your model on a single CPU instance i.e. ___`Scaling up`___ or perform distributed model training in parallel across various compute instances i.e. ___`Scaling out`___
- In the cloud, when the model training is completed, the instances are terminated as well. This means you only pay for what you actually use.
- The cloud allows you to store and process almost any amount of data. It also comes with a large data science and machine learning toolbox from which you can choose, to perform your tasks as fast and efficiently as possible.

![image](https://github.com/omkarfadtare/Practical_data_science/assets/154773580/5d4e0e9a-c2b5-4570-a99f-92ab3355dbec)

## Project use case: Multi-class classification for Sentiment analysis of Product reviews
- Assume you work at an e-commerce company, selling many different products online. Your customers are leaving product feedback across all the online channels. Whether it is through sending email, writing chat FAQ messages on your website, maybe calling into your support center, or posting messages on your company's mobile app, popular social networks, or partner websites. And as a business, you want to be able to capture this customer feedback as quickly as possible to spot any change in market trends or customer behavior and then be alerted about potential product issues.
- Your task is to build an NLP model that will take those product reviews as input. You will then use the model to classify the sentiment of the reviews into the three classes of positive, neutral, and negative.
- Multi-class classification is a supervised learning task, hence, you must furnish your classifier model with examples to correctly learn how to classify products and product reviews into the respective sentiment classes. 
- You can use the review text as the input feature for model training and assign sentiment labels to train the model. Sentiment classes are typically represented as integer values during model training, such as 1 for positive sentiment, 0 for neutral sentiment, and -1 for negative sentiment.

## Data ingestion and Exploration:
-  ___`Data ingestion`___ is the process of bringing data from various sources, such as databases, files, or websites, into a system where it can be used. Think of it like gathering ingredients into your kitchen before cooking a meal.
- Imagine your e-commerce company collecting customer feedback from multiple online channels, including social media, support center calls, emails, mobile apps, and website data.
- To accomplish this, you need a flexible and scalable repository capable of storing different file formats, including structured data like CSV files and unstructured data like support center call audio files. Additionally, it should dynamically scale storage capacity as new data streams in.
- Cloud-based data lakes provide a solution to this problem. A ___`Data lake`___ is a centralized and secure repository that can store, discover, and share virtually any amount and type of data.
- Data can be ingested into a data lake in its raw format without prior transformation. Whether it's structured relational data in CSV or TSV files, semi-structured data like JSON or XML files, or unstructured data such as images, audio, and media files. Additionally, you can ingest streaming data such as continuous log file feeds or social media channel feeds into your data lake.
- Effective governance is crucial for managing a data lake. With new data continuously arriving, it's essential to implement mechanisms for discovering and cataloging incoming data.
- There are three types of storage technologies used in computer systems and data storage solutions.
  > ___`File storage`___ organizes data as individual files stored in a hierarchical directory structure. It is similar to how files are organized on personal computers or file servers. File storage is well-suited for storing structured and semi-structured data, such as documents, spreadsheets, multimedia files, and application data.
  > ___`Block storage`___ manages data as individual blocks or chunks, typically at the disk level. Each block is a fixed-size unit of data and is accessed using block-level protocols like SCSI (Small Computer System Interface) or Fibre Channel. Block storage is commonly used in storage area networks and provides high-performance, low-latency access to data.
  > ___`Object storage`___ is a storage architecture that manages data as objects. Each object consists of data, metadata (information that describes data, such as when the object was last modified), and a unique identifier.
- Data lakes, such as Amazon S3 are often built on top of object storage. Amazon S3 provides access to durable and highly-available object storage in the cloud, allowing you to ingest virtually any amount of data, from a few dataset files to exabytes of data.
- AWS provides various tools and services that help ensure your data lake, which is built on Amazon S3, is secure, compliant with regulations, and allows for auditing. These tools and services include features like access control, encryption, data governance, and compliance certifications, which help protect your data and ensure it meets legal requirements.
- By using Amazon S3 as a centralized repository for your data lake, you can easily access and analyze your data for data warehousing analytics. Data warehousing analytics involves analyzing large volumes of structured data to gain insights and make informed decisions. Additionally, you can leverage machine learning tools and algorithms to extract valuable insights from your data, identify patterns, and make predictions or recommendations based on your business needs.
- Data lakes and data warehouses are both technologies used for storing and analyzing data, but they have different architectures and purposes
  > ___`Data lake`___ are repositories that store vast amounts of raw, unstructured, and structured data in its native format. They are designed to ingest and store data from various sources, such as databases, sensors, logs, social media, and more, without prior transformation. Data lakes are ideal for exploratory data analysis, data science, and big data processing, as they enable organizations to retain and analyze raw data for future use. ex: ___`AWS S3 Bucket`___
  > ___`Data warehouse`___ are structured repositories that store processed and organized data in a structured format. Data warehouses undergo a process of extraction, transformation, and loading (ETL) to clean, transform, and integrate data from different sources before loading it into the warehouse. Data warehouses provide a consolidated view of business data and are optimized for high-performance analytics, reporting, and business intelligence (BI) applications. They are used for historical analysis, generating reports, and supporting decision-making processes. ex: ___`AWS Redshift`___
- ___`AWS Data wrangler`___ is an open-source Python library, that helps you interact with data stored in AWS environments and provides easy-to-use functions to load data from AWS services like S3, Glue, Athena, Redshift, and more into Python environments (such as Jupyter notebooks), and to push processed data back into AWS services.
- For example, if you have a bunch of data stored in an Amazon S3 bucket and you want to use it in your Python code (perhaps for analysis, visualization, or machine learning), AWS Data Wrangler makes it simple to load that data into a Pandas DataFrame. Similarly, if you've processed some data in your Python code and want to store it back into an AWS service like S3 or Redshift, AWS Data Wrangler provides functions to easily accomplish that task too.




Amazon Sagemaker -> Studio -> Open studio -> Launch -> Studio -> Open launcher -> Open System terminal -> 


![image](https://github.com/omkarfadtare/Practical_data_science/assets/154773580/95159905-3c7e-4d11-96b4-4f90f811b654)
![image](https://github.com/omkarfadtare/Practical_data_science/assets/154773580/da4f2c5a-ce50-4ed2-87d4-7ed0d0e19d88)
![image](https://github.com/omkarfadtare/Practical_data_science/assets/154773580/e7320ed0-29a2-4b32-9e7c-f4fbd8efcccb)
![image](https://github.com/omkarfadtare/Practical_data_science/assets/154773580/d61a5335-bb75-48a4-8915-b8ac4fb9aab2)
![image](https://github.com/omkarfadtare/Practical_data_science/assets/154773580/1f4b4a96-6320-46fa-bc68-6ba0a8ea41ac)
![image](https://github.com/omkarfadtare/Practical_data_science/assets/154773580/a7d622ba-fbf1-4c4a-876d-2c3cbd583b97)











!pip install awswrangler

import awswrangler as wr
import pandas as pd

df = wr.s3.read_csv(path='s3://bucket/prefix/')
```
- __AWS Data catalog services__ are used to register or catalog the data stored in S3. It is like a list/inventory that keeps track of all the data stored in S3. It helps you to know what data you have in your S3 storage. 
- When you use the data catalog services, it's like establishing a reference between a file you have stored in Amazon S3 and a table. This table is managed by __AWS Glue__, and it lives in a special database created by AWS Glue. However, this table doesn't contain the actual data, it just holds metadata information such as the data schema.
- Instead of registering data manually, you can use __AWS Glue Crawler__. It's a tool that can automatically scan your data to find out what's there.
- It figures out how the data is structured and keeps your data catalog updated without you having to do it yourself.
- To register data you can use AWS Data Wrangler tool following below steps:
> Start by creating a database in the AWS Glue Data Catalog database using the command below:
```ruby
import awswrangler as wr

wr.catalog.create_database(name=name_for_the_database)
```
> Next, create a CSV table (metadata only) in the AWS Glue Data Catalog using the command below:
```ruby
wr.catalog.create_csv_table(database=name_of_the_database, table=name_of_the_table, column_types=...)
```
- __AWS Athena__ is a tool used to query the data stored in S3. It allows you to use standard SQL queries to explore your data interactively.
- Athena is serverless, meaning you don't have to set up any infrastructure to run your queries. Regardless of the data's size, you can simply write your SQL query, referencing the dataset schema provided in the AWS Glue Data Catalog.
- To execute a query, follow these steps from your Python environment:
> Begin by setting up Amazon Athena to access your data stored in S3.
```ruby
import awswrangler as wr

wr.athena.create_athena_bucket()
```
> Next, execute your SQL query on Amazon Athena:
```ruby
df = wr.athena.read_sql_query(sql='sql_query', database=name_of_the_database)
```
- Athena processes the query on the specified dataset, stores the results in S3, and returns them as a Pandas DataFrame.
- When running highly complex analytical queries against large volumes of data, Athena automatically scales out and divides the query into simpler ones to run in parallel. This capability is possible because Athena is built on Presto, an open-source distributed SQL engine designed for this purpose.



![image](https://github.com/omkarfadtare/Practical_data_science/assets/154773580/09a430f3-3175-4630-a5ce-f3bd4e31eb37)

### Data visualization:
- The type of visualizations you use may vary depending on the type of data you're exploring and the relationships you're examining within the data.
- Pandas, an open-source library, is utilized for data analysis and manipulation.
- NumPy, another open-source library, facilitates scientific computing in Python.
- Matplotlib aids in creating static, animated, and interactive visualizations.
- Seaborn, built on top of matplotlib, enhances visualizations with statistical data analysis.

> Section A
- In this section, you will learn how to ingest the data into a central repository, explore the data using various tools, and analyze the dataset using interactive queries and learn how to visualize the results.
- You will perform exploratory data analysis to detect statistical data biases and class imbalance.
- Next, you will learn to train machine learning models using automated machine learning techniques and build a multi-class text classification model using state-of-the-art algorithms.
- You will understand how to describe the concept of statistical bias, and use metrics to measure imbalances in data sets.
- You will understand how to detect statistical bias in your data and generate bias reports. You will further explore how to generate feature importance reports.

### Important links:
[Dataset](https://www.kaggle.com/datasets/nicapotato/womens-ecommerce-clothing-reviews)
[AWS SDK](https://github.com/aws/aws-sdk-pandas)
[AWS Glue](https://aws.amazon.com/glue/)
[AWS Athena](https://aws.amazon.com/athena/)
[matplotlib](https://matplotlib.org/)
[Seaborn](https://seaborn.pydata.org/)
[Pandas](https://pandas.pydata.org/)
[NumPy](https://numpy.org/)
[AWS Wrangler](https://aws-sdk-pandas.readthedocs.io/en/stable/)



## Statistical bias and Feature importance:
- Statistical bias and feature importance help you gain a better understanding of your data quality and how individual features contribute to your model.
- These concepts also allow you to explore how the individual features of your datasets contribute to the final model.
- A dataset is biased if it fails to accurately represent the underlying problem space. Statistical bias refers to a statistic's tendency to either overestimate or underestimate a parameter.
- For instance, in a dataset where fraudulent credit card transactions are rare, fraud detection models may struggle to identify fraudulent transactions due to lack of exposure.
- Similarly, consider a product review dataset where one product category (A) has a large number of reviews compared to categories B and C. When building a sentiment prediction model using this biased dataset, the model may accurately predict sentiments for category A products but perform poorly for categories B and C.
- One solution to this issue is to augment the training dataset with more examples of fraudulent transactions.

__Types of Bias:__
> 1) Activity bias:
- Activity bias occurs when certain groups or individuals are overrepresented or underrepresented in the data due to their level of engagement or activity.
- In an online shopping dataset, frequent users may have more data recorded about their preferences and behaviors compared to occasional users, leading to biased predictions.
> 2) Societal bias:
- Societal bias reflects existing societal inequalities and prejudices that are reflected in the data, leading to unfair treatment of certain groups.
- Historical biases against certain demographics (e.g., race, gender) may be perpetuated in datasets, resulting in biased decisions in areas like hiring or lending.
> 3) Selection bias:
- Selection bias occurs when the data collection process systematically favors certain samples over others, leading to an unrepresentative dataset.
- A survey conducted only among tech-savvy individuals may not accurately represent the opinions of the general population, leading to biased conclusions.

__Types of drift in Machine learning operations:__
> 1) Data drift:
- Data drift happens when the data used by a model changes over time, making the model less accurate
> 2) Concept drift:
- Concept drift occurs when the relationship between the model's input and output changes over time.
- For example, if you're predicting whether someone will buy a product based on their age, and suddenly younger people start buying more than older people, that's concept drift.
> 3) Covariate drift:
- Covariate drift happens when the characteristics used by the model to make predictions change over time.
- Let's say you're trying to predict how much ice cream people will buy based on the temperature. If suddenly people start buying more ice cream on colder days instead of hotter ones, that's covariate drift.
> 4) Prior probability drift:
- Prior probability drift is the shift in the frequency of each outcome over time.
- Imagine you're flipping a coin, and at first, it comes up heads 70% of the time and tails 30% of the time. Your model learns from this and gets good at predicting based on that. But then, over time, the coin changes, and now it's heads only 50% of the time and tails 50% of the time.
> 5) Model drift: 
- Model drift is when a model that used to perform well becomes less accurate over time.
- This can happen if the data the model was trained on changes, or if the world changes in a way that the model didn't expect. 
> 6) Population drift:
- Population drift occurs when the population the model is applied to changes over time, making the model less accurate.
- Let's say you're building a model to predict what kind of movies people will like, and you train it on data from one country. If you then try to use that model in a different country where people have different tastes, that's population drift.
> 7) Label drift:
- Label drift is when the answers or labels you have for your data change over time.
- It's like if you were trying to label pictures of cats and dogs, but then someone changed their mind about what a cat looks like. So, the labels for the pictures change, making it harder for your model to learn from them because the right answers keep changing.

__Measuring statistical bias:__
- Class imbalance, or CI, shows if there are more examples of one thing than another in your dataset.
- A facet is a sensitive feature in your dataset, that you want to analyze for these imbalances.
- For example, CI can tell us if one product category has a lot more reviews than others.
- The Difference in Proportions of Labels (DPL) metric checks if one group has more positive outcomes than others. When applied to the product review dataset, what this metric is measuring is if a particular product category, say product category A, has disproportionately higher ratings than other categories.
- So, while CI looks at overall reviews, DPL looks at whether some categories get higher ratings than others.
- For example, consider we have a dataset of customer reviews for an e-commerce platform. Each review is labeled as either "positive" or "negative" sentiment based on the customer's feedback.
- Class imbalance occurs if there are significantly more positive reviews than negative reviews, or vice versa.
- DPL would assess whether certain product categories receive a disproportionately higher proportion of positive reviews compared to others.

__AWS tools to detect statistical bias in dataset:__
- The two AWS tools used to detect statistical bias in datasets are SageMaker Data Wrangler and SageMaker Clarify.
- ata Wrangler allows you to connect to various data sources, visualize, and transform data, detect statistical bias, and generate reports on the detected bias in datasets. It also provides feature importance calculations for your training dataset.
- Amazon SageMaker Clarify can detect statistical bias and generate bias reports on training datasets. Additionally, it can detect bias in trained and deployed models. Moreover, it offers capabilities for machine learning explainability and detects data and model drift.

__Detecting Bias in Datasets Using Amazon SageMaker Clarify:__
- To use Clarify APIs, start by importing the SageMaker Clarify module from the SageMaker SDK and then construct the SageMakerClarifyProcessor object using the SageMakerClarifyProcessor constructor.
> 1) Constructing SageMakerClarifyProcessor object
```ruby
from sagemaker import clarify

clarify_processor = clarify.SageMakerClarifyProcessor(role=role, instance_count=1, instance_type="ml.c5.2xlarge", sagemaker_session=sess)
```

> 2) Define S3 path for bias report output
```ruby
bias_report_output_path = "s3://your-bucket-name/path/to/save/bias/report"
```
- instance_count represents the number of nodes that are included in the cluster 
- instance_type represents the processing capacity of each individual node in the cluster
- The processing capacity is measured by the node's compute capacity, memory and the network
- In the next step you configure the data config object on the clarify library, Data config object represents the details about your data

> 3) Configuring data config object
```ruby
bias_data_config = clarify.DataConfig(s3_data_input_path = "s3://your-bucket-name/path/to/input/data", s3_output_path = bias_report_output_path, label = 'sentiment', headers = df_balanced.columns.to_list(), dataset_type = 'text/csv')
```
label that we are going to predict
- In the next step, you configure the bias config object on clarify library. The bias config object captures the facet or the featured name that you are trying to evaluate for bias or imbalance. In this below case you are trying to find out the imbalances in the product category feature. SO if the sentiment feature is your label what is the desired value for that label. That value goes into the parameter label or threshold.
- The parameter label_values_or_threshold defines the desired values for the labels.

> 4) Configuring bias config object
```ruby
bias_config = clarify.BiasConfig(label_values_or_threshold=[...], 
                                 facet_name='product_category')
```
- In the next step you run the pre training bias method on the clarify processor.
>  Running pre-training bias method
```ruby
clarify_processor.run_pre_training_bias(data_config=bias_data_config, 
                                        data_bias_config=bias_config, 
                                        methods=["CI", "DPL", ...], 
                                        wait=False, 
                                        logs=False)
```
- In addition to specifying the data config and the data bias you already configured, You can also specify the methods that you want to evaluate for bias. These are nothing but the metrics that you already learned about to detetct bias.
- Wait parameter specifies whether this bias detection job should block your rest of the code or should it be executed in the background.
- Similarly logs parameter specify that whether you want to capture the logs or not.
- Once the configuration of the pre-training bias method is done, you launch this job. In the background, SageMaker Clarify is using a construct called SageMaker Processing Job to execute the bias detection at scale. SageMaker Processing Jobs is a construct that allows you to perform any data-related tasks at scale.
- These tasks could be executing pre-processing, or post-processing tasks, or even using data to evaluate your model.

- 
- As you can see in the figure here, the SageMaker Processing Job expects the data to be in an S3 bucket.  The data is collected from the S3 bucket and processed on this processing cluster which contains a variety of containers in the cluster.

![image](https://github.com/omkarfadtare/Practical_data_science/assets/154773580/94a703d1-c887-48ba-914e-24689a8f8525)

 Once the processing cluster has processed the data, the transformed data or the processed data is put back in the S3 bucket.  What do you think happens when you execute this run pre-training bias?
- The result will actually be a very detailed report on the bias on your dataset that has persisted in S3 bucket. You can download the report and review in detail to understand the behavior of your data.  you should see a few familiar metrics, like CI and DPL, and also a few other metrics that you might not know about.



__Which one of these tools should you use, in which situation?__
- Data Wrangler, provides you with more of a UI-based visual experience. 
- So, if you would like to connect to multiple data sources and explore your data in more visual format, and configure what goes into your bias reports by making selections from drop-down boxes and option buttons, and finally, launch the bias detection job using a button click, Data Wrangler is the tool for you.
- Keep in mind that Data Wrangler is only using a subset of your data to detect bias in that data set.
-  SageMaker Clarify provides you with more of an API-based approach. Additionally, Clarify also provides you with the ability to scale out the bias detection process.
-  SageMaker Clarify uses a construct called processing jobs that allow you to configure a distributed cluster to execute your bias detection job at scale. So, if you're thinking of large volumes of data, for example, millions of millions of rows of product reviews, and you want to explore that data set for bias, then SageMaker Clarify is the tool for you, so that you can take advantage of the scale and capacity offered by Cloud.




__Feature importance (SHAP):__
- Feature importance is the idea of explaining the individual features that make up your training data set, using a score called important score.
- Some features from your data set could be more relevant, or more important, to your final model than others. Using feature importance, you can rank the individual features in the order of their importance and contribution to the final model.
- Feature importance allows you to evaluate how useful or valuable a feature is, in relation to the other features that exist in the same data set.
- In case of product review dataset, It consists of multiple different features, and you are trying to build a product sentiment prediction model out of that data set.
- Feature importance is based on a very popular for open source framework called SHAP; SHAP stands for Shapley Additive Explanations.
- The framework itself is based on Shapley values, which in turn is based on game theory. consider a play, or a game, in which multiple players are involved and there is a very specific outcome to the play that could be either a win or a loss. Shapley values allow you to attribute the outcome of the game to the individual players involved in the game. you can use the same concept to explain the predictions made by the machine learning model.
- In this case, the individual players would be the individual features that make up the data set, and the outcome of the play would be the machine learning model prediction.
- Using the SHAP framework, you can provide both local and global explanations. While the local explanation focuses on indicating how an individual feature contributes to the final model, the global explanation takes a much more comprehensive view in trying to understand how the data in its entirety contributes to the final outcome from the machine learning model.
- SHAP framework it considers all possible combinations of feature values along with all possible outcomes for your machine learning model.

__How to use Data Wrangler to calculate feature importance on your data set__
- Amazon sagemaker studio >> New data flow >> S3/Athena >> navigate to the right bucket >> navigate to right data that you want to calculate the feature importance on >>  After selecting right csv you will see the preview of the columns in that csv file >> import dataset (THis action will bring the data from s3 bucket to data wrangler environment) >> Once the data is imported click of + sign >> Add analysis >> select type of analysis (quick model) >> name analysis >> select the label that you want to ndicate in your data set >> preview >> Create analysis

combine positive feedback count + recommender indicator + new feature

Week2 
- Detecting statistical bias in the training dataset can help you gain insight into how imbalanced the dataset could be. I demonstrated using Data Wrangler, to detect statistical bias in your training data and generate bias reports. I also introduced SageMaker Clarify API, that'll help you perform the bias detection at scale. In the lab exercise this week, you will use the Clarify APIs to generate the bias reports and explore the report in a bit more detail. I further introduced feature importance and demonstrated using Data Wrangler how to generate the feature importance report on your training dataset. The generated report give you an insight into how the individual features of the training dataset are contributing to the final model. I hope you enjoyed the Week 2 content, and you're ready and excited to explore the lab assignment.










### Week3:
- Discuss some of the challenges, or repetitive tasks, that you can often run into when building machine learning models. learn about some of the benefits of using AutoML
- After this week's course, you'll be able to describe the concept of AutoML as well as be able to describe how you can train a text classifier using AutoML.
- you will learn about how Amazon Sagemaker uniquely implements AutoML capabilities through Sagemaker autopilot. For this, I'll walk you through the steps on how you can use Sagemaker autopilot to train a text classifier. So let's get started and dive deeper into AutoML.
