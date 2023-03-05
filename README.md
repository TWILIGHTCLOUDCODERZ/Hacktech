# Hacktech
Predict CO2 emissions from cars with Azure Machine Learning

# Test 

[ClicK to test the ML project](https://ml.azure.com/experiments/id/e34be1b0-38d6-4026-9370-47d902a60a4a/runs/7189338a-dbf9-408b-ab49-aa558e0139e7?wsid=/subscriptions/63ef8b26-b9c5-487a-9543-8bd28f703592/resourcegroups/Hacktech/providers/Microsoft.MachineLearningServices/workspaces/Hacktech&tid=f6365406-ec6d-449c-a9a1-95f6a70d355d&nsq=runStatus+in+{Completed}#/?graphId=808b800e-47a8-4f71-8845-b5944b16953f&label=carbon+prediction&newGraphId=808b800e-47a8-4f71-8845-b5944b16953f&path=%2Fexperiments%2Fid%2Fe34be1b0-38d6-4026-9370-47d902a60a4a%2Fruns%2F7189338a-dbf9-408b-ab49-aa558e0139e7&runId=7189338a-dbf9-408b-ab49-aa558e0139e7)
  
<br>
  
[Swagger Json](https://eastus2.api.azureml.ms/pipelines/swagger/pipelineendpointsubmit/swagger.json)
  
<br>

## Problem

![2](https://user-images.githubusercontent.com/101945531/222964587-ad6d4324-9141-4ddf-8116-14edde1facd6.png)
<br>
## Solution

![3](https://user-images.githubusercontent.com/101945531/222964635-aa46c568-2484-4517-94d5-272db06468f8.png)
<br>
## Create an Azure Machine Learning workspace
<li> Sign in to Azure Portal and select Create a resource.
<li> Search for Machine Learning and then click Create to start
<li> Configure the new Machine Learning resource.Select subscription, resource group, workspace name, region and click Review-Create.
<li> Wait for the workspace to be created (it may take several minutes) and then select Go to resource
<li> Click on Studio Web URL to go to your Azure Machine Learning workspace.
<br>
  
## workspace

<li> Create dataset->select Asset and then select Data + Create Dataset > 
  
![image](https://user-images.githubusercontent.com/101945531/222964949-cb060518-1e4f-41e7-bf59-ea49cea22f6a.png)
  
<li> Provide relevant name and details  
  
![image](https://user-images.githubusercontent.com/101945531/222965015-6c48fc2a-72e6-4fd3-8d50-290d40d670aa.png)

<li> In Datastore and file selection select Browse and choose the file on your local computer
  
![image](https://user-images.githubusercontent.com/101945531/222965085-bf68a69c-c4b0-4957-afca-b498537d9825.png)

<li>Select database type where your data result needs to be stored
  
![image](https://user-images.githubusercontent.com/101945531/222965209-692452c9-8e13-40ef-9f67-7f067a9130ac.png)
  
<li>Upload data from local machine U CAN CHOOSE OTHER RESOURCES LIKE COSMODB,BLOB, ONLINE SERVICES ENDPOINT)

![image](https://user-images.githubusercontent.com/101945531/222965263-ae7c8a04-6325-4719-b1b1-d44b5a49a0ca.png)

<li>Customize data parameter 
  
![image](https://user-images.githubusercontent.com/101945531/222965329-35335ca2-b1d9-4ed1-91b0-981c3dcbb815.png)
  
<li>Change the schema type as per data type
  
![image](https://user-images.githubusercontent.com/101945531/222965367-6db8c604-8829-40f6-b559-53d5dc5c23cf.png)
  
<li>Review and Create
  
![image](https://user-images.githubusercontent.com/101945531/222965396-a42c0ac1-802a-417d-88d7-57a806ce89ce.png)

## Create a new pipeline

<li> Select Designer and then select the plus sign (+) to create a new pipeline
  
 ![image](https://user-images.githubusercontent.com/101945531/222965580-6211f315-e9bc-4af2-8267-9fa1e6752420.png)

<li> Expand the Datasets section, select the dataset carbon-control and drag it onto the canvas  
  
![image](https://user-images.githubusercontent.com/101945531/222965459-a7a58c70-0dd2-45ff-b07a-f43d20eaec42.png)
  
<li> Data transformation section drag Split data module onto the canvas and connect the dataset’s output port to the Split data module. Simply drag from the dataset’s output port to the Split data module’s input port.
  
 ![image](https://user-images.githubusercontent.com/101945531/222965756-6ee41b21-a8e0-46b7-8e41-9b080cc1e97d.png)
  
 <li> Machine Learning Algorithms and under Regression select the Linear Regression module and drag it onto the canvas
   
  ![image](https://user-images.githubusercontent.com/101945531/222965784-8e2f3ac2-e210-4a2a-bc2e-796bf731d240.png)
   
<li> Model Training section, select Train Model. Connect the output port of the Linear Regression module to the left input port of the Train Model module. Connect the left port (training set) of the Split Data module to the right input port.
  
 ![image](https://user-images.githubusercontent.com/101945531/222965814-e36b8b05-031f-4a76-9394-d1845253698e.png)

  <li> Select the Train Model module and in the right pane click on Edit column to select the label column (the variable that you want to predict).
    
 ![image](https://user-images.githubusercontent.com/101945531/222965924-2e9f5970-2dd0-44d7-bf63-54955c20520b.png)

<li> Model Scoring and Evaluation section, select the Evaluate Model module. Connect the output of the Score Model module to the left input of the Evaluate Model module
  
![image](https://user-images.githubusercontent.com/101945531/222965983-04439f5d-bee6-469c-bc9e-ab1afd6f556b.png)
  
<br>
  
![image](https://user-images.githubusercontent.com/101945531/222965996-a165b85b-9789-4ac7-b244-993d28800442.png)

  ## Training model
  
  ![image](https://user-images.githubusercontent.com/101945531/222966040-d25c403f-1442-47b6-bec6-f0d4a3af4030.png)

  
  ## Set up Compute target
  
 <li> Select the settings icon. In the setting pane, under Default compute target click on Select compute target.
 
 ![image](https://user-images.githubusercontent.com/101945531/222966104-ba1d8d11-55aa-4205-b7cc-3b681b76f03e.png)
  
 <li> Depends on your need create compute target ( cpu/gpu core is high time consumption will be reduced)
   
 ![image](https://user-images.githubusercontent.com/101945531/222966152-7911ac81-0dbd-4729-a6d5-e5addaad6a1a.png)
      
<br>
      
 [image](https://user-images.githubusercontent.com/101945531/222966182-4a0f8e54-06b4-4cbc-9ac4-3414193b7e93.png)
   
 ## Run the training pipeline
   
<li> Set up pipeline run form, select Create new, enter a name for the experiment and click Submit. 
  
![image](https://user-images.githubusercontent.com/101945531/222966252-317fd4c9-c68e-462c-8752-7ea6e0538f14.png)
  
 <li> Monitor the pipeline job run
   
 ![image](https://user-images.githubusercontent.com/101945531/222966287-d4e90865-e788-4bba-870c-419aa7e5a2fb.png)
   
 ## Result 
   
 <li>Right-click the Score Model and select Visualize > Scored dataset. The last two columns of the dataset are the actual and the predicted CO2 emissions
   
 ![image](https://user-images.githubusercontent.com/101945531/222966324-a3b0ec8f-e7e9-4b5c-91a3-379c4c0deb32.png)

  
   

     

