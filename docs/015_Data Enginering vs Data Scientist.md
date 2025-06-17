# Data Enginer vs Data Scientist

Now that we know the essentials of the data science, let's go deep into the following roles: data engineer vs data scientist. Despite we already know they are different, the boundaries between them might be blurred, leading to confusion in job descriptions, hiring processes, and tasks definitions. This chapter aims to clarify the differences between them, helping readers can better understand how these roles collaborate and where they diverge.

On one hand, the data scientist focuses on building models to generate predictions and extract insights from existing data to create value for the business. On the other hand, the data engineer is responsible for designing and maintaining the infrastructure that enables data to move efficiently from one place to another and be readily available for analysis. Rather than being overlapping roles, they are best understood as complementary—each one essential in a data science project.

When it comes to technical skills, data engineers tend to have deeper expertise in cloud infrastructure, ETL processes, and pipeline orchestration, with a strong foundation in computer science and software engineering principles. In contrast, data scientists are more focused on mathematics, statistics, and building predictive models, often drawing on knowledge from analytical and scientific disciplines.

In the following table, we can see a comparison between both roles:

| | Data Engineer | Data Scientist |
| ----------- | ----------- | ----------- |
| Main focus | Building and maintain data infrastructure | - Building and maintain predictive models <br>- Analysing data to get insights|
| Responsabilities | - Design data architecture <br>- Develop and manage ETL pipelines <br>- Ensure data quality and availability | - Analyze data <br>- Develop predictive models <br>- Communicate insights | 
| Background | Computer Science<br>Software Engineering | Mathematics<br>Statistics<br>Data Analysis |
| Project phase involved | - Data Collection<br>- Data Cleaning<br>- Model Implementation| - Data Collection<br>- Data Cleaning<br>- EDA<br>- Modelling<br>- Implementation|

## Tools and technologies
Regarding the tools used by each role, we can name the following ones:

### Airflow
Airflow is an open-source platform for developing, scheduling, and monitoring batch-oriented workflows. It is used by data engineers to orchestrate their data pipelines.

In Airflow, workflows are defined using a structure called a DAG, which stands for Directed Acyclic Graph.
A DAG is a model that encapsulates everything needed to execute a workflow. It is essentially a collection of tasks that are connected and executed in a specific order based on their dependencies. The term "directed" means that each task points to the next in a defined flow, and "acyclic" means that there are no loops—a task cannot depend on itself, either directly or indirectly.

Some DAG attributes might include the following ones:

- Schedule: When the workflow should run.

- Tasks: tasks are discrete units of work that are run on workers.

- Task Dependencies: The order and conditions under which tasks execute.

- Callbacks: Actions to take when the entire workflow completes.

For instance, we can see the following DAG:

```
from airflow.decorators import dag, task
from pendulum import datetime
import requests

API='http://numbersapi.com/random/date'

@dag(
    start_date=datetime(2025,6,10),
    schedule='@hourly',
    catchup=False  ##disable the processing of all missed intervals
)

def my_dag():
    @task
    def get_date_information():
        r = requests.get(API,timeout=10)
        return r.text

    get_date_information()

my_dag()
```

This DAG is a very simple example that runs hourly and executes the get_date_information task. In the next picture, we can see the DAG list in Airflow (just one in this case):

![Airflow DAGs](/aispace-chapter/assets/img/015_airflow_dag.png)

If we go into the DAG, we can see its tasks and some other information like the duration of the task execution, the status, the log and so on:
![DAG task](/aispace-chapter/assets/img/015_dag_information.png)

We can add as many tasks as we want in a DAG, set dependencies between them and also change the schedule as we wish.

Airflow is a platform for orchestrating batch workflows that have a clear start and end and run on a schedule. It is not intended for continuously running, event-driven, or streaming workloads.

### Spark
Apache Spark is a multi-language engine for executing data engineering, data science, and machine learning on single-node machines or clusters. It utilizes in-memory caching, and optimized query execution for fast analytic queries against data of any size.

Commonly used by data engineers to process large volumes of data quickly and efficiently but also could be useful for data scientist.

It allows to work with many different languages: Python, SQL, Scala, Java or R and many different sources such as AVRO, CSV, JSON, Parquet, Relational DDBB, No SQL and so on.

Data engineers can use it to build data pipelines to run ETL processes that can be batch or real-time and work with multiples data formats.

