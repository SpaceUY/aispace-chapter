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

## Tools and technologies [WIP]
> (Airflow, Spark, SQL vs Python, ML libraries).

Regarding the tools used by each role, we can name the following:

### Airflow
Airflow is an open-source platform for developing, scheduling, and monitoring batch-oriented workflows. It is used by data engineers to orchestrate their data pipelines.

In Airflow, workflows are defined using a structure called a DAG, which stands for Directed Acyclic Graph.
A DAG is a model that encapsulates everything needed to execute a workflow. It is essentially a collection of tasks that are connected and executed in a specific order based on their dependencies. The term "directed" means that each task points to the next in a defined flow, and "acyclic" means that there are no loops—a task cannot depend on itself, either directly or indirectly.

Some DAG attributes might include the following ones:

- Schedule: When the workflow should run.

- Tasks: tasks are discrete units of work that are run on workers.

- Task Dependencies: The order and conditions under which tasks execute.

- Callbacks: Actions to take when the entire workflow completes.


Sources:
[What is Airflow?](https://airflow.apache.org/docs/apache-airflow/stable/index.html#)
