---
title: Data Science - Landscape
layout: default
nav_order: 14
---
# Data Science - Landscape

Most people believe that data science is solely about developing predictive models using machine learning, overlooking the many other tasks required to make those predictions possible. The goal of this chapter is to present the main roles within this branch of computer science and explain their main responsabilities.

## What is Data Science?
With the rapid proliferation of devices that automatically collect and store information, along with the growing use of online systems and payment portals in areas like e-commerce, finance, and beyond, data science has become one of the important fields across industries. But, what is Data Science?

Data science is the study of data to get meaningful insights for business. It is a multidisciplinary approach that combines principles and practices from the fields of mathematics, statistics, artificial intelligence, and computer engineering to analyze large amounts of data. It is used to make decisions, predict outcomes, and solve problems based on data.

Within Data Science we can find several roles, among the most common ones are:
- Data Scientist
- Data Engineer
- Data Analyst

In the following sections, we will go deep into each of those roles, their main responsabilities, tasks and required qualifications.

## Data Science Roles

### Data Scientist
Probably the most obvious key role in a data science team. A data scientist tries to understand certains phenomena through the analysis of modeling of complex data.

Typical responsabilities:
- Develop statistical models, machine learning algorithms, and predictive analytics solutions to address business challenges;
- Analyze large amounts of complex data to extract insights and drive decision-making;
- Design experiments to test hypotheses and measure the effectiveness of solutions;
- Use data visualization tools to communicate insights and findings to stakeholders.

Required qualifications:
- Knowledge in maths, statistics, computer science, data science, or related quantitative field;
- Strong programming skills in Python or R;
- Strong SQL skills and understanding of databases;
- Strong experience with machine learning algorithms;
- Familiarity with data visualization tools such as Tableau, Power BI, or matplotlib;
- Ability to work with complex and unstructured data.

Tools:
- Specific data scientist Python or R libraries to manipulate data, create predictive models and make statistical analysis;
- Visualization tools to analyse and present the data in a more proper way such as Matplotlib (python library) or Tableau.


### Data Engineer
Responsible for the collection, storage, and processing of data. They design, build, and maintain the infrastructure that enables the data science team to work with large amounts of data. This includes databases, data pipelines, and data warehousing solutions. The data engineer ensures that data is available when and where it is needed, and that it is of high quality.

Typical responsabilities:
- Design, build, and maintain data pipelines to move and transform data from various sources into a target location such as a data warehouse or data lake;
- Develop and maintain the infrastructure required to support data science initiatives, including data warehousing, ETL or ELT tools, and data integration solutions;
- Ensure data quality, accuracy, and consistency across multiple data sources;
- Work with data scientists, data analysts, and other stakeholders to understand data requirements and provide support for data-driven decision-making.

Typical qualifications:
- Knowledge in computer science, data science, or a related field;
- Strong programming skills in one or more languages such as Python, Java, or Scala;
- Strong experience with SQL, NoSQL, and data warehousing technologies such as Redshift, Snowflake, or BigQuery;
- Experience with ETL tools such as Apache Airflow, AWS Glue, or Azure Data Factory;
- Familiarity with distributed computing frameworks such as Hadoop, Spark, or Flink;
- Knowledge of data modeling, data integration, and data quality concepts.

Tools:
- To create ETL data pipelines:
    * Programming languages like Python or Java
    * Spark to create pipelines that process huge amounts of data
    * ETL tools that use flowcharts such as Azure Data Factory
- Pipeline orchestrator like Airflow to schedule and monitor data pipelines;
- Data warehouse tools such as BigQuery to maintain the data warehouse

### Data Analyst
Responsible for collecting, processing, and performing statistical analyses on large sets of data. They use various analytical tools and techniques to extract meaningful insights from data and communicate those insights to decision-makers. They are focused on reporting on the current state as opposed to predictive analytics.

Typical responsabilities:
- Collect and preprocess data from multiple sources to ensure data quality, accuracy, and consistency;
- Analyze and interpret complex data to identify patterns and trends, and to provide insights that support business decision-making;
- Develop dashboards and reports using data visualization tools to communicate insights and findings to stakeholders;
- Collaborate with data scientists and data engineers to collect and preprocess data, and build and maintain data pipelines.

Typical qualifications:
- Knowledge in in computer science, business analytics, or a related field.
- Strong proficiency in SQL and data visualization tools such as Tableau, Power BI, or QlikView.
- Experience with statistical analysis and A/B testing methodologies.
- Familiarity with data modeling and data preprocessing techniques.
- Ability to work with complex and unstructured data.

