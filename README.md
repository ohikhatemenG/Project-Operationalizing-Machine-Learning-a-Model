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
1 as the number of the minimum nodes and 5 as the number of the maximum nodes. And I selected and uploaded the exist Bank-marketing Dataset.Also I selected y as the target column for the model.I configured the AutoML run using the newly created cluster named bank-cluster and successfully run the AutoML experiement named Bankexperiement. Once the AutoML run was completed.The best model I got was voting ensemble model with accuracy 91.62% 
