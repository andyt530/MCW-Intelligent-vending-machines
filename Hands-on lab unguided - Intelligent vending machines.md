![](images/HeaderPic.png "Microsoft Cloud Workshops")

<div class="MCWHeader1">
Intelligent vending machines
</div>

<div class="MCWHeader2">
Hands-on lab unguided
</div>

<div class="MCWHeader3">
March 2018
</div>


Information in this document, including URL and other Internet Web site references, is subject to change without notice. Unless otherwise noted, the example companies, organizations, products, domain names, e-mail addresses, logos, people, places, and events depicted herein are fictitious, and no association with any real company, organization, product, domain name, e-mail address, logo, person, place or event is intended or should be inferred. Complying with all applicable copyright laws is the responsibility of the user. Without limiting the rights under copyright, no part of this document may be reproduced, stored in or introduced into a retrieval system, or transmitted in any form or by any means (electronic, mechanical, photocopying, recording, or otherwise), or for any purpose, without the express written permission of Microsoft Corporation.

Microsoft may have patents, patent applications, trademarks, copyrights, or other intellectual property rights covering subject matter in this document. Except as expressly provided in any written license agreement from Microsoft, the furnishing of this document does not give you any license to these patents, trademarks, copyrights, or other intellectual property.

The names of manufacturers, products, or URLs are provided for informational purposes only and Microsoft makes no representations and warranties, either expressed, implied, or statutory, regarding these manufacturers or the use of the products with any Microsoft technologies. The inclusion of a manufacturer or product does not imply endorsement of Microsoft of the manufacturer or product. Links may be provided to third party sites. Such sites are not under the control of Microsoft and Microsoft is not responsible for the contents of any linked site or any link contained in a linked site, or any changes or updates to such sites. Microsoft is not responsible for webcasting or any other form of transmission received from any linked site. Microsoft is providing these links to you only as a convenience, and the inclusion of any link does not imply endorsement of Microsoft of the site or the products contained therein.
© 2018 Microsoft Corporation. All rights reserved.

Microsoft and the trademarks listed at https://www.microsoft.com/en-us/legal/intellectualproperty/Trademarks/Usage/General.aspx are trademarks of the Microsoft group of companies. All other trademarks are property of their respective owners.

**Contents**
<!-- TOC -->