Tools:
- Visualization tools such as Tableau, PowerBI and Looker
- Tools to analyse the data such as BigQuery and Excel 

------------
All of these roles need to have strong analytical and problem-solving skills as well as strong communication skills and ability to work collaboratively with cross-functional teams. These roles usually work together to achieve the goals.
The following table highlights the main differences and responsibilities among three core roles within a data science team:

| | Data Scientist | Data Engineer | Data Analyst |
| ----------- | ----------- | ----------- | ----------- |
| Key word | Prediction | Infrastructure | Reporting
| Objective | Make predictions to answer key business questions | Build and maintain the data infrastructure to make it available in a clean way | Report the current status of the company |
| Knowledge | Statistics, math, programming skills (Python or R), SQL and predictive models | Programming skills (Java, Python), SQL, Cloud computing, ETL tools | SQL, Excel and data visualization tools (i.e. Tableau)|

## Data Science Workflows
In a typical data science project, the workflow starts with defining **the business problem**. For instance, imagine a clothing e-commerce that notices a high rate of shopping cart abandonment.The goal is to understand why users abandon their carts and how to reduce the rate. At this stage, a Data Scientist plays a key role by defining the problem in analytical terms and proposing a predictive modeling approach, while a Data Analyst helps clarify the business context and relevant performance indicators.

The next step is **the data collection**. Data is pulled from various sources, such as website clickstreams, cart activity logs, customer information, and session timestamps. This phase involves the Data Engineer, who builds robust data pipelines and ensures data is accessible, reliable, and scalable. Meanwhile, the Data Scientist defines what data is needed, and the Data Analyst may help identify specific business metrics to capture.

Once the data is collected, **the cleaning and preparation process** starts. This includes handling missing values, encoding categorical variables, and creating meaningful features like session duration or whether a user is new or returning. Data Engineers often clean data and optimize data storage, while Data Scientists perform advanced preprocessing and feature engineering. Data Analysts might support this phase through exploratory SQL queries or preparing subsets of the data.

**Exploratory Data Analysis (EDA)** follows. This phase is crucial for finding out trends and patterns. Analysts might discover that most abandoned carts include discounted items, or that abandonment peaks during late-night hours. Data Analysts take the lead in creating visualizations and descriptive statistics, while Data Scientists explore deeper correlations and test hypotheses that guide the modeling process.

The core of the project is **building a predictive model**. Using machine learning algorithms, the Data Scientist trains a model to predict the likelihood of a user abandoning their cart. Then the model is evaluated using some metrics. Data Engineers may assist by scaling up training processes or preparing infrastructure for model deployment.

Once the model is performing well, the team interprets the results. Suppose the model reveals that high shipping costs or slow website performance are strong predictors of abandonment. The team can recommend interventions such as offering discounts, streamlining the checkout process, or sending reminder emails. Here, Data Scientists explain the model outputs, and Data Analysts help translate insights into business actions. This is normally known as **the storytelling** step.

Besides the storytelling, it is important to **implement the model** into production on the store's website. Doing that, if a customer shows signs of abandoning a cart, the system might trigger a discount pop-up or some strategy to attract him. Data Engineers handle integration and deployment, ensuring performance and scalability, while Data Scientists monitor the model’s accuracy post-deployment.

Finally, the **continuous evaluation** step ensures the model remains effective. Over time, user behavior may change, and the model needs retraining. Data Scientists take charge of model maintenance and re-training, Data Analysts track KPIs and evaluate success, and Data Engineers adapt data infrastructure to new needs.

![Data Science Workflow](/aispace-chapter/assets/img/ds_workflow.png)

It is important to note that the stages of a data science project are not strictly sequential. Reaching one stage may require going back to a previous one. It is more of an iterative process than a linear one.

Additionally, depending on the project, one role may play a more prominent part than others. In the example provided, data scientists and data engineers take on a more significant role. However, there are other types of projects where the data analyst becomes more central — for instance, in tasks like customer segmentation or analyzing customer acquisition cost (CPA) across different time periods.

Sources:
[What is Data Science? - AWS](https://aws.amazon.com/what-is/data-science/)

[What is Data Science? - IBM](https://www.ibm.com/think/topics/data-science)

[Data Science Roles – A Definitive Guide](https://www.datascience-pm.com/data-science-roles/)