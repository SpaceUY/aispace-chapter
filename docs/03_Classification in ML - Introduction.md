---
title: Types ML
layout: default
nav_order: 2
---

#### 2. **Types of Machine Learning**

Machine Learning can be broadly categorized into three main types:  

1. **Supervised Learning**  
2. **Unsupervised Learning**  
3. **Reinforcement Learning**  

Additionally, **Semi-supervised Learning** and **Self-supervised Learning** serve as bridges between the traditional paradigms, addressing scenarios with limited labeled data.

This section explains each type, provides real-world examples, includes mathematical insights, and suggests visual figures for clarity.

---

### **1. Supervised Learning**

In **Supervised Learning**, the model learns from **labeled data** where the input \( X \) is paired with the desired output \( Y \). The objective is to approximate a mapping function \( f: X \to Y \).  

#### **Mathematical Foundation**

Given a dataset \( D = \{(x_1, y_1), (x_2, y_2), \dots, (x_n, y_n)\} \):  

- The goal is to minimize a **loss function** \( L(y, \hat{y}) \), where \( \hat{y} = f(x; \theta) \).  
- For **regression**, the Mean Squared Error (MSE) is commonly used:  

\[
L = \frac{1}{n} \sum_{i=1}^n (y_i - f(x_i; \theta))^2
\]  

- For **classification**, the Cross-Entropy Loss is used:  

\[
L = - \frac{1}{n} \sum_{i=1}^n \left[ y_i \log(\hat{y}_i) + (1 - y_i) \log(1 - \hat{y}_i) \right]
\]

---

#### **Practical Examples**  

| **Application**           | **Use Case**                          | **Algorithm**             |  
|---------------------------|---------------------------------------|---------------------------|  
| **Finance**               | Fraud detection in transactions      | Logistic Regression       |  
| **Healthcare**            | Disease diagnosis from medical scans | Support Vector Machines   |  
| **Marketing**             | Customer churn prediction            | Random Forest             |  

---

#### **Visual Suggestions**  

