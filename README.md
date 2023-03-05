# Hacktech
Predict CO2 emissions from cars with Azure Machine Learning
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
   
    <li> Machine Learning Algorithms and under Regression select the Linear Regression module and drag it onto the canvas

      ![image](https://user-images.githubusercontent.com/101945531/222965814-e36b8b05-031f-4a76-9394-d1845253698e.png)