```
# 1. Create Spark session
spark = SparkSession.builder \
    .appName("ETL-CustomerOrders") \
    .getOrCreate()

# 2. Extract: Read data from a relational database (e.g., PostgreSQL)
orders_df = spark.read.format("jdbc").options(
    url="jdbc:postgresql://db.example.com:5432/sales",
    dbtable="orders",
    user="my_user",
    password="my_password",
    driver="org.postgresql.Driver"
).load()

# 3. Transform: Clean and enrich the data
# - Convert date field
# - Add year column
# - Flag high-value orders

transformed_df = orders_df \
    .withColumn("order_date", to_date("order_date", "yyyy-MM-dd")) \
    .withColumn("year", year("order_date")) \
    .withColumn("is_high_value", when(col("total_amount") > 1000, 1).otherwise(0)) \
    .filter(col("status") == "completed")

# 4. Load: Write to S3 in Parquet format, partitioned by year
transformed_df.write.mode("overwrite").partitionBy("year") \
    .parquet("s3://my-bucket/clean-data/orders/")

```

Spark also includes MLlib, a library of algorithms to do machine learning on data at scale. The algorithms include the ability to do classification, regression, clustering, collaborative filtering, and pattern mining. 

```
# Every record contains a label and feature vector
df = spark.createDataFrame(data, ["label", "features"])

# Split the data into train/test datasets
train_df, test_df = df.randomSplit([.80, .20], seed=42)

# Set hyperparameters for the algorithm
rf = RandomForestRegressor(numTrees=100)

# Fit the model to the training data
model = rf.fit(train_df)

# Generate predictions on the test dataset.
model.transform(test_df).show()
```

### SQL vs Python
In the world of data, both SQL and Python are essential but they serve different purposes and shine in different scenarios.

Python is a programming language known for its versatility, ease of use, integration and flexibility, used by software programmers and data professionals. It is a favorite for working with data because its easy integration with multiple libraries and flexibility make it easy to adapt to various formats (text, video, audio, Comma Separated Values (CSV), and web) involved with working with data.

Regarding SQL, it is a programming language used to build, store, and retrieve data from data management systems. SQL allows data professionals to retrieve records from databases and generate powerful insights crucial for business decision-making.

In the data world, Python is used for:
- Building data pipelines and ETL processes
- Making Machile Learning, statistics and visualization work

As for SQL, it is commonly used for:
- Querying and aggregating data in databases
- Building dashboards and BI reports

These two tools are very useful in Data Science project and can be complementary to each other. For example, thinking in a project to maintain a data warehouse, we could keep all the code to create and feed the tables in SQL code and use Python for the data pipelines that will run that SQL code.

### ML libraries
Python offers a wide range of libraries that facilitate machine learning tasks. In this last section, we will dive into the most common Python libraries for machine learning:

#### NumPy
For large **multi-dimensional array and matrix processing**, with the help of a large collection of high-level mathematical functions. It is very useful for fundamental scientific computations in Machine Learning. It is particularly useful for linear algebra, Fourier transform, and random number capabilities.

#### Pandas
Very popular for data analysis. Even when it is not directly related to ML, it is very useful **to prepare the datasets before training**. 
Pandas provides high-level data structures and wide variety tools for data analysis. It has many inbuilt methods for grouping, combining and filtering data.

#### Matplotlib
Also not directly related to ML but very useful to identify patterns in the data during the EDA step. It **provides various kinds of graphs and plots** for data visualization, histogram, error charts, bar chats, etc, 

#### Scikit-Learn
Useful and very popular for **classical ML algorithms**, it can also be used for data-mining and data-analysis. Scikit-Learn is designed primarily for prediction analytics. After data is cleaned and processed, it is separated into a training set and a test set. The training set is used to train the model using its algorithm and is then evaluated on how it performs on the test data.

#### TensorFlow
Tensorflow is a framework that involves defining and running computations involving tensors. It can t**rain and run deep neural networks** that can be used to develop several AI applications.

#### PyTorch
PyTorch is a machine learning library based on the Torch library, used for applications such as **computer vision and natural language processing**.

Sources:
[What is Airflow?](https://airflow.apache.org/docs/apache-airflow/stable/index.html#)
[Getting Started with Airflow for Beginners](https://www.youtube.com/watch?v=xUKIL7zsjos)
[What is Apache Spark™?](https://spark.apache.org/)
[Python vs. SQL: A deep dive comparison](https://www.softwareag.com/en_corporate/blog/streamsets/python-vs-sql.html)
[Best Python libraries for Machine Learning](https://www.geeksforgeeks.org/machine-learning/best-python-libraries-for-machine-learning/)