# Task 4: MLOps Scenario
• Consider a machine learning model that needs to be trained and deployed in a production environment.  
• Describe the steps you would take to automate the model training and deployment process.  
• Explain how you would version control the model artifacts and track the model's lineage.  
• Discuss the challenges and best practices for monitoring and managing the deployed model in production.


## MLOps Scenario   
 
![mlops-phasen](https://github.com/jaekimandy/MLOps_Scenario/assets/99704906/39260e52-55eb-4a1d-9f2e-a3e1fe823a70)
    

## Ⅰ. Automated Model Training and Deployment Process

<table>
  <tr>
    <th>Stage </th>
    <th>Stage Specifics</th>
    <th>Tools</th>
    <th>Description</th>
  </tr>
  <tr>
    <td rowspan="4">A. Data Preprocessing</td>
    <td>1. Data Collection</td>
    <td>Apache Nifi <br> Airflow <br> Luigi</td>
    <td>Automate the collection of raw data from various sources (databases, APIs, etc.) using scheduled ETL (Extract, Transform, Load) jobs.
</td>
  </tr>
  <tr>
    <td>2. Data Cleaning</td>
    <td>Spark<br>Pandas</be></td>
    <td>Implement automated data cleaning scripts to handle missing values, outliers, and inconsistencies<be>
      <a href="https://reintech.io/blog/building-scalable-etl-pipelines-apache-spark">Spark Example</a>
    </td>
  </tr>
  <tr>
    <td>3. Feature Engineering</td>
    <td>FeatureTools<br> Scikit-learn<br> Pandas</td>
    <td>Automate feature extraction and transformation processes using tools like FeatureTools or custom scripts</td>
  </tr>
  <tr>
    <td>4. Data Splitting</td>
    <td>Scikit-learn<br> Pandas<br> Dask</td>
    <td>Automate the process of splitting data into training, validation, and test sets</td>
  </tr>
  <tr>
    <td rowspan="3">B. Model Training</td>
    <td>1. Training Pipeline</td>
    <td>Apache Airflow<br> Kubeflow Pipelines<br> Prefect</td>
    <td>Use orchestration tools to create a training pipeline that can be triggered automatically</td>
  </tr>
  <tr>
    <td>2. Hyperparameter Tuning</td>
    <td>Optuna<br> Hyperopt<br> Ray Tune</td>
    <td> Integrate hyperparameter optimization tools to automate the search for the best model parameters</td>
  </tr>
  <tr>
    <td>3. Model Training</td>
    <td>TensorFlow<br> PyTorch<br>  Scikit-learn</td>
    <td>Train the model using scalable computing resources, such as those provided by cloud platforms or on-premise clusters</td>
  </tr>
  <tr>
    <td rowspan="2">C. Model Evaluation</td>
    <td>1. Evaluation Metrics</td>
    <td>Scikit-learn<br> TensorFlow<br>  PyTorch</td>
    <td>Automate the evaluation of the model using predefined metrics (accuracy, precision, recall, F1 score, etc.)</td>
  </tr>
  <tr>
    <td>2. Validation</td>
    <td>Scikit-learn<br>  Pandas</td>
    <td> Automatically validate the model against a hold-out validation set to ensure it meets performance requirements</td>
  </tr>
  <tr>
    <td rowspan="3">D. Deployment</td>
    <td>1. Containerization</td>
    <td>Docker</td>
    <td>Containerize the model and its dependencies</td>
  </tr>
  <tr>
    <td>2. Model Serving</td>
    <td>Kubernetes</td>
    <td> Integrate hyperparameter optimization tools to automate the search for the best model parameters 
    </td>
  </tr>
  <tr>
    <td>3. API Creation</td>
    <td>Flask<br> FastAPI<br>  Django</td>
    <td>Expose the model as an API endpoint for consumption by other applications<br>
     <a href="https://medium.com/@shanakachathuranga/machine-learning-model-serving-with-django-rest-framework-397f495a8a38"> Exposing Model</a> </td>
  </tr>
  <tr>
</table>  


## Nifi
![nifi](https://github.com/jaekimandy/MLOps_Scenario/assets/99704906/f81db1a8-632d-4ecb-81f2-775c03692d08)


## Ⅱ. Version Control and Lineage Tracking

<table>
  <tr>
    <th>Stage </th>
    <th>Stage Specifics</th>
    <th>Tools</th>
    <th>Description</th>
  </tr>
  <tr>
    <td rowspan="3">A. Version Control</td>
    <td>1. Code and Configurations</td>
    <td>Git </td>
    <td>Use Git for version controlling the codebase, configuration files, and training scripts.</td>
</td>
  </tr>
  <tr>
    <td>2. Model Artifacts</td>
    <td>MLflow<br> DVC </td>
    <td>Use a model registry or artifact repository to store and version control trained model artifacts</td>
  </tr>
  <tr>
    <td>3. Experiment Tracking</td>
    <td>MLflow Tracking<br> TensorBoard</td>
    <td>Log experiments, capturing metadata such as hyperparameters, metrics, and data versions</td>
  </tr>
  <tr>
    <td rowspan="3">B. Lineage Tracking</td>
    <td>1. Data Lineage</td>
    <td>Apache Atlas<br> Amundsen</td>
    <td>Data lineage is the story behind the data. It tracks the data from its creation point to the points of consumption. This pipeline of dataflow involves input and output points, transformation and modeling processes the data has undergone, record analysis, visualizations, and several other processes which are constantly tracked and updated. The objective of data lineage is to observe the entire lifecycle of data such that the pipeline can be upgraded and leveraged for optimal performance.</td>
  </tr>
  <tr>
    <td>2. Model Lineage</td>
    <td>MLflow<br> DVC</td>
    <td> Ensure each model artifact is associated with its training data, parameters, code version, and environment using the model registry.</td>
  </tr>
  <tr>
    <td>3. Reproducibility</td>
    <td>Detailed logs<br> configuration files</td>
    <td> Store detailed logs and configuration files to reproduce any training run or model version</td>
  </tr>
</table>

**Registered Model in MLFlow**
![image](https://github.com/jaekimandy/MLOps_Scenario/assets/99704906/77a78d1f-bf46-4441-a274-db491d3a05ec)
![image](https://github.com/jaekimandy/MLOps_Scenario/assets/99704906/8532ac30-653c-4e02-a366-dde4db39212e)
![image](https://github.com/jaekimandy/MLOps_Scenario/assets/99704906/6e577ae7-3ea0-4446-8238-282649c82852)





## Ⅲ. Monitoring and Managing the Deployed Model

<table>
  <tr>
    <th>Stage </th>
    <th>Stage Specifics</th>
    <th>Tools</th>
    <th>Description</th>
  </tr>
  <tr>
    <td rowspan="3">A. Monitoring</td>
    <td>1. Performance Monitoring</td>
    <td>Prometheus <br> Grafana </td>
    <td> Continuously monitor model performance in production, tracking metrics such as response time, throughput, and error rates</td>
</td>
  </tr>
  <tr>
    <td>2. Drift Detection</td>
    <td>Evidently AI<br> Alibi Detect</td>
    <td> Implement drift detection mechanisms to monitor changes in data distribution or model performance over time. Data drift is a change in the statistical properties and characteristics of the input data. It occurs when a machine learning model is in production, as the data it encounters deviates from the data the model was initially trained on or earlier production data. This shift in input data distribution can lead to a decline in the model's performance. The reason is, when you create a machine learning model, you can expect it to perform well on data similar to the data used to train it. However, it might struggle to make accurate predictions or decisions if the data keeps changing and the model cannot generalize beyond what it has seen in training. In simple terms, data drift is a change in the model inputs the model is not trained to handle. Detecting and addressing data drift is vital to maintaining ML model reliability in dynamic settings.</td>
  </tr>
  <tr>
    <td>3. Alerting</td>
    <td>Prometheus Alertmanager<br> PagerDuty<br> Slack Integrations<br> TensorBoard</td>
    <td>Set up alerting systems to notify relevant stakeholders when performance metrics fall below certain thresholds</td>
  </tr>
  <tr>
    <td rowspan="3">B. Management</td>
    <td>1. Automated Retraining</td>
    <td>Apache Airflow <br> Kubeflow Pipeline </td>
    <td> Implement pipelines to automatically retrain the model when significant performance degradation or drift is detected. Model retraining refers to updating a deployed machine learning model with new data. This can be done manually, or the process can be automated as part of the MLOps practices. Monitoring and automatically retraining an ML model is referred to as Continuous Training (CT) in MLOps. Model retraining enables the model in production to make the most accurate predictions with the most up-to-date data. 
Model retraining does not change the parameters and variables used in the model. It adapts the model to the current data so that the existing parameters give healthier and up-to-date outputs. This enables businesses to efficiently monitor and continuously retrain their models for the most accurate predictions.
</td>
  </tr>
  <tr>
    <td>2. A/B Testing</td>
    <td>Kubernetes</td>
    <td>  Use A/B testing or canary deployments to safely test new model versions in production before full rollout<be>
      <a href="https://mlflow.org/docs/latest/deployment/deploy-model-to-kubernetes/tutorial.html">Kuberbets deployment Reference document</a>  
    </td>
  </tr>
  <tr>
    <td>3. Rollback Mechanism</td>
    <td>Kubernetes</td>    
    <td> Ensure a robust rollback mechanism is in place to revert to a previous model version in case of issues with the new deployment</td>
  </tr>
</table>

**Drift Detection  **
     
![image](https://github.com/jaekimandy/MLOps_Scenario/assets/99704906/0ca63840-2eaa-499a-8a8f-a32fdedff55e)   


## Ⅳ. Challenges and Best Practices


**Challenges**   

**Data Quality**:   Ensuring consistent data quality and dealing with missing or noisy data.   
**Scalability**:   Scaling the training and serving infrastructure to handle large datasets and high traffic.   
Complexity:   Managing the complexity of the pipeline and ensuring all components work seamlessly together.   
Regulatory Compliance:   Ensuring the model and its data comply with relevant regulations and industry standards.  
    
**Best Practices**   
**Modular Pipelines**:    Design modular and reusable components for the training and deployment pipelines.   
**Continuous Integration/Continuous Deployment (CI/CD)**:   Implement CI/CD pipelines for model training and deployment to ensure seamless integration and rapid iteration.  
**Security**:   Secure data, models, and APIs using encryption, authentication, and authorization mechanisms.   
**Documentation**:   Maintain comprehensive documentation for the entire pipeline, including setup instructions, configurations, and troubleshooting guides.   
**Stakeholder Collaboration**:   Foster collaboration between data scientists, engineers, and operations teams to ensure smooth deployment and maintenance of models.   
