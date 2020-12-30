# Project-Operationalizing-Machine-Learning-a-Model
# overview
I will continue to work with the Bank Marketing dataset. I will use Azure to configure a cloud-based Machine Learning Production Model, deploy it, and consume it, and will create, publish, and interact with a pipeline.
# Architectural Diagram
<img src="https://github.com/ohikhatemenG/Project-Operationalizing-Machine-Learning-a-Model/blob/main/Architectual%20Diagram.png"/>
I started with Authentication and then run Auto ML Model or experiement to get the best model and after that I Deploy the Best Model. The next action I took was to applied the Enable Logging(Enable Application Insight) to reveiw important information about the service when consuming the Consume Model Endpoints. The next steps was to Create AND Publish, and interact with a pipeline, finally established a Documentation for the people to read and learn.

# Key Steps

# Authentication
The first stage of the Machine Learning Operations is Authentication, and they are three authentication types.

(1). Key based: Which involved Azure Kubernetes Service (AKS) enable and Azure Container Instances Service(ACI) disable both by default.

(2). Token based: Which involved only Azure Kubernetes Service disable by default.

(3). Interactive based: It is use for local  deployment and experimentation

# Auto ML Model

Navigated to the AutoML section on the workspace and create a new Automated ML run. I created and configured a new computer cluster with Standard DS12_V2, and selected
1 as the number of the minimum nodes and 5 as the number of the maximum nodes. And I selected and uploaded the exist Bank-marketing Dataset.Also I selected y as the target column for the model.I configured the AutoML run using the newly created cluster named bank-cluster and successfully run the AutoML experiement named Bankexperiement. Once the AutoML run was completed.The best model I got was voting ensemble model with accuracy 91.6%.
<img src="https://github.com/ohikhatemenG/Project-Operationalizing-Machine-Learning-a-Model/blob/main/AutoML.png"/>
<img src="https://github.com/ohikhatemenG/Project-Operationalizing-Machine-Learning-a-Model/blob/main/AutoML%202.png"/>
<img src="https://github.com/ohikhatemenG/Project-Operationalizing-Machine-Learning-a-Model/blob/main/AutoML%201.png"/>

# Deploy the Best Model

Since I have the best model ready for deployment, I clicked on deploy and created deploy a model name bank-mk-deploy, and selected Azure Container Instances (ACI) and enable 'Authentication' and run. And after the completed of deployment is successfull, I verified the deployment of the model in order to know the "deploy status" was shown as Healthy, which will create an endpoint
<img src="https://github.com/ohikhatemenG/Project-Operationalizing-Machine-Learning-a-Model/blob/main/Deploy%20healthy.png"/>

# Enable Logging in the Application Insight

Once the model is deployed successfully I took the next steps to engaged in Enable Application Insights through modified of the logs script that enable application insights=True and add the experiment name of the deploy model, and execute the logs script. After the completed run and checked the endpoint section and found that the Application Insight Enabled is equal fail request, server response time, server request and availability.
<img src="https://github.com/ohikhatemenG/Project-Operationalizing-Machine-Learning-a-Model/blob/main/Enable%20logging%203.png"/>
<img src="https://github.com/ohikhatemenG/Project-Operationalizing-Machine-Learning-a-Model/blob/main/Enable%20logging%202.png"/>
<img src="https://github.com/ohikhatemenG/Project-Operationalizing-Machine-Learning-a-Model/blob/main/Enable%20logging%204.png">

# Consume Model Endpoints

Swagger is a tool help build, document and consume RESTful web services in Azure. Once a model is deployed, I was enable to get swagger.json file from the endpoint which I downloaded and placed it in a folder containing swagger file serve.py and swagger.sh. I wanted to create local web server because of that run serve.py and swagger.sh on a terminal
