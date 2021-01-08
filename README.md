# Project-Operationalizing-Machine-Learning-a-Model
# overview
I will continue to work with the Bank Marketing dataset. I will use Azure to configure a cloud-based Machine Learning Production Model, deploy the best model to web service, and consume it, and will create, publish, and interact with a pipeline.
# Architectural Diagram
<img src="https://github.com/ohikhatemenG/Project-Operationalizing-Machine-Learning-a-Model/blob/main/Architectual%20Diagram.png"/>
I started with Authentication after registered the dataset and then ran Auto ML Model or experiment to get the best model and after that I Deploy the Best Model to the Web service through Azure Container Instance(ACI). The next action I took was to apply the Enable Logging(Enable Application Insight) to review important information about the service when consuming the model at Endpoint section. The next steps were to Create and Publish, and interact with a pipeline, finally establishing a Documentation for the people to read and learn.

# Key Steps

# Authentication
The first stage of the Machine Learning Operations is Authentication, and they are three authentication types.

(1). Key based: Which involved Azure Kubernetes Service (AKS) enable and Azure Container Instances Service(ACI) disable both by default.

(2). Token based: Which involved only Azure Kubernetes Service disable by default.

(3). Interactive based: It is use for local  deployment and experimentation

# Registered Datasets

I navigated to the left of the Virtual Machine (VM) and I clicked on Dataset section and selected Registered datasets, clicked create and selected web file for storage of dataset
<img src="https://github.com/ohikhatemenG/Project-Operationalizing-Machine-Learning-a-Model/blob/main/Dataset1.png"/>

# Auto ML Model

Navigated to the AutoML section on the workspace and created a new Automated ML run. I created and configured a new computer cluster with Standard DS12_V2, and selected
1 as the number of the minimum nodes and 5 as the number of the maximum nodes. And I selected and uploaded the existing Bank-marketing Dataset.Also I selected y as the target column for the model.I configured the AutoML run using the newly created cluster named bank-cluster and successfully ran the AutoML experiment named Bankexperiement. Once the AutoML run was completed.The best model I got was voting ensemble model with accuracy 91.6%.
<img src="https://github.com/ohikhatemenG/Project-Operationalizing-Machine-Learning-a-Model/blob/main/AutoML%202.png"/>
Automl run and the best model results obtained
<img src="https://github.com/ohikhatemenG/Project-Operationalizing-Machine-Learning-a-Model/blob/main/AutoML%201.png"/>
Automl run shown completed

# Deploy the Best Model

Since I have the best model ready for deployment, I clicked on deploy and created a model named bank-mk-deploy, and selected Azure Container Instances (ACI) and enabled 'Authentication' and run. And after the completion of deployment is successful, I verified the deployment of the model in order to know the "deploy status" was shown as Healthy, which will create an endpoint
<img src="https://github.com/ohikhatemenG/Project-Operationalizing-Machine-Learning-a-Model/blob/main/Deploy%20healthy.png"/>
Deploy the best model and the deployment status shown Healthy means it's was successful

# Enable Logging in the Application Insight

Once the model is deployed successfully I took the next steps to engage in Enable Application Insights through modifications of the logs script that enable application insights=True and add the experiment name of the deploy model, and execute the logs script. After the completed run and checked the endpoint section and found that the Application Insight Enabled is equal to fail request, server response time, server request and availability.
<img src="https://github.com/ohikhatemenG/Project-Operationalizing-Machine-Learning-a-Model/blob/main/Enable%20logging%203.png"/>
<img src="https://github.com/ohikhatemenG/Project-Operationalizing-Machine-Learning-a-Model/blob/main/Enable%20logging%202.png"/>
<img src="https://github.com/ohikhatemenG/Project-Operationalizing-Machine-Learning-a-Model/blob/main/Enable%20logging%204.png">
Run Enable Application Insights on python terminal and the above results were accomplished

