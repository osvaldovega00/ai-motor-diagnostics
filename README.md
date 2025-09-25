# Predictive AI for AC-Motor Diagnostics

**Summary:**

This solution leverages machine learning techniques to classify and predict the type of maintenance required for motors. By providing recommendations on the type of corrective maintenance needed, the system helps avoid unnecessary troubleshooting and misdiagnoses, ultimately reducing downtime and operational disruptions. The development process includes data collection, preprocessing, model training and optimization, deployment, validation, and monitoring to build a predictive system that categorizes maintenance needs based on motor conditions and historical patterns. Importantly, the dataset used here serves as a proof of concept and demonstration only; it does not include the data or models deployed in the final project. The outcome is a smart maintenance recommendation engine that integrates seamlessly into existing workflows, enabling organizations to optimize maintenance schedules, allocate resources efficiently, and reduce unexpected motor failures.


**Dataset:**

The dataset consists of 10,000 data points stored as rows with 8 features, 1 target variable, and 1 column indicating failure type, providing a robust sample size for initial model development and evaluation. This dataset was used solely to develop a proof of concept and does not contain the data used in the final project nor the final models. It serves for demonstration purposes only. The predictive maintenance model’s performance will be assessed using accuracy, precision, recall, and F1 score to provide a comprehensive evaluation of its ability to identify equipment maintenance needs.

Dataset Link: https://archive.ics.uci.edu/ml/datasets/AI4I+2020+Predictive+Maintenance+Dataset 

**Project Structure:**


* Development
  * dataset
  * scripts → converted notebooks and test `.py` scripts  
  * streamlit_app → front end designed for local development environment  

* Deployment  
  * ai-motor-container → docker container with inference models and supporting files  
  * ai-motor-ui-container → docker container containing front-end assets

**Pre-requisites:**
*   pandas V 2.2.3
*   scikit-learn V 1.6.1
*   joblib V 1.5.0
*   gunicorn V 23.0.0
*   imbalanced-learn V 0.13.0
*   flask V 3.1.0
*   streamlit V 1.45.1
*   requests V 2.32.3
*   google-auth V 2.40.3

**Model Details:**
XGBoost model predicting type of errors based on sensor data related to AC-Motors.

**App Preview:**
![Screenshot 2025-06-22 215558](https://github.com/user-attachments/assets/513a136c-c336-4638-8f3e-881960f682e6)


**Deployment Architecture:**
![image](https://github.com/user-attachments/assets/e3a991ff-cb47-4e0c-8074-0e9750449759)

**Request-Response Logging in Google BigQuery:**
![image](https://github.com/user-attachments/assets/7e432c8c-2597-4b91-a845-98ea8862c4bb)

**Data Drift Monitoring in Google Vertex AI:**

Google Vertex AI monitors data drift on the project endpoint and runs a report every 24 hours (arbitrarily chosen). If the drift value exceed threshold of 0.3, an alert is triggered and sent to email.
![image](https://github.com/user-attachments/assets/31adaef7-3c05-4078-828b-cf6ae12d3a89)