- [Intelligent vending machines hands-on lab unguided](#intelligent-vending-machines-hands-on-lab-unguided)
    - [Abstract and learning objectives](#abstract-and-learning-objectives)
    - [Overview](#overview)
    - [Solution architecture](#solution-architecture)
    - [Requirements](#requirements)
    - [Exercise 1: Environment setup](#exercise-1--environment-setup)
        - [Task 1: Download and open the vending machines starter project](#task-1--download-and-open-the-vending-machines-starter-project)
            - [Tasks to complete:](#tasks-to-complete)
            - [Exit Criteria:](#exit-criteria)
        - [Task 2: Provision IoT Hub](#task-2--provision-iot-hub)
            - [Tasks to complete:](#tasks-to-complete)
            - [Exit Criteria:](#exit-criteria)
        - [Task 3: Create Microsoft Machine Learning Server on Linux](#task-3--create-microsoft-machine-learning-server-on-linux)
            - [Tasks to complete:](#tasks-to-complete)
            - [Exit Criteria:](#exit-criteria)
        - [Task 4: Create Storage Account](#task-4--create-storage-account)
            - [Tasks to complete:](#tasks-to-complete)
            - [Exit Criteria:](#exit-criteria)
        - [Task 5: Provision Cognitive Services Face API](#task-5--provision-cognitive-services-face-api)
            - [Tasks to complete:](#tasks-to-complete)
            - [Exit Criteria:](#exit-criteria)
        - [Task 6: Provision SQL Database](#task-6--provision-sql-database)
            - [Tasks to complete:](#tasks-to-complete)
            - [Exit Criteria:](#exit-criteria)
    - [Exercise 2: Create Dynamic Pricing Model](#exercise-2--create-dynamic-pricing-model)
        - [Task 1: Create a model locally](#task-1--create-a-model-locally)
            - [Tasks to complete:](#tasks-to-complete)
            - [Exit Criteria:](#exit-criteria)
        - [Task 2: Try a prediction locally](#task-2--try-a-prediction-locally)
            - [Tasks to complete:](#tasks-to-complete)
            - [Exit Criteria:](#exit-criteria)
        - [Task 3: Create the model in R Server on HDInsight](#task-3--create-the-model-in-r-server-on-hdinsight)
            - [Tasks to complete:](#tasks-to-complete)
            - [Exit Criteria:](#exit-criteria)
        - [Task 4: Create predictive service in R Server Operationalization](#task-4--create-predictive-service-in-r-server-operationalization)
            - [Tasks to complete:](#tasks-to-complete)
            - [Exit Criteria:](#exit-criteria)
    - [Exercise 3: Implement dynamic pricing](#exercise-3--implement-dynamic-pricing)
        - [Task 1: Implement photo uploads to Azure Storage](#task-1--implement-photo-uploads-to-azure-storage)
            - [Tasks to complete:](#tasks-to-complete)
            - [Exit Criteria:](#exit-criteria)
        - [Task 2: Invoke Face API](#task-2--invoke-face-api)
            - [Tasks to complete:](#tasks-to-complete)
            - [Exit Criteria:](#exit-criteria)
        - [Task 3: Invoke pricing model](#task-3--invoke-pricing-model)
            - [Tasks to complete:](#tasks-to-complete)
            - [Exit Criteria:](#exit-criteria)
        - [Task 4: Configure the Simulator](#task-4--configure-the-simulator)
            - [Tasks to complete:](#tasks-to-complete)
            - [Exit Criteria:](#exit-criteria)
        - [Task 5: Test dynamic pricing in Simulator](#task-5--test-dynamic-pricing-in-simulator)
            - [Tasks to complete:](#tasks-to-complete)
            - [Exit Criteria:](#exit-criteria)
    - [Exercise 4: Implement purchasing](#exercise-4--implement-purchasing)
        - [Task 1: Create the transactions table](#task-1--create-the-transactions-table)
            - [Tasks to complete:](#tasks-to-complete)
            - [Exit Criteria:](#exit-criteria)
        - [Task 2: Configure the Simulator](#task-2--configure-the-simulator)
            - [Tasks to complete:](#tasks-to-complete)
            - [Exit Criteria:](#exit-criteria)
        - [Task 3: Test purchasing](#task-3--test-purchasing)
            - [Tasks to complete:](#tasks-to-complete)
            - [Exit Criteria:](#exit-criteria)
    - [Exercise 5: Implement device command and control](#exercise-5--implement-device-command-and-control)
        - [Task 1: Listen for control messages](#task-1--listen-for-control-messages)
            - [Tasks to complete:](#tasks-to-complete)
            - [Exit Criteria:](#exit-criteria)
        - [Task 2: Send control messages](#task-2--send-control-messages)
            - [Tasks to complete:](#tasks-to-complete)
            - [Exit Criteria:](#exit-criteria)
        - [Task 3: Configure the DeviceControlConsole and the Simulator](#task-3--configure-the-devicecontrolconsole-and-the-simulator)
            - [Tasks to complete:](#tasks-to-complete)
            - [Exit Criteria:](#exit-criteria)
    - [Exercise 6: Analytics with Power BI Desktop](#exercise-6--analytics-with-power-bi-desktop)
        - [Task 1: Build the query and create the visualization](#task-1--build-the-query-and-create-the-visualization)
            - [Tasks to complete:](#tasks-to-complete)
            - [Exit Criteria:](#exit-criteria)
    - [After the Hands-on Lab](#after-the-hands-on-lab)
        - [Task 1: Delete Resource Group](#task-1--delete-resource-group)
            - [Tasks to complete:](#tasks-to-complete)
            - [Exit Criteria:](#exit-criteria)

<!-- /TOC -->

# Intelligent vending machines hands-on lab unguided

## Abstract and learning objectives

In this workshop, attendees will implement an IoT solution for intelligent vending machines, leveraging facial feature recognition and Azure Machine Learning, to gain a better understanding of building cloud-based machine learning app, and real-time analytics with SQL Database in-memory and columnar indexing.

In addition, attendees will learn to:

-   Enable real-time analytics with SQL Database in-memory and columnar indexing

-   Implement distributed machine learning with R Server for HDInsight & Microsoft R Server Operationalization

-   Perform facial image processing

-   Wrangle data in Power BI Desktop

## Overview

Trey Research Inc. looks at the old way of doing things in retail and introduces innovative experiences that delight customers and drive sales. Their latest initiative focuses on intelligent vending machines that support commerce, engagement analytics, and intelligent promotions.

## Solution architecture

Below are diagrams of the solution architecture you will build in this lab. Please study this carefully, so you understand the whole of the solution as you are working on the various components.

![The preferred solution is shown to meet the customer requirements. From right to left there is an archtecture diagram which shows the connections from a mobile device to a Web Application. The Web Application is shown setting data to an Event Hub which is connected to a Web Job. From there Event Hub and Service Bus work together with Stream Analytics, Power BI and Cosomos DB to provide the full solution.](images/Hands-onlabunguided-Intelligentvendingmachinesimages/media/image2.png)

## Requirements

-   Microsoft Azure subscription must be pay-as-you-go or MSDN.

    -   Trial subscriptions will not work.

-   A virtual machine configured with:

    -   Visual Studio Community 2017 15.6 or later

    -   Azure SDK 2.9 or later (Included with Visual Studio 2017)

    -   [R Tools for Visual Studio](https://www.microsoft.com/en-us/legal/intellectualproperty/Trademarks/Usage/General.aspx) 0.3.2 or later

    -   [Power BI Desktop](http://bit.ly/2w6t2qz) (June 2016 build or later)

-   A running R Server on HD Insight Spark cluster (see [Before the Hands-on Lab](#_Before_the_Hands-on)).


## Exercise 1: Environment setup

Duration: 45 minutes

Trey Research has provided a starter solution for you. They have asked you to use this as the starting point for creating the Vending Machines solution in Azure.

### Task 1: Download and open the vending machines starter project

#### Tasks to complete: 

-   From your Lab VM, download the starter project from [http://bit.ly/2w6t2qz](https://git-scm.com/downloads), and unzip the contents.

-   Open VendingMachines.sln with Visual Studio 2017.

#### Exit Criteria:

-   You have a local copy of the starter project running in Visual Studio on your Lab VM.

**Note**: If you attempt to build the solution at this point, you will see many build errors. This is intentional. You will correct these in the exercises that follow.

### Task 2: Provision IoT Hub

In these steps, you will provision an instance of IoT Hub.

#### Tasks to complete: 

-   Provision an IoT Hub at the S1 Standard tier.

#### Exit Criteria:

-   You can navigate to the IoT Hub instance using the Azure Portal.

### Task 3: Create Microsoft Machine Learning Server on Linux 

In these steps, you will provision and configure a Virtual Machine running Microsoft Machine Learning Server. You will use this machine to host the R Server Operationalization service.

#### Tasks to complete: 

-   Provision a VM instance of Microsoft Machine Learning Server 9.3.0 on Ubuntu 16.04 from the Marketplace. The deployment model should be Resource Manager and size of Standard E2S V3.

-   Add an inbound bound rule to the Network Security Group attached to the Network Interface of the VM, that allows TCP connections to Port: 12800

-   Confirm there is already a default-allow-ssh rule on TCP port 22.

#### Exit Criteria:

-   You can successfully SSH into the VM.

### Task 4: Create Storage Account

In these steps, you will provision a storage account that will be used for storing photos sent from the vending machine simulator and for the storage of the promotional package resources.

#### Tasks to complete: 

-   Create a new Azure Storage account in the same region and resource group as your other resources for this hands-on lab. It can use Locally-redundant storage (LRS).

-   Using the Portal, create a container named "photos" with a private access type.

-   Using the Portal, create a container named "promos" with a private access type.

-   Using the Azure Storage explorer tool of your choice, upload the three images (CoconutWater.png, Soda.png, and Water.png) into the promo container. They can be found in the starter solution under Simulator\\Images.

#### Exit Criteria:

-   Your Azure Storage account should have a promo and photos container. The former should have the three photos from the starter solution in it.

### Task 5: Provision Cognitive Services Face API

To provision access to the Face API (which provides demographic information about photos of human subjects), you will need to provision a Cognitive Services account.

#### Tasks to complete: 

-   Provision a Cognitive Services account of type Face API.

#### Exit Criteria:

-   You can navigate to the Face API blade, and locate its key1 value, available under Settings -\> Keys.

-   You can retrieve Face API Endpoint from the Essentials block of the Overview blade.

### Task 6: Provision SQL Database

In these steps, you will provision a SQL database to support the transactions and real-time analytics.

#### Tasks to complete: 

-   Provision a SQL Database in the Premium (P1) tier.

#### Exit Criteria:

-   You can navigate to the blade for the SQL Database, and locate its ADO.NET connection string.

## Exercise 2: Create Dynamic Pricing Model

Duration: 45 minutes

In this exercise, you will create a machine learning model that predicts the purchase price for an item sold by the vending machine, provided the demographics of the customer and the item. You will then operationalize this model by exposing it as a web service hosted in Azure Machine Learning, and test it out.

### Task 1: Create a model locally

#### Tasks to complete: 

-   In Visual Studio, open TrainModel.R located within the PricingModel project.

-   Run the text between the "Create Sample Data" and "END Create Sample Data" comments, and view the sampleData created in the Variable Explorer window.

-   Complete TODO 1 through 4.

#### Exit Criteria:

-   In the same folder as your script, you should have the files sampleData.RData, pricingModel.RData, and inputExample.RData.

### Task 2: Try a prediction locally

#### Tasks to complete: 

-   In Visual Studio, open PredictUsingModel.R located within the PricingModel project.

-   Complete TODO 1 through 2.

-   Run the script.

#### Exit Criteria:

-   Using Variable Explorer, expand the prediction variable and observe the price the model suggested to use for purchasing the coconut water for the input of a 30-year-old female.
    ![Screenshot of Variable Explorer, with a purchase price suggestion of 0.949.](images/Hands-onlabunguided-Intelligentvendingmachinesimages/media/image34.png "Variable Explorer")

### Task 3: Create the model in R Server on HDInsight

#### Tasks to complete: 

-   SSH into your R Server on HDInsight Cluster.

-   Run the R shell.

-   Copy the script text from PredictUsingModel.r and paste it into the shell to train the model using R running across your HDInsight cluster.

-   Copy the generated files samleData.RData pricingModel.RData, and inputExample.RData to the /models folder in HDFS.

-   Use Visual Studio to download the sampleData.RData, pricingModel.RData, and inputExample.RData from Blob storage to the PricingModel project directory, overwriting existing files as necessary.

#### Exit Criteria:

-   You should have the files sampleData.RData, pricingModel.RData, and inputExample.RData copied down to the PricingModel project directory on your local machine.

### Task 4: Create predictive service in R Server Operationalization

After training a model, you want to operationalize the model so that it becomes available for integration by developers. One way to operationalize a trained model is to take the model you trained in HDInsight, and then to expose that as a predictive web service. In this task, you take a version of the scripts you have been running locally and in HDInsight and migrate them to run in the VM that is running R.

#### Tasks to complete: 

-   SSH into your Microsoft Machine Learning Server VM

-   Use the Azure CLI commands to configure Microsoft R Server operationalization with a One-box configuration.

    -   sudo -i

    -   az ml admin node setup \--onebox \--admin-password Password.1!! \--confirm-password Password.1!!

-   Update the App.config for the Simulator with the settings for:

    -   rServiceBaseAddress: with your server IP and web node port (example: http://\<your-server-ip\>:12800).

    -   rServicePassword: as set when you configured R Server operationalization.

-   Update the TODO 1 section of the PredictPricingService.r file within the PricingModelProject to reference the following packages:

    -   curl

    -   ggplot2

    -   mrsdeploy

    -   RevoScaleR

-   Update TODO 2 to remoteLogin to the R Server operationalization web node with the admin user and configured password.

-   Execute all the code interactively to publish the service.

-   Update TODO 3 to consume the API as a test, printing the result\$output("answer") value.

-   Update TODO 4 to generate the Swagger JSON file for the API, and save it as swagger.json to the project directory.

#### Exit Criteria:

-   You successfully configured Microsoft Machine Learning Server operationalization.

-   Your apiPredictPurchasePrice service was successfully published.

-   You are able retrieve a prediction result from the service.

-   You have generated the Swagger JSON file for the service.

## Exercise 3: Implement dynamic pricing

Duration: 45 minutes

In this exercise, you will implement the code that performs dynamic pricing, capitalizing on the Face API to acquire demographics, and your deployed pricing model to suggest the price based on those demographics. You will then run the vending machine simulator and see the dynamic pricing in action.

### Task 1: Implement photo uploads to Azure Storage

#### Tasks to complete: 

-   In Visual Studio Solution Explorer, expand the Simulator project and then MainWindow.xaml, and then open MainWindow.xaml.cs and scroll to the UpdateDynamicPricing method.

-   Complete TODO 1 through 3.

-   Save the file.

#### Exit Criteria:

-   You have removed any errors around TODO items 1 through 3.

### Task 2: Invoke Face API 

#### Tasks to complete: 

-   Within MainWindow.xaml.cs, locate the GetBlobSasUri method.

-   Complete TODO items 4 through 9.

-   Save the file.

#### Exit Criteria:

-   You have removed any errors around TODO items 4 through 9.

### Task 3: Invoke pricing model

#### Tasks to complete: 

-   Within MainWindow.xaml.cs, locate and complete TODO 10.

-   Save the file.

#### Exit Criteria:

-   You have removed any errors around TODO item 10.

### Task 4: Configure the Simulator

#### Tasks to complete: 

-   In Visual Studio, open App.config within the Simulator project.

-   Within the appSettings section, set the following settings:

    -   faceAPIKey: set this to the KEY 1 value for your Face API as acquired from the Azure Portal.

    -   faceEndpoint: set this to the ENDPOINT value for your Face API as acquired from the Azure Portal (for example: https://eastus2.api.cognitive.microsoft.com/face/v1.0)

    -   storageConnectionString: set this to the connection string for the Storage Account you created with the photos container.

-   Save the App.config.

#### Exit Criteria:

-   You have values for the settings in the config file.

### Task 5: Test dynamic pricing in Simulator

#### Tasks to complete: 

-   Set the Simulator project as the startup project.

-   Run the Simulator without debugging.

-   Take a picture using the simulator.

#### Exit Criteria:

-   In a few moments, you should see the price change from \$1.25 to whatever value the predictive model suggested.
    
    ![Screenshot of the Vending Machine price for coconut water, now set at \$0.91.](images/Hands-onlabunguided-Intelligentvendingmachinesimages/media/image35.png "Vending Machine price")

## Exercise 4: Implement purchasing

Duration: 15 minutes

In this exercise, you will create an in-memory, columnar index table in SQL DB that will be used to support purchase transactions in a real-time analytics fashion, and then implement the purchasing process in the vending machine simulator. Finally, you will run the simulator and purchase items.

### Task 1: Create the transactions table

#### Tasks to complete: 

-   Within Visual Studio Solution Explorer, expand the SQL Scripts folder and open the file Create Table.sql.

-   Complete TODO items 1 through 4.

-   Save the script.

-   Execute the script against your SQL Database.

#### Exit Criteria:

-   You have successfully executed the SQL script against the vending database.

### Task 2: Configure the Simulator

#### Tasks to complete: 

-   In the Simulator project, open App.config.

-   Within the connectionString section, set the following:

    -   TransactionsModel: set the value of the connectionString attribute to the ADO.NET connection string to your SQL DB instance.

-   Save the App.config.

#### Exit Criteria:

-   The value for the connectionString has been updated.

### Task 3: Test purchasing

#### Tasks to complete: 

-   Build the Simulator.

-   Start the Simulator without debugging.

-   In the Simulator, select Buy.

#### Exit Criteria:

-   You should see a confirmation dialog like the following:
    
    ![Screenshot of a Confirmation dialog box that says, \"Purchase complete. Enjoy!\"](images/Hands-onlabunguided-Intelligentvendingmachinesimages/media/image36.png "Confirmation dialog box")

## Exercise 5: Implement device command and control

Duration: 30 minutes

In this exercise, you will implement the ability to push new promotions to the vending machine simulator using the command and control features of IoT Hub. You will update the simulator to listen for these messages. You will also update the console application DeviceControlConsole to send selected promotions.

### Task 1: Listen for control messages

#### Tasks to complete: 

-   Within Visual Studio Solution Explorer, expand the Simulator project and open the file MainWindow.xaml.cs.

-   Complete TODO items 1 through 4.

-   Save the file.

#### Exit Criteria:

-   You have no errors around TODO items 1 through 4 in MainWindow.xaml.cs.

### Task 2: Send control messages

#### Tasks to complete: 

-   Within Visual Studio Solution Explorer, expand the DeviceControlConsole project, and open the file Program.cs.

-   Complete TODO items 1 and 2.

-   Save the file.

#### Exit Criteria:

-   You have no errors around TODO items 1 and 2 in Program.cs.

### Task 3: Configure the DeviceControlConsole and the Simulator

#### Tasks to complete: 

-   In the DeviceControlConsole project, open App.config.

-   Set the IoTHubConnectionString appSetting to have a value of the connection string for the service policy to your IoT Hub. (Recall you can get this from the Azure Portal, Settings, Keys.)

-   Set the storageConnectionString appSetting to have the same connection string for your storage account that the App.config file in the Simulator project has.

-   Save the file.

-   In the Simulator project, open App.config.

-   Set the IoTHubSenderConnectionString appSetting to have a value of the connection string for the device policy to your IoT Hub (recall you can get this from the Azure Portal, Settings, Keys).

-   Set the IoTHubManagerConnectionString appSetting to have a value of the connection string for the iothubowner policy to your IoT Hub.

-   Save the file.

-   Set both the DeviceControlConsole and Simulator to startup projects for the solution.

-   Start without debugging.

#### Exit Criteria:

-   Both the Vending Machine Simulator and the DeviceControlConsole appear.
    
    ![Screenshot of the Vending Machine Simulator and DeviceControlConsole side-by-side. The vending machine simulator displays the advertisement for coconut water.](images/Hands-onlabunguided-Intelligentvendingmachinesimages/media/image37.png "Vending Machine Simulator and DeviceControlConsole")

-   In the DeviceControlConsole, press 1 to push the promotion for soda.

    ![Screenshot of the Vending Machine Simulator and DeviceControlConsole side-by-side. The vending machine simulator now displays the advertisement for soda.](images/Hands-onlabunguided-Intelligentvendingmachinesimages/media/image38.png)

-   The entire promotion surface of the vending machine changes (product name, price, and image).

## Exercise 6: Analytics with Power BI Desktop

Duration: 15 minutes

In this exercise, you will use Power BI Desktop to query purchase data from the in-memory table of SQL DB and visualize the result.

### Task 1: Build the query and create the visualization

#### Tasks to complete: 

-   Open Power BI Desktop and connect to your SQL Database.

-   Query the transactions table.

-   Create a Stacked column chart visualization that displays the sum of the purchase price by minute across all the data in the table.

#### Exit Criteria:

-   Your chart should appear as follows:
    
    ![Screenshot of the Purchase Price by Minute stacked column chart.](images/Hands-onlabunguided-Intelligentvendingmachinesimages/media/image39.png "Purchase Price by Minute")

## After the Hands-on Lab 

Duration: 10 mins

In this exercise, attendees will deprovision any Azure resources that were created in support of the lab.

### Task 1: Delete Resource Group

#### Tasks to complete: 

-   Delete the Resource Group you created.

#### Exit Criteria:

-   You have no services deployed for this hackathon remaining in your subscription.