# Consume Model Endpoints (Swagger Documentation)

Swagger is a tool to help build, document and consume RESTful web services in Azure. Once the model is deployed, I was able to get a swagger.json file from the endpoint which I downloaded and placed it in a folder containing swagger file serve.py and swagger.sh. I wanted to create a local web server because of that I run serve.py and swagger.sh on a terminal.And replaced the swagger url with a local host url to achieve the below outcome.
<img src="https://github.com/ohikhatemenG/Project-Operationalizing-Machine-Learning-a-Model/blob/main/Swagger%202.png"/>
<img src="https://github.com/ohikhatemenG/Project-Operationalizing-Machine-Learning-a-Model/blob/main/Swagger%201.png"/>
The results shown above were obtained from consume model endpoints of swagger documentation

# Consume Model Endpoints

After the consume model endpoints of swagger documentation result above, I modified the endpoint.py of both the scoring url and key to match the key for web service and url that was generated after deployment and run to test and accomplish the result.
<img src="https://github.com/ohikhatemenG/Project-Operationalizing-Machine-Learning-a-Model/blob/main/Consume%20Endpoints%202.png"/>
This show that the consume model endpoints was successful

# Bench Marking Endpoints

The benchmark is used to create an acceptable performance, HTTP API is used to find the average response time for a deployed model. I used the apache benchmark to evaluate the performance of the model for ten runs
<img src="https://github.com/ohikhatemenG/Project-Operationalizing-Machine-Learning-a-Model/blob/main/Benchmark%202.png"/>
The bench marking endpionts result

# Createing and Publishing Pipeline

The best way to automated workflow is through pipeline and published pipeline allow external services to interact with them so that they can do work more efficiently. In this project I applied Azure Python Software Development Kit (SDK) and these are the outputs below.
<img src="https://github.com/ohikhatemenG/Project-Operationalizing-Machine-Learning-a-Model/blob/main/create%20%26%20publish%20pipeline%202.png"/>
<img src="https://github.com/ohikhatemenG/Project-Operationalizing-Machine-Learning-a-Model/blob/main/create%20%26%20publish%20pipeline%206.png"/>
<img src="https://github.com/ohikhatemenG/Project-Operationalizing-Machine-Learning-a-Model/blob/main/create%20%26%20publish%20pipeline%2011.png"/>
<img src="https://github.com/ohikhatemenG/Project-Operationalizing-Machine-Learning-a-Model/blob/main/create%20%26%20publish%20pipeline%2012.png"/>
<img src="https://github.com/ohikhatemenG/Project-Operationalizing-Machine-Learning-a-Model/blob/main/create%20%26%20publish%20pipeline%203.png"/>
<img src="https://github.com/ohikhatemenG/Project-Operationalizing-Machine-Learning-a-Model/blob/main/create%20%26%20publish%20pipeline%208.png"/>
<img scr="https://github.com/ohikhatemenG/Project-Operationalizing-Machine-Learning-a-Model/blob/main/create%20%26%20publish%20pipeline%205.png"/>
<img src="https://github.com/ohikhatemenG/Project-Operationalizing-Machine-Learning-a-Model/blob/main/pipeline1.png"/>
<img src="https://github.com/ohikhatemenG/Project-Operationalizing-Machine-Learning-a-Model/blob/main/create%20%26%20publish%20pipeline%205.png"/>
<img src="https://github.com/ohikhatemenG/Project-Operationalizing-Machine-Learning-a-Model/blob/main/create%20%26%20publish%20pipeline%2010.png"/>


# Screencast Record

My project machine learning
https://youtu.be/b8tRtjsArUQ
https://youtu.be/OEzo_C8eiXE

# Additional Information for Improvements

(1) The nature of the dataset is imbalance and application of feature engineering may improve the accuracy
(2) Addition of more data will definitly improve the accuracy
(3) Considering the test of batch data in a scheduled and observe the performance
