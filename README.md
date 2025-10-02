# Customer Segmentation using K-Means Clustering

This project performs customer segmentation on a dataset from a mall. The goal is to group customers into distinct clusters based on their annual income and spending score. This is an unsupervised learning problem, and the K-Means clustering algorithm is used to achieve this segmentation.

## Dataset

The dataset used is `Mall_Customers.csv`, which contains the following columns:

  - `CustomerID`: Unique ID assigned to each customer.
  - `Gender`: Gender of the customer.
  - `Age`: Age of the customer.
  - `Annual Income (k$)`: Annual income of the customer in thousands of dollars.
  - `Spending Score (1-100)`: A score assigned by the mall based on customer behavior and spending nature.

For this clustering analysis, we will focus on the `Annual Income (k$)` and `Spending Score (1-100)` features.

## Methodology

The project follows these steps:

1.  **Data Loading and Exploration**: The necessary libraries are imported, and the dataset is loaded into a pandas DataFrame. Initial exploration is done to check for missing values and understand the data types.

2.  **Feature Selection**: `Annual Income` and `Spending Score` are selected as the features for clustering.

3.  **Finding the Optimal Number of Clusters**: The **Elbow Method** is used to determine the optimal number of clusters ($k$) for the K-Means algorithm.

      - We calculate the Within-Cluster Sum of Squares (WCSS) for a range of cluster numbers (1 to 10).
      - WCSS is the sum of the squared distance between each point and the centroid in a cluster.
      - By plotting WCSS against the number of clusters, we look for an "elbow" point, which indicates the optimal $k$.
      - The elbow plot suggests that the optimal number of clusters is **5**.

4.  **Model Training**: A K-Means model is trained on the data with $k=5$. The model assigns each data point to one of the five clusters.

5.  **Visualization**: The five customer clusters are visualized using a scatter plot, with each cluster represented by a different color. The centroids of each cluster are also plotted.

## Results: Customer Segments

The analysis identifies five distinct customer segments:

  - **Cluster 1 (Green)**: Low Income, Low Spending Score. These are careful customers who earn less and spend less.
  - **Cluster 2 (Blue)**: High Income, High Spending Score. This is the **target** group. They earn high and spend high, making them ideal customers.
  - **Cluster 3 (Yellow)**: Low Income, High Spending Score. These customers spend a lot despite having a low income. They could be considered careless or high-risk.
  - **Cluster 4 (Red)**: High Income, Low Spending Score. These customers earn a high income but are careful with their spending.
  - **Cluster 5 (Violet)**: Average Income, Average Spending Score. This group represents the standard or average customers.

These insights can help the mall in formulating targeted marketing strategies for each segment.

## Libraries Used

  - `numpy`
  - `pandas`
  - `matplotlib`
  - `seaborn`
  - `scikit-learn`

## How to Run

1.  Clone the repository:
    ```bash
    git clone <repository-url>
    ```
2.  Navigate to the project directory:
    ```bash
    cd <project-directory>
    ```
3.  Install the required libraries:
    ```bash
    pip install numpy pandas matplotlib seaborn scikit-learn
    ```
4.  Ensure the `Mall_Customers.csv` file is in the same directory as the notebook.
5.  Launch Jupyter Notebook and open `Customer_Segmentation.ipynb`.
    ```bash
    jupyter notebook Customer_Segmentation.ipynb
    ```
6.  Run the cells in the notebook to execute the analysis.