1. **Supervised Learning Process**:  
   - Visual: Diagram showing labeled data flowing into a model, resulting in predictions with ground-truth comparisons.  
   - Example: Predicting house prices with input features (area, rooms) and labeled outputs (price).  

   **Placeholder**:  
   ![Supervised Learning](https://upload.wikimedia.org/wikipedia/commons/thumb/3/3a/Linear_regression.svg/700px-Linear_regression.svg.png)  

---

### **2. Unsupervised Learning**

In **Unsupervised Learning**, the model works with **unlabeled data** and aims to uncover patterns, groupings, or structures within the data.  

#### **Key Methods**  

- **Clustering**: Grouping similar data points into clusters.  
   - *Example*: Customer segmentation using K-Means.  
- **Dimensionality Reduction**: Reducing data dimensions while retaining essential features.  
   - *Example*: Principal Component Analysis (PCA) for visualizing high-dimensional data.

#### **Mathematical Foundation**

Clustering (e.g., **K-Means**) minimizes the distance between data points and cluster centroids:  

\[
J = \sum_{i=1}^n \min_{\mu_k} \|x_i - \mu_k\|^2
\]

Where:  
- \( x_i \): Data points.  
- \( \mu_k \): Centroids of clusters.  

---

#### **Practical Examples**  

| **Application**           | **Use Case**                          | **Algorithm**             |  
|---------------------------|---------------------------------------|---------------------------|  
| **E-commerce**            | Customer segmentation                | K-Means Clustering        |  
| **Image Processing**      | Anomaly detection in images          | Autoencoders              |  
| **Finance**               | Detecting abnormal patterns          | DBSCAN                    |  

---

#### **Visual Example**  

1. **Clustering Illustration**:  
   - Scatter plot with distinct clusters labeled by color.  

   ![Unsupervised Clustering](https://upload.wikimedia.org/wikipedia/commons/e/ea/K-means_convergence.gif)  

---

### **3. Reinforcement Learning (RL)**  

**Reinforcement Learning** involves an **agent** interacting with an environment to take actions \( a \) in order to maximize cumulative rewards \( R \). It learns through trial and error.  

---

#### **Mathematical Foundation**  

Modeled as a **Markov Decision Process (MDP)**:  
- \( S \): States.  
- \( A \): Actions.  
- \( R \): Rewards.  
- \( \gamma \): Discount factor.  

The goal is to maximize expected cumulative reward:  

\[
G_t = \mathbb{E} \left[ \sum_{k=0}^\infty \gamma^k R_{t+k+1} \right]
\]

---

#### **Practical Examples**  

| **Application**           | **Use Case**                          | **Algorithm**             |  
|---------------------------|---------------------------------------|---------------------------|  
| **Robotics**              | Robot learning to walk               | Q-Learning                |  
| **Gaming**                | AI mastering games like Chess/Go     | Deep Q-Networks (DQN)     |  
| **Autonomous Vehicles**   | Learning optimal driving strategies  | Policy Gradient Methods   |  

---

#### **Visual Example**  

1. **Reinforcement Learning Flow**:  
 - Diagram showing an agent interacting with the environment, taking actions, and receiving rewards. This is applied for example in a robot navigating a maze.  

   ![Reinforcement Learning](https://upload.wikimedia.org/wikipedia/commons/thumb/d/da/Markov_diagram_v2.svg/2880px-Markov_diagram_v2.svg.png)  

---

### **4. Semi-supervised Learning**  

**Semi-supervised Learning** is a hybrid approach that combines **a small amount of labeled data** with **a large amount of unlabeled data** to train models.  

- **Use Case**: Labeling millions of images when only a few are annotated.  
- **Method**: Use labeled data to bootstrap predictions for unlabeled data.  

---

### **5. Self-supervised Learning**  

**Self-supervised Learning** generates **pseudo-labels** from the data itself, often used for pre-training deep learning models.  

- **Use Case**: Training GPT models to predict the next word in a sentence.  

**Visual Idea**: Example showing a language model predicting masked tokens in a sentence:  

\[
\text{Input}: \text{The cat sat on the [MASK].}  
\text{Prediction}: \text{"mat"}
\]

---

### **Summary Table**  

| **Type**                  | **Data Type**            | **Task**                 | **Example**                             |  
|---------------------------|--------------------------|--------------------------|-----------------------------------------|  
| **Supervised Learning**   | Labeled Data             | Regression, Classification | Predicting house prices                 |  
| **Unsupervised Learning** | Unlabeled Data           | Clustering, PCA          | Customer segmentation                   |  
| **Reinforcement Learning**| Interaction with Environment | Maximize rewards        | Robot navigating a maze                 |  
| **Semi-supervised**       | Small labeled + unlabeled | Classification           | Image classification with few labels    |  
| **Self-supervised**       | Pseudo-labels from data  | Pre-training             | GPT language model training             |  

---

### **Conclusion**

Understanding the types of Machine Learning is crucial to choosing the right approach for any problem. Supervised Learning excels with labeled data, Unsupervised Learning discovers hidden patterns, and Reinforcement Learning teaches agents to make optimal decisions.  

Semi-supervised and Self-supervised Learning address modern challenges where labeled data is scarce, expanding ML's capabilities.

---

### **References**  

1. Shalev-Shwartz, S., & Ben-David, S. (2014). *Understanding Machine Learning: From Theory to Algorithms*. Cambridge University Press.  
2. Sutton, R. S., & Barto, A. G. (2018). *Reinforcement Learning: An Introduction*. MIT Press.  
3. Stanford CS229: [https://cs229.stanford.edu](https://cs229.stanford.edu)  
4. Self-supervised Learning Overview: [https://arxiv.org](https://arxiv.org)  

---
